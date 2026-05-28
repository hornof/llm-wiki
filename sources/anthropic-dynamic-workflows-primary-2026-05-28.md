---
title: "Anthropic primary: Introducing Dynamic Workflows in Claude Code"
type: source
medium: article
url: https://claude.com/blog/introducing-dynamic-workflows-in-claude-code
ingested: 2026-05-28
---

## Summary

[[anthropic|Anthropic]] primary on **Dynamic Workflows in [[claude-code|Claude Code]]** (2026-05-28). Adds substantial operational detail to the same-day [[claude-opus-4-8-dynamic-workflows-2026-05-28|Digg-derived bundle capture]] that surfaced via the Daily Brief earlier today. **Headline framing**: *"Work you'd normally plan in quarters now finishes in days."* The orchestration primitive runs **tens to hundreds of parallel subagents in a single session**, with **adversarial agents working to break results before they reach the operator** + a **convergence loop** that iterates until answers stabilize. **Bun Zig→Rust port (Jarred Sumner)** is the named launch case study: **99.8% of existing test suite passing, ~750,000 lines of Rust, 11 days from first commit to merge**.

## Key Claims / Takeaways

### Scale: tens to hundreds of parallel subagents

- *"Claude dynamically writes orchestration scripts that run tens to hundreds of parallel subagents in a single session."*
- **First wiki-captured 100+-parallel-subagent claim from a frontier-lab primary surface.** Pairs with [[anthropic-spacex-higher-limits-2026-05-06|the 300+ MW / 220K-GPU Colossus 1 deal]] as the compute-floor that enables 100+-agent fan-out.
- **Coordination is "outside the conversation"** — *"because the coordination happens outside the conversation, the plan stays on track no matter how big the task gets."* This is the architectural answer to context-window scaling: the coordinator's working memory isn't constrained by the conversation context that participating sub-agents share.

### Distribution surfaces (much broader than Digg suggested)

| Surface | Status |
|---|---|
| **[[claude-code|Claude Code]] CLI** | Research preview (Max / Team / Enterprise) |
| **[[claude-desktop|Claude Desktop]]** | Research preview (Max / Team / Enterprise) |
| **VS Code extension** | Research preview (admin-enabled for Enterprise) |
| **Claude API** | Available |
| **Amazon Bedrock** | Available |
| **Google Vertex AI** | Available |
| **Microsoft Foundry** | Available |

