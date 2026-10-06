# Siddharth Srivastava (`@sidsri14`)

**Systems & LLM Infrastructure Engineer** building low-latency Rust proxies, deterministic AI gateway controls, and reliable TypeScript backends. Creator of **[StackIntercept](https://github.com/sidsri14/stack-intercept)**.

Based in Lucknow, India · **Open to remote full-time & high-impact contract roles worldwide** (US/EU/APAC async-friendly).

[Portfolio](https://sidsri14.github.io/career-command-center) · [LinkedIn](https://www.linkedin.com/in/siddharth-srivastava-529a21277/) · [GitHub](https://github.com/sidsri14) · [StackIntercept](https://stackintercept.com) · [Email](mailto:sidsri1502@gmail.com)

---

## 🏆 Standout Project: StackIntercept

**[StackIntercept](https://github.com/sidsri14/stack-intercept)** is an ultra-low-latency, self-hosted streaming reverse proxy for OpenAI-compatible LLM inference APIs, engineered in Rust on Tokio and Hyper.

- **Sub-Millisecond Overhead**: Delivers `<0.8ms p99` latency on streaming Server-Sent Events (SSE) token pass-through.
- **Cost & Latency Reduction**: Exact-match & SIMD-accelerated semantic caching prevents redundant upstream GPU token billing.
- **High Availability**: Single-hop reactive upstream failover (switches from primary to fallback provider in `<5ms` upon HTTP 5xx or rate limit).
- **Client Disconnect Protection**: Detects aborted client connections instantly to cancel upstream GPU generation, stopping phantom billing loops.
- **Production Observability**: Built-in Prometheus metrics (`inference_latency_seconds`, `cache_hit_ratio`, `token_throughput_total`), Docker Compose profile, and mock-upstream integration test suite.

---

## 🛡️ Enterprise Open-Source Contributions (Merged Upstream)

Verifiable evidence of production code contributions merged into high-visibility security and developer infrastructure codebases:

| Organization / Repository | Pull Request | Impact & Technical Delivery |
| :--- | :--- | :--- |
| **DataDog** / `guarddog` | [#827](https://github.com/DataDog/guarddog/pull/827) | Implemented Rust/crates.io support for supply-chain malware scanning (467 tests passing) |
| **Tailscale** / `hujson` | [#48](https://github.com/tailscale/hujson/pull/48) | Hardened parser by rejecting ambiguous Unicode line separators in comments |
| **Sentry** / `tacos-gha` | [#319](https://github.com/getsentry/tacos-gha/pull/319) | Resolved deletion-path `KeyError` in CI workflows with strict typing and regression proof |
| **OpenTelemetry** / `opentelemetry-python` | [#5545](https://github.com/open-telemetry/opentelemetry-python/pull/5545) | Bound resource-detector waits to configured timeout, preventing process hang |
| **Nushell** / `nushell` | [#18976](https://github.com/nushell/nushell/pull/18976) | Fixed error-stream propagation across `length`, `columns`, and `is-empty` pipeline commands |
| **Temporal** / `sdk-typescript` | [#2249](https://github.com/temporalio/sdk-typescript/pull/2249) | Preserved zero-value optional duration parameters in workflow dispatch |
| **Grafana** / `gcx` | [#1066](https://github.com/grafana/gcx/pull/1066) | Allowed environment credentials to safely override failed OS keychain lookups |

*Active contributor across AI infrastructure tooling including [LiteLLM](https://github.com/BerriAI/litellm).*

---

## ⚡ Additional Selected Systems

### [Tempo Z-Spend](https://github.com/sidsri14/tempo-zspend) — Autonomous Agent Spend Rails
Deterministic risk containment middleware for autonomous AI agents. Combines a fail-closed local policy engine with rolling epoch budget caps and HTTP 402 / x402 micropayments (verified across EVM, Solana, Celo, and Arbitrum Stylus).

### [Solana Stealth Shield](https://github.com/sidsri14/solana-stealth-shield) — Low-Level Privacy Infrastructure
Zero-knowledge stealth transaction coordinator and ephemeral key isolation on high-throughput blockchain networks.

---

## 🛠️ Core Engineering Stack

- **Systems & Languages**: Rust (`tokio`, `hyper`, `axum`), TypeScript, Node.js, Python, Go.
- **AI & LLM Infrastructure**: OpenAI API, Anthropic, LiteLLM, vLLM, Ollama, SSE Streaming, Prompt Caching, MCP (Model Context Protocol).
- **Backend & Data**: PostgreSQL, Redis, Docker, Prometheus, Grafana, GitHub Actions, Linux.

---

## 📬 Contact & Availability

- **Status**: Available for **remote full-time roles**, **advisory engagements**, and **AI infrastructure / backend reliability contracts**.
- **Email**: `sidsri1502@gmail.com`
- **X / Twitter**: [@SidSri0228](https://x.com/SidSri0228)
- **LinkedIn**: [siddharth-srivastava](https://www.linkedin.com/in/siddharth-srivastava-529a21277/)
