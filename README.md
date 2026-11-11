# Siddharth Srivastava (`@sidsri14`)

Open-source systems and LLM tooling developer based in Lucknow, India. I build
reliable Rust and TypeScript systems, and I contribute focused fixes upstream.

Open to remote full-time, contract, and relocation-supported software roles.

[Services & Kits](https://sidsri14.github.io) | [Upwork ($60/hr)](https://www.upwork.com/freelancers/~01f93f1a56b9ef1b8d) | [LinkedIn](https://www.linkedin.com/in/siddharth-srivastava-529a21277/) | [StackIntercept](https://stackintercept.com) | [Email](mailto:sidsri1502@gmail.com)

## Selected Work & Commercial Boilerplates

### [Solana Anchor + Token-2022 Starter](https://github.com/sidsri14/solana-anchor-token2022-starter)

Production-grade Anchor 0.30+ monorepo engineered for Solana dApps with Token-2022 extensions, custom Transfer Hook CPI compliance enforcement, automated TypeScript client SDK with dynamic priority fee routing, and integration test suites. Available for custom smart contract & Web3 engineering via [Upwork](https://www.upwork.com/freelancers/~01f93f1a56b9ef1b8d).

### [Solana DEX & MCP Analytics](https://github.com/sidsri14/solana-dex-analytics) · [MCP Server](https://github.com/sidsri14/mcp-solana-analytics)

Real-time Solana instruction log parsers, constant-product bonding curve simulators, Raydium CPMM swap/liquidity migration math, wallet profitability profiling, and Model Context Protocol (MCP) JSON-RPC tooling (**18/18 automated tests passing** across both suites).

### [Resilient AI Worker Kit](https://github.com/sidsri14/resilient-ai-worker-kit)
[![Get Pro Edition on Polar](https://img.shields.io/badge/Polar.sh-Instant_Checkout_%2439-blue?style=flat&logo=github)](https://buy.polar.sh/polar_cl_4mrUXvOPjiB4LEIEBsVyJshejMA8oq7XIHPQV163dbE)

Fault-tolerant background AI agent queue built on Node.js, BullMQ, and Redis. Features real-time atomic token-budget kill switches, automatic multi-provider model failover (OpenAI -> Anthropic -> Groq) on 429/500 errors, clean TypeScript builds (`tsc`), and **7/7 passing Vitest tests**.

### [Hybrid AI On-Device & Cloud Router](https://github.com/sidsri14/hybrid-ai-router)
[![Commercial Edition on Polar](https://img.shields.io/badge/Polar.sh-Instant_Checkout_%2449-blue?style=flat&logo=github)](https://buy.polar.sh/polar_cl_aChnKOBlSuTr0gEWTc1tZdxEFtcx3EuRWja9l4R1qiW)

Hybrid inference routing layer combining sub-millisecond on-device complexity/PII classification (Gemma 2B / SmolLM) with Gemini cloud escalation and bidirectional circuit-breaker failover (**11/11 passing Vitest tests**).

### [PayPal ScopeGuard](https://github.com/sidsri14/paypal-scopeguard)

Fail-closed agentic commerce control plane built on the PayPal Developer Platform (Orders v2 REST API + `PayPal-Request-Id` idempotency + raw-body RSA-SHA256 webhook verification) and strict JSON-schema intent extraction (**25/25 passing unit tests**).

### [StackIntercept](https://github.com/sidsri14/stack-intercept)

A Rust proxy for OpenAI-compatible LLM APIs with exact and semantic caching, reactive failover, Prometheus metrics, and tenant isolation (**38/38 passing `cargo test` suites**). Designed for teams that want to inspect cache behavior and upstream failures without moving prompts outside their own deployment.

### [DriftGuard](https://github.com/sidsri14/driftguard)

A local-first CI evaluation engine and pre-commit gate built in Rust. It catches missing environment variables, schema drift, and broken LLM output contracts before merge using Git-diff scoped AST scanning and strict JSON Schema validation.

### [Tempo Z-Spend](https://github.com/sidsri14/tempo-zspend)

An agent spend-control prototype that enforces per-agent, per-window USDC limits in code. Its five local suites contain 31 passing tests across policy, Monad, Arc, BSC, and control-plane paths. It is prototype work, not a deployed financial product.

### [SolSentinel](https://github.com/sidsri14/solsentinel)

Static analysis tooling for Solana programs. It detects 10 documented vulnerability classes and is intended as a practical security-review aid.

## Upstream Contributions

**22 merged pull requests** across external upstream open-source repositories, including:

| Repository | Merged contribution |
| --- | --- |
| [BerriAI/litellm](https://github.com/BerriAI/litellm/pull/50073) | Bedrock Converse cross-model signed-thinking leak fix (`main`) |
| [open-telemetry/opentelemetry-python-contrib](https://github.com/open-telemetry/opentelemetry-python-contrib/pull/4982) | Restore logging handlers and formatters on `uninstrument()` (`main`) |
| [open-telemetry/opentelemetry-python](https://github.com/open-telemetry/opentelemetry-python/pull/5545) | Bounded resource-detector waits to configured timeout |
| [temporalio/sdk-typescript](https://github.com/temporalio/sdk-typescript/pull/2249) | Preserved zero-value optional durations in workflow dispatch |
| [DataDog/guarddog](https://github.com/DataDog/guarddog/pull/827) | Rust/crates.io support for supply-chain malware scanning |
| [scalar/scalar](https://github.com/scalar/scalar/pull/9945) | Omit empty `Cookie` header when `X-Scalar-Cookie` is absent |
| [tailscale/hujson](https://github.com/tailscale/hujson/pull/48) | Parser handling for ambiguous Unicode line separators |
| [getsentry/tacos-gha](https://github.com/getsentry/tacos-gha/pull/319) | Regression fix for a deletion-path `KeyError` in CI workflows |
| [nushell/nushell](https://github.com/nushell/nushell/pull/18976) | Error-stream propagation across pipeline commands |
| [grafana/gcx](https://github.com/grafana/gcx/pull/1066) | Safer environment-credential behavior after OS keychain lookup failure |

## 📚 Technical Writing & Articles

- [**Building Custom Royalty & Compliance Rules with Solana Token-2022 Transfer Hooks in Anchor 0.30+**](https://dev.to/sidsri14/building-custom-royalty-compliance-rules-with-solana-token-2022-transfer-hooks-in-anchor-030-1bm9) — In-depth architectural tutorial on SPL Transfer Hook CPI resolution, dynamic extra account metas, and fast deterministic testing.
- [**Preventing Runaway LLM Bills: Building a Resilient AI Worker Queue with Redis, BullMQ, and Model Fallbacks**](https://sidsri14.github.io/articles/prevent-runaway-llm-bills-bullmq.html) — Guide to mitigating cascading rate limits and enforcing hard spending caps in agent queues.
- [**Cutting AI Inference Bills with Hybrid On-Device Routing**](https://sidsri14.github.io/articles/slash-ai-api-costs-hybrid-router.html) — Deterministic complexity/PII classification routing edge tasks locally while escalating complex calls cleanly.
- [**Why Async SSE Streaming Collapses Reverse Proxy Connection Pools (and How to Fix It in Rust)**](articles/why-async-sse-streaming-collapses-connection-pools.md) — Deep architectural teardown on LLM token streaming, client disconnection TCP socket leaks, and backpressure handling with Tokio & Axum.
- [**20 Merged PRs Across 18 OSS Organizations: A Deep Dive into Real-World Upstream Engineering**](articles/20-merged-prs-across-18-oss-orgs.md) — Detailed catalog of root causes, fixes, and lessons from Datadog, Tailscale, Sentry, OpenTelemetry, Temporal, and Grafana.
- [**Silent Cache Poisoning in LLM Streaming Proxies**](https://sidsri14.github.io/articles/silent-cache-poisoning-llm-proxies.html) — How transient upstream stream truncation corrupts exact/semantic caches on HTTP 200, and how to enforce completion invariants.

Additional open-source contributions in review across `BerriAI/litellm`, `makeplane/plane`, `calcom/cal.diy`, `inngest/inngest-js`, `cadence-workflow/cadence`, and `BurntSushi/ripgrep`.

## Technical Focus

- Rust, TypeScript, Node.js, Python, Go
- Solana Smart Contracts (Anchor 0.30+, Token-2022 Transfer Hooks, DEX analytics)
- Async services, HTTP/SSE streaming, API design, testing, debugging
- PostgreSQL, Redis / BullMQ, Docker, Prometheus, Linux, GitHub Actions
- LLM gateway patterns, semantic caching, failover, and observability

## Contact & Consulting

- **Upwork Contracts & Project Catalog**: [Sid S. (`~01f93f1a56b9ef1b8d`)](https://www.upwork.com/freelancers/~01f93f1a56b9ef1b8d)
- Email: `sidsri1502@gmail.com`
- X: [@SidSri0228](https://x.com/SidSri0228)
- LinkedIn: [siddharth-srivastava](https://www.linkedin.com/in/siddharth-srivastava-529a21277/)
- Arc / Codementor: [arc.dev/@sidsri929666](https://arc.dev/@sidsri929666?preview=1) (Available for Rust, Solana, and Systems Debugging)
- Cantina Auditor Profile: [cantina.xyz/@sidsri14](https://cantina.xyz/)