- **Default state**: on by default for Max / Team / API; **off by default for Enterprise** (admin must enable via [Claude Code managed settings](https://code.claude.com/docs/en/settings)).
- **Broader-than-Claude-Code distribution at launch**: all four major model-deployment surfaces (Bedrock + Vertex + Foundry + Anthropic API) ship Dynamic Workflows on day one. **First wiki-captured frontier-lab same-day API/Bedrock/Vertex/Foundry distribution for a new orchestration primitive.**

### The `ultracode` setting (new Claude Code primitive)

- New Claude Code-specific setting: **`ultracode`**
- Accessible through the **effort menu**
- **Sets effort level to `xhigh`** ([[claude-opus-4-7|Opus 4.7]] introduced `xhigh` as the extended-effort level above `high`)
- Lets Claude **decide automatically when to use a workflow** to handle the task — *agent-deciding-when-to-fan-out* is the new operator-facing primitive
- **Pairs structurally with [[claude-md-pattern|CLAUDE.md pattern]]**: `ultracode` operationalizes "let Claude decide when to escalate," which CLAUDE.md (per [[mnilax-claude-md-12-rules-2026-05-09|Mnilax 12-rule expansion]]) sometimes constrains via per-task token budgets. Tension between operator-imposed budgets and agent-decided escalation worth tracking.
- **Auto-mode integration**: *"For the best experience, turn on auto mode when using dynamic workflows."* — `auto` + `ultracode` is the named full-autonomy combo at launch.

### Two entry-paths

1. **Direct invocation**: *"Ask Claude to create a dynamic workflow directly (e.g., 'Create a workflow')."*
2. **Setting-based**: switch on `ultracode` and let Claude decide.

### Three named use-case shapes

1. **Codebase-wide bug hunts, profiler-guided optimization audits, security audits** — *"Claude searches a service or repo in parallel, then runs independent verification on every finding so the report surfaces real issues. The same shape works for hardening passes: auth checks, input validation, and unsafe patterns across an entire codebase."*
2. **Large migrations and modernization** — *"Framework swaps, API deprecations, language ports that span thousands of files end-to-end."* — directly names the Bun-style port shape.
3. **Critical work needing review** — *"A workflow gives Claude independent attempts at the problem and adversarial agents working to break the result before you see it."* — first wiki-captured Anthropic-primary description of **adversarial-agent verification as a launch capability** (not a research artifact).

### The Bun Zig→Rust rewrite (Jarred Sumner)

The single case study Anthropic ships in the announcement:

- **Jarred Sumner used dynamic workflows to port [[bun|Bun]] from Zig to Rust.**
- **99.8% of existing test suite passing**
- **~750,000 lines of Rust**
- **11 days from first commit to merge**

**The workflow shape Sumner used** (load-bearing operational detail):

1. **Workflow 1**: mapped the right Rust lifetime for every struct field in the Zig codebase.
2. **Workflow 2**: wrote every `.rs` file as a behavior-identical port of its `.zig` counterpart — *"hundreds of agents working in parallel with two reviewers on each file."*
3. **Fix loop**: drove the build and test suite until both ran clean.
4. **Overnight workflow** (post-port): addressed unnecessary data copies and opened a PR for each for final review.

**Critical qualifier**: *"While not yet in production, all of this was handled by dynamic workflows."* The port is real and code is on disk; production deployment is pending. **Treat as significant-but-incomplete demonstration**, not a shipped-in-production proof.

**Pattern named**: *"hundreds of agents in parallel with two reviewers on each file"* is the first wiki-captured **per-file dual-review parallelism pattern** for a real codebase port. The 2:1 verifier:author ratio is operational structure for `n=hundreds` agent fan-out.

**Jarred will write more in the future** — primary-pending follow-up worth tracking. Until then, the operational specifics are Anthropic-attributed-to-Sumner, not Sumner-direct.

### How it works (Anthropic's architectural framing)

- *"Claude plans dynamically based on your prompt, breaks it into subtasks, and fans the work out across subagents running in parallel."*
- *"Results are checked before they're folded in."*
- *"Agents address the problem from independent angles, other agents try to refute what they found, and the run keeps iterating until the answers converge."*
- **Convergence-loop framing**: the run terminates when *"answers converge,"* not when a fixed step-count completes. This is operationally close to *"verify until stable,"* which puts adversarial verification at the center of the loop's termination condition.

### Long-running operation

- *"Built for parallel and long-running work that can extend into hours and days."*
- *"Progress is saved as the run goes, so a job that's interrupted picks up where it left off instead of starting over."*
- **First wiki-captured Anthropic-primary persistence-across-interruption claim** for an agent orchestration primitive. Pairs with [[claude-cowork|Claude Cowork's]] Scheduled Tasks and Dispatch as the long-running-agent surface.

### Token consumption warning (operationally important)

- *"Dynamic workflows can consume substantially more tokens than a typical Claude Code session."*
- *"We recommend starting on a scoped task to get a feel for usage in your work."*
- *"The first time a workflow triggers, Claude Code shows what's about to run and asks you to confirm."*
- **Operational implication**: Dynamic Workflows pricing structure is **per-subagent-token, not per-workflow-flat**. A 100-agent run at typical session cost ≈ 100× a typical session. Operator-side cost forecasting is non-trivial.
- **Direct cross-cut with [[ai-roi-gap]]**: this is the launch surface most exposed to the [[sankar-token-spend-roi-gap-2026-05-25|$100K→$18K funnel]] / [[cyb3rops-four-stages-ai-coding-hype-2026-05-26|stage-3 grind]] critiques. *"Substantially more tokens"* is the new generation of the cost variable that's already under scrutiny.

### What the brief / Digg secondary missed

The earlier [[claude-opus-4-8-dynamic-workflows-2026-05-28|Digg-derived capture]] characterized Dynamic Workflows as "orchestration primitives for multi-agent code migration at scale + self-verifying workflow patterns." Now-captured primary-source detail it didn't include:

- **Scale: 10s to 100s of parallel subagents** (vs. unspecified parallelism)
- **`ultracode` Claude Code setting** as the operator-facing knob
- **Distribution across all four surfaces** (Bedrock + Vertex + Foundry + API)
- **Bun rewrite case study** with concrete numbers (99.8% / 750K LOC / 11 days)
- **Adversarial-agent verification** as the named convergence-termination mechanism
- **Per-file dual-review parallelism pattern** (hundreds of agents + 2 reviewers per file)
- **Long-running operation with progress persistence** across interruption
- **Token-consumption warning** with explicit "substantially more" framing + first-run confirmation gate
- **Enterprise default-off** vs Max/Team default-on

### What's still verification-pending

- **Pricing structure for parallel subagents**: confirmed *"substantially more"* but not the multiplier or whether sub-agent calls are billed per-call vs per-workflow.
- **Whether `ultracode` is available on Pro** (the announcement scopes to Max / Team / Enterprise — Pro is excluded). Worth confirming.
- **Bun rewrite primary from Sumner** — Anthropic-attributed at launch; Sumner-direct write-up pending.
- **Adversarial-agent specifics**: how many adversarial agents per author-agent in non-Bun shapes; whether adversarial verification uses model-as-judge or independent verifier with separate context.
- **Workflow-as-code surface**: *"Claude dynamically writes orchestration scripts"* — the script is generated, but what language/runtime executes the script (Claude Code internal? Python? JSON spec?) is unspecified.

## Pages Updated

- [[claude-code]] — Dynamic Workflows feature added with `ultracode` setting + auto-mode integration; Bun rewrite added as a launch case study; distribution surfaces expanded
- [[claude-opus-4-8]] — Dynamic Workflows companion fleshed out with primary-source detail; cross-reference to this primary updated
- [[claude-opus-4-8-dynamic-workflows-2026-05-28]] — primary-source cross-reference added; verification-pending items resolved by this primary
- [[anthropic]] — Dynamic Workflows added under Recent Activity as primary-source distinct from the Digg-secondary entry
- [[ai-roi-gap]] — *"substantially more tokens"* warning added as the most direct exposure point to the token-spend-vs-shipped-value gap

Verification-pending: per-subagent pricing structure; whether `ultracode` is available on Pro; Sumner's direct write-up of the Bun rewrite; adversarial-agent architectural specifics; orchestration-script runtime.

## Adjacent sources

- [[claude-opus-4-8-dynamic-workflows-2026-05-28]] — same-day Digg-derived bundle capture (now superseded for Dynamic Workflows operational detail)
- [[anthropic-series-h-65b-965b-2026-05-28]] — same-day capital event; together with Dynamic Workflows + Opus 4.8 + ad-free positioning forms the four-event triple-bundle
- [[anthropic-spacex-higher-limits-2026-05-06]] — compute-floor that enables 100+-agent fan-out
- [[claude-cowork]] — long-running-agent surface sibling (Scheduled Tasks + Dispatch)
- [[code-mode]] — runtime primitive that Dynamic Workflows orchestrates above
