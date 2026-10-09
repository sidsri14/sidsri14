# What I Learned Merging 20 Pull Requests Across 18 Open-Source Organizations

*Siddharth Srivastava · October 2026*

---

Over the past year, I've had pull requests merged into projects maintained by **Grafana, Sentry, Tailscale, OpenTelemetry, Microsoft, Google, Temporal, Nushell, Coder, Boeing, ClickHouse, Rancher, Anchore, PostHog, CycloneDX, Inngest, MedusaJS**, and more. These weren't speculative drive-by typo fixes — they touched test infrastructure, configuration validators, data pipelines, CLI tools, and SDK internals.

Here's what the experience actually taught me.

---

## The Portfolio

| # | Organization | Repository | Contribution Area |
|---|---|---|---|
| 1 | **Grafana Labs** | [alloy](https://github.com/grafana/alloy) | Observability pipeline components |
| 2 | **Grafana Labs** | [clickhouse-datasource](https://github.com/grafana/clickhouse-datasource) | ClickHouse plugin fixes |
| 3 | **Grafana Labs** | [faro-web-sdk](https://github.com/grafana/faro-web-sdk) | Browser telemetry SDK |
| 4 | **Grafana Labs** | [scenes](https://github.com/grafana/scenes) | Dashboard framework |
| 5 | **Grafana Labs** | [gcx](https://github.com/grafana/gcx) | Internal tooling |
| 6 | **Sentry** | [json-schema-diff](https://github.com/getsentry/json-schema-diff) | Schema comparison engine |
| 7 | **Sentry** | [sentry-rust](https://github.com/getsentry/sentry-rust) | Rust SDK |
| 8 | **Sentry** | [sentry-infra-tools](https://github.com/getsentry/sentry-infra-tools) | Infrastructure tooling |
| 9 | **Sentry** | [sentry-toolbar](https://github.com/getsentry/sentry-toolbar) | Browser toolbar extension |
| 10 | **Sentry** | [tacos-gha](https://github.com/getsentry/tacos-gha) | GitHub Actions workflows |
| 11 | **Tailscale** | [hujson](https://github.com/tailscale/hujson) | Human JSON parser |
| 12 | **Tailscale** | [terraform-provider-tailscale](https://github.com/tailscale/terraform-provider-tailscale) | Terraform provider |
| 13 | **OpenTelemetry** | [opentelemetry-python](https://github.com/open-telemetry/opentelemetry-python) | Python SDK core |
| 14 | **OpenTelemetry** | [opentelemetry-python-contrib](https://github.com/open-telemetry/opentelemetry-python-contrib) | Python instrumentation |
| 15 | **OpenTelemetry** | [opentelemetry-go-contrib](https://github.com/open-telemetry/opentelemetry-go-contrib) | Go instrumentation |
| 16 | **Temporal** | [sdk-typescript](https://github.com/temporalio/sdk-typescript) | TypeScript workflow SDK |
| 17 | **Microsoft** | [vscode-js-debug](https://github.com/microsoft/vscode-js-debug) | VS Code debugger |
| 18 | **Google** | [yamlfmt](https://github.com/google/yamlfmt) | YAML formatter |
| 19 | **Boeing** | [config-file-validator](https://github.com/Boeing/config-file-validator) | Multi-format config validator |
| 20 | **Nushell** | [nushell](https://github.com/nushell/nushell) | Modern shell (Rust) |

Plus contributions to: Coder, ClickHouse, Rancher/k3k, Anchore/syft, PostHog, CycloneDX, Inngest, MedusaJS, Scalar, and more.

---

## Lesson 1: The README Is Lying to You

Every contributor guide says "we welcome contributions!" Most don't mean it for your type of contribution.

The actual signal that a project accepts outside PRs:
- **Recent merge history from non-maintainers.** If the last 50 merged PRs are all from people with the org badge, don't bother.
- **Issue triage cadence.** If `good-first-issue` labels are stale by 6+ months, the project has contributor-facing docs but no contributor-facing process.
- **CI must be green on main.** If the default branch CI is broken, your PR will rot in review purgatory because maintainers can't verify it cleanly.

I learned this the hard way with three repos where I wrote solid patches that sat unreviewed for weeks because the maintainer had moved on but the project was still accepting stars.

---

## Lesson 2: The Best First PR Is a Test Fix, Not a Feature

Every first-time contributor wants to add a feature. Don't.

My highest acceptance rate came from:
1. **Fixing a flaky test** — maintainers hate flaky CI. If you can identify *why* a test is flaky (race condition, time-dependent assertion, missing mock) and fix it, you're immediately trusted.
2. **Fixing a build/lint warning** — Clippy lints in Rust repos, ESLint warnings in JS repos. These are small but they demonstrate you can run the full toolchain.
3. **Correcting documentation that contradicts code** — Find a function where the docstring says one thing and the implementation does another. Fix the docs (after verifying which is correct).

Feature PRs from unknown contributors get scrutinized 10x more. Test fixes get merged in hours.

---

## Lesson 3: Cross-Org Patterns Repeat

After touching 18 different codebases, I noticed the same architectural patterns and the same mistakes everywhere:

**Pattern: Every Go project eventually reinvents configuration parsing.** I contributed to Boeing's config-file-validator, Tailscale's hujson, and Google's yamlfmt. Three different orgs, three different takes on "how do we parse config files safely." The YAML/JSON/TOML parsing ecosystem is fragmented and every team builds their own validation layer.

**Pattern: Observability SDKs all have the same batching bug.** Both OpenTelemetry Python and Grafana's Faro SDK had edge cases around batch export — what happens when the process exits before the batch flushes? The answer is usually "data loss" and the fix is usually "add a shutdown hook with a bounded timeout." I saw this three times.

**Pattern: Terraform providers are undertested.** Tailscale's Terraform provider, like most, had gaps in acceptance tests because real API calls are expensive. The maintainers appreciated any test that could exercise logic without hitting their production API.

---

## Lesson 4: Rust Projects Are the Most Welcoming

Counterintuitive finding: Rust projects (Nushell, Sentry-Rust, eza, ripgrep, fd, tealdeer) had the fastest review cycles and most constructive feedback.

My theory: the Rust compiler is so strict that if your PR compiles, passes `clippy --deny warnings`, and passes the existing test suite, there's very little for a reviewer to argue about. The type system does 80% of the code review.

Compare this to Python and JavaScript projects where reviews often devolve into style debates because the language doesn't enforce enough structure.

---

## Lesson 5: Your PR Description Matters More Than Your Code

The PRs that got merged fastest all had:
1. **A one-sentence summary of *why*** — not what, not how, but why this change matters
2. **A reproduction case or failing test** — before/after evidence
3. **Explicit scope limitation** — "This PR does X. It deliberately does not do Y because [reason]."

The PRs that rotted had beautiful code but said "fixes #123" with no context.

---

## Lesson 6: The Job Market Signal

Here's the part nobody talks about: **merged PRs are the best job application material that exists.**

When you apply to Grafana and say "I've merged PRs into alloy, clickhouse-datasource, faro-web-sdk, scenes, and gcx," you skip the "can this person code?" question entirely. You've already passed their CI, their linters, their review process, and their coding standards — on five separate repos.

I haven't fully capitalized on this yet (honestly — that's what this article is about realizing), but the signal is there. If you're job hunting, contributing to the specific company's OSS repos is orders of magnitude more effective than LeetCode grinding.

---

## The Numbers

- **Organizations touched**: 18+
- **Pull requests merged**: 20+
- **Languages**: Rust, Go, Python, TypeScript, YAML
- **Average review turnaround**: 2-7 days (Rust fastest, Python slowest)
- **Longest review cycle**: 3 weeks (a Python SDK change that required CODEOWNER approval across time zones)
- **Fastest merge**: 4 hours (a Clippy lint fix in a Rust project)

---

## What I'd Do Differently

1. **Focus on 3-4 orgs max.** I spread across 18 orgs which looks impressive as a list but means no single maintainer remembers my name. If I'd done 5 PRs each to Grafana, Sentry, and OpenTelemetry, I'd have relationship equity.

2. **Write about it sooner.** These contributions happened over months. This article should have been written after the 5th merge, not the 20th.

3. **Ask for feedback on rejected PRs.** I had a few PRs that went stale. Instead of abandoning them, I should have asked "is this direction worth pursuing or should I close this?"

4. **Ship my own project first.** Contributing to other people's projects is valuable, but I spent time I could have used making [StackIntercept](https://github.com/sidsri14/stack-intercept) production-ready and getting real users.

---

*Siddharth Srivastava builds [StackIntercept](https://stackintercept.com), a high-performance LLM proxy in Rust with semantic caching and reactive failover. He's looking for Rust/infrastructure roles — reach out at sidsri1502@gmail.com or [@SidSri0228](https://twitter.com/SidSri0228).*

*Find him on [GitHub](https://github.com/sidsri14).*
