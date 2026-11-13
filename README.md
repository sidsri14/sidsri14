# Siddharth Srivastava (`@sidsri14`)

Independent software developer based in Lucknow, India. I work on AI-assisted
Rust and TypeScript projects and contribute focused fixes upstream. The projects
below are personal projects and prototypes, not employment or production client
experience.

Available for remote, paid backend debugging and developer-tooling projects.

[Paid projects on Upwork](https://www.upwork.com/freelancers/~01f93f1a56b9ef1b8d) | [LinkedIn](https://www.linkedin.com/in/siddharth-srivastava-529a21277/) | [StackIntercept source](https://github.com/sidsri14/stack-intercept) | [Email](mailto:sidsri1502@gmail.com)

## Start with a bounded paid task

- **Backend/API debugging:** one reproducible failure, a focused fix, regression
  coverage and a short handoff. [Discuss the scope on Upwork](https://www.upwork.com/freelancers/~01f93f1a56b9ef1b8d).
- **MCP tool or server:** one agreed integration with automated tests.
  [View the existing Project Catalog service](https://www.upwork.com/services/product/development-it-one-model-context-protocol-mcp-tool-or-server-built-with-automated-tests-2116134634537475815).

We agree the stack, expected behavior, acceptance criteria, price and funded
milestones before custom work starts. AI assistance is disclosed, and I review
and verify the changes I deliver.

## Selected Independent Projects

### [Solana Anchor + Token-2022 Starter](https://github.com/sidsri14/solana-anchor-token2022-starter)

An independent Anchor/Token-2022 starter prototype with TypeScript examples and tests.

### [Solana DEX & MCP Analytics](https://github.com/sidsri14/solana-dex-analytics) · [MCP Server](https://github.com/sidsri14/mcp-solana-analytics)

Independent Solana analytics and MCP tooling prototypes. Their repositories document the implementation and local test scope.

### [Resilient AI Worker Kit](https://github.com/sidsri14/resilient-ai-worker-kit)
[![Get Pro Edition on Polar](https://img.shields.io/badge/Polar.sh-Instant_Checkout_%2439-blue?style=flat&logo=github)](https://buy.polar.sh/polar_cl_4mrUXvOPjiB4LEIEBsVyJshejMA8oq7XIHPQV163dbE)

A Node.js/TypeScript starter exploring BullMQ queues, sequential mock-provider fallback and Redis-backed usage accounting. Seven local tests use mock providers and an in-memory Redis substitute. Live provider adapters are not included, and the separate budget check and usage update do not guarantee a spending cap. The source is public under MIT; the paid offering is a packaged distribution and separately scoped setup guidance.

### [Hybrid AI On-Device & Cloud Router](https://github.com/sidsri14/hybrid-ai-router)
[![Commercial Edition on Polar](https://img.shields.io/badge/Polar.sh-Instant_Checkout_%2449-blue?style=flat&logo=github)](https://buy.polar.sh/polar_cl_aChnKOBlSuTr0gEWTc1tZdxEFtcx3EuRWja9l4R1qiW)

An independent TypeScript prototype exploring local/cloud routing, classification and fallback.

### [PayPal ScopeGuard](https://github.com/sidsri14/paypal-scopeguard)

An independent PayPal API and webhook prototype with local tests.

### [StackIntercept](https://github.com/sidsri14/stack-intercept)

A Rust proxy for OpenAI-compatible LLM APIs with exact caching, optional semantic caching, reactive failover, Prometheus metrics and tenant-scoped behavior. Local mock-upstream tests exercise its API and failure paths.

### [DriftGuard](https://github.com/sidsri14/driftguard)

A local-first CI evaluation engine and pre-commit gate built in Rust. It catches missing environment variables, schema drift, and broken LLM output contracts before merge using Git-diff scoped AST scanning and strict JSON Schema validation.

### [Tempo Z-Spend](https://github.com/sidsri14/tempo-zspend)

An agent spend-control prototype exploring per-agent, per-window policies with local tests.

### [SolSentinel](https://github.com/sidsri14/solsentinel)

An independent static-analysis prototype for Solana programs.

## Upstream Contributions

**23 merged pull requests in external repositories**, verified November 13, 2026.
Selected contributions:

| Repository | Merged contribution |
| --- | --- |
| [BerriAI/litellm](https://github.com/BerriAI/litellm/pull/50073) | Bedrock Converse cross-model signed-thinking leak fix (`main`) |
| [open-telemetry/opentelemetry-python-contrib](https://github.com/open-telemetry/opentelemetry-python-contrib/pull/5003) | Fix Celery span loss on worker child pool recycle (`main`) |
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
- [**Worker Kit implementation and limits**](https://github.com/sidsri14/resilient-ai-worker-kit#readme) — Notes on the mock-provider queue prototype, local verification and non-atomic budget check.
- [**Hybrid routing experiment**](https://github.com/sidsri14/hybrid-ai-router) — Source and project notes for an independent routing prototype.
- [**Why Async SSE Streaming Collapses Reverse Proxy Connection Pools (and How to Fix It in Rust)**](articles/why-async-sse-streaming-collapses-connection-pools.md) — Deep architectural teardown on LLM token streaming, client disconnection TCP socket leaks, and backpressure handling with Tokio & Axum.
- [**20 Merged PRs Across 18 OSS Organizations: A Deep Dive into Real-World Upstream Engineering**](articles/20-merged-prs-across-18-oss-orgs.md) — Detailed catalog of root causes, fixes, and lessons from Datadog, Tailscale, Sentry, OpenTelemetry, Temporal, and Grafana.
- [**Silent Cache Poisoning in LLM Streaming Proxies**](https://sidsri14.github.io/articles/silent-cache-poisoning-llm-proxies.html) — How transient upstream stream truncation corrupts exact/semantic caches on HTTP 200, and how to enforce completion invariants.

[Browse current upstream pull-request states](https://github.com/pulls?q=is%3Apr+author%3Asidsri14).

## Technical Focus

- Rust, TypeScript, Node.js, Python, Go
- Independent Solana prototypes (Anchor, Token-2022, DEX analytics)
- Async services, HTTP/SSE streaming, API design, testing, debugging
- PostgreSQL, Redis / BullMQ, Docker, Prometheus, Linux, GitHub Actions
- LLM gateway patterns, semantic caching, failover, and observability

## Contact & Consulting

- **Upwork Contracts & Project Catalog**: [Sid S. (`~01f93f1a56b9ef1b8d`)](https://www.upwork.com/freelancers/~01f93f1a56b9ef1b8d)
- Email: `sidsri1502@gmail.com`
- X: [@SidSri0228](https://x.com/SidSri0228)
- LinkedIn: [siddharth-srivastava](https://www.linkedin.com/in/siddharth-srivastava-529a21277/)
- Arc / Codementor: [arc.dev/@sidsri929666](https://arc.dev/@sidsri929666?preview=1)

