---
name: Bun
type: tool
category: framework
status: gaining-traction
last_updated: 2026-06-05
---

## What It Is

Bun is an all-in-one JavaScript runtime + toolkit (runtime, bundler, transpiler, package manager, test runner) led by **Jarred Sumner**. Originally written in **Zig**. As of May 2026, Bun has been **ported to Rust using [[anthropic-dynamic-workflows-primary-2026-05-28|Anthropic's Dynamic Workflows]]** — the rewrite is the named launch case study for the Dynamic Workflows orchestration primitive in [[claude-code|Claude Code]].

First wiki appearance: 2026-05-28 via the Dynamic Workflows launch primary.

## Traction Signals

- **Bun Zig→Rust port via Anthropic Dynamic Workflows (2026-05-28)** — Anthropic's primary on Dynamic Workflows names Sumner's Bun rewrite as the load-bearing operational case study:
  - **99.8% of existing test suite passing**
  - **~750,000 lines of Rust**
  - **11 days from first commit to merge**
  - **Workflow shape**: lifetime-mapping workflow → per-file behavior-identical port workflow (hundreds of agents in parallel with 2 reviewers per file) → fix-loop driving build + test suite clean → overnight workflow addressing unnecessary data copies + opening PR for each
  - **Critical qualifier**: *"While not yet in production, all of this was handled by dynamic workflows."* — port is real and code is on disk; production deployment pending.
  - **Per-file dual-review parallelism pattern** named for the first time at scale: hundreds of agents with 2:1 reviewer:author ratio.

## How to Use It

Pre-rewrite Bun is a drop-in alternative to Node.js with faster startup + integrated package manager + native test runner. Post-rewrite Rust version is not yet GA. Watch for Sumner's direct write-up (Anthropic-attributed in the launch announcement; promised follow-up).

## Compared To

- **Node.js** — incumbent JavaScript runtime; Bun is positioned as the *all-in-one faster alternative*
- **Deno** — sibling alternative runtime; secure-by-default, TypeScript-native

## Resources

- [[anthropic-dynamic-workflows-primary-2026-05-28]] — Anthropic primary; Bun rewrite as launch case study
- [[claude-opus-4-8-dynamic-workflows-2026-05-28]] — same-day capability bundle (Opus 4.8 + Dynamic Workflows)
- [[trq-dynamic-workflows-harness-2026-06-02]] — Thariq Shihipar's harness post confirms Bun Zig→Rust as the named *"migrations and refactors"* canonical use case for Dynamic Workflows; links to [Jarred Sumner's X thread](https://x.com/jarredsumner/status/2060050578026189172)
- [[anthropic-dynamic-workflows-official-docs-2026-06]] — canonical Dynamic Workflows docs
- [bun.com](https://bun.com/) — official site
- [Jarred Sumner X thread on the Bun Zig→Rust migration](https://x.com/jarredsumner/status/2060050578026189172) — practitioner-side primary; cited in Thariq's harness post
