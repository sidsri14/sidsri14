# Silent Cache Poisoning in LLM Streaming Proxies

An LLM proxy can receive HTTP 200, forward several Server-Sent Event chunks,
and still fail before the stream is complete. Treating the status code as proof
of a cacheable response turns a transient upstream failure into a persistent,
replayable partial answer.

I found this boundary while reviewing StackIntercept, a small Rust
OpenAI-compatible proxy. It forwards upstream SSE bytes and stores successful
responses in an exact cache. The initial implementation used the upstream HTTP
status to decide whether to cache a stream. That is insufficient: after a 200,
`bytes_stream()` can still yield an error because the upstream connection was
truncated or reset.

## The unsafe sequence

1. The upstream returns 200 and starts a streamed completion.
2. The proxy forwards a few valid `data:` frames.
3. The upstream connection breaks before `[DONE]`.
4. The proxy sends the client a terminal SSE error frame.
5. The proxy caches the bytes collected before the error because the initial
   status was successful.

The next identical request can then receive a cache hit containing an
incomplete completion, without any indication that it was partial.

## The required invariant

For a streamed response, cache insertion needs two conditions:

```text
initial HTTP response is successful
AND
the body stream completed without an error
```

StackIntercept now tracks stream completion separately from the HTTP status. On
a chunk error, it forwards an SSE error frame and marks the stream incomplete.
The terminal cache-insertion step checks that marker before inserting into the
exact or semantic cache.

The relevant implementation is in
[`src/main.rs`](https://github.com/sidsri14/stack-intercept/blob/master/src/main.rs),
and the regression test is in
[`test_persistence_eviction_sse.py`](https://github.com/sidsri14/stack-intercept/blob/master/test_persistence_eviction_sse.py).
The test serves a deliberately truncated SSE body with a larger declared
`Content-Length`, verifies that the client receives an error frame and `[DONE]`,
then verifies the next identical request is a cache miss rather than a replay
of partial data.

## Where failover stops

StackIntercept's configured fallback is intentionally a single retry before a
stream has produced body bytes: a connection failure, 429, or configured 5xx
status can select the fallback request. It does not retry after partial stream
output. Restarting a different model response after visible tokens have reached
the client changes the response contract and can duplicate side effects in
tool-using workflows.

That is a reliability boundary, not a complete high-availability system. The
project does not currently provide circuit breaking, health-based load
balancing, rate limiting, or spend caps.

## What this does not prove

This change does not make any claim about TCP backpressure, connection-pool
behavior, zero-copy operation, or throughput under slow clients. The current
streaming path accumulates a completed response before caching it, so it should
be evaluated with explicit response-size limits and load tests before making
performance claims. The evidence here is narrower: a truncated upstream stream
will not poison the cache.

## Reproduce

From the StackIntercept repository:

```powershell
cargo build
python test_persistence_eviction_sse.py
```

The suite uses only a local mock upstream and includes the truncated-stream
case alongside cache persistence and SSE error-frame checks.
