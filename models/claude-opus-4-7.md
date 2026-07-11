---
name: Claude Opus 4.7
type: model
provider: Anthropic
status: available
last_updated: 2026-07-10
---

> [!note] Lint refresh — 2026-07-10 (superseded as default, but still Active)
> Reviewed during the 2026-07-10 lint against Anthropic's primary [model-deprecations page](https://platform.claude.com/docs/en/about-claude/model-deprecations):
> - **`claude-opus-4-7` is listed "Active"** — *not* deprecated or retired. Tentative retirement is **"not sooner than 2027-04-16."** No migration mandate exists for 4.7 (unlike `claude-opus-4-1`, retiring 2026-08-05, and `claude-opus-4`/`claude-sonnet-4`, retired 2026-06-15).
> - **Superseded as the default model** by [[claude-opus-4-8]] (launched **2026-05-28**, same price, adds Claude Code dynamic workflows) — see [[claude-sonnet-5-launch-2026-06-30|the broader Claude 5 / Opus 4.8 cluster]]. 4.7 remains available via API for pinned workloads.
> - **Migration gotcha**: `temperature` / `top_p` / `top_k` are deprecated **from Opus 4.7 onward** — non-default values return a 400 error (also true on Opus 4.8 and Claude Sonnet 5).
> - *(A secondary report of a 4.7 "fast mode" deprecation on 2026-07-24 could not be confirmed against Anthropic primary docs — left out pending verification.)*

## What It Is

Claude Opus 4.7 is the April 2026 Opus refresh from [[anthropic]] — generally available since **April 16, 2026** via Claude API, Amazon Bedrock, Google Cloud Vertex AI, and Microsoft Foundry under the model identifier `claude-opus-4-7` ([[anthropic-opus-4-7-launch-2026-04-16]]). Successor to Opus 4.6 at the same pricing ($5 / million input, $25 / million output) with material gains on the most difficult software-engineering tasks, document reasoning, and long-running execution. Headlined separately at Code w/ Claude 2026 on May 6 alongside the [[claude-design]] integration — the visual design capability previously a partially-documented surface inside Claude.ai now ships native to Opus 4.7 itself ([[willison-code-w-claude-2026]]).

Sits alongside [[claude-mythos]] (Anthropic's preview line, used in Mozilla's Firefox security partnership and Anthropic's NLA research) — Mythos is *not* a successor to Opus 4.7; positioning between the two has not yet been publicly clarified by Anthropic.

## Strengths & Weaknesses

### Benchmark deltas vs. Opus 4.6 (Anthropic-published, [[anthropic-opus-4-7-launch-2026-04-16]])
- **3× more production tasks completed** on Rakuten-SWE-Bench
- **70% (vs. Opus 4.6 at 58%)** on CursorBench
- **+13%** on a 93-task internal coding benchmark
- **21% fewer errors** on document reasoning
- "Particular gains on the most difficult tasks" — i.e., performance gap widens at the high end of difficulty, not just on average

### Vision and multimodal
- Long-edge image support up to **2,576 pixels (~3.75 megapixels)** — substantially larger than prior Opus generations
- Better instruction following and multimodal understanding (no specific deltas published)

### Developer-facing primitives (new in 4.7)
- **`xhigh` effort level** — extends the reasoning-effort ladder above prior `high`; gives developers finer-grained latency/quality control. Exact envelope vs. `high` not yet published.
- **Task budgets (public beta)** — first-class per-task token-budget enforcement at the model runtime. Notable because the same discipline is the central rule of community-evolved CLAUDE.md templates (Rule 6 of [[mnilax-claude-md-12-rules-2026-05-09]] enforces per-task 4K / per-session 30K caps via prompting). What developers were enforcing in CLAUDE.md is now becoming a native model feature.
- **`/ultrareview` slash command** — explicit code-review primitive in Claude Code. Sibling rather than overlap with the Code w/ Claude 2026 **Code Review** subsystem (cross-team automated review at the org level); `/ultrareview` operates at the per-invocation scope.

### Caveats
- All benchmark numbers are Anthropic-published. Independent verification (LMSYS leaderboards, third-party SWE-Bench replications, etc.) not yet captured here.
- "Rakuten-SWE-Bench" and "CursorBench" provenance — whether standard SWE-Bench applied to specific codebases or vendor-specific variants — not detailed. Verify methodology before quoting numbers externally.

## When to Use It

- **Visual + design-heavy work**: explicit positioning makes Opus 4.7 the default Anthropic choice for end-to-end design + code workflows previously tackled with Claude Design + Opus 4.6 in tandem.
- **Long-running multi-step tasks**: explicit consistency improvements and the new task-budget primitive make 4.7 the better fit for agentic / [[claude-cowork]] workflows where 4.6 would drift.
- **Highest-difficulty SWE tasks**: the largest gap vs. 4.6 sits at the difficult end of the distribution, not on standard tasks; Opus 4.7 earns its premium most clearly on hard code-modification work.
- **Drop-in upgrade path**: same pricing as Opus 4.6, same surfaces. Default model in Claude Code as of May 2026.

## Community Sentiment

- **April 16, 2026 GA**; widely surfaced by Anthropic at Code w/ Claude 2026 (May 6) — three-week gap between GA and event coverage suggests the model launched quietly into the developer surface and was repositioned for general announcement at the event.
- Karpathy's "jagged intelligence" framing names Opus 4.7 specifically: *"How is it possible that state-of-the-art Opus 4.7 will simultaneously refactor a 100,000 line codebase or find zero day vulnerabilities and yet tells me to walk to this car wash?"* — [[karpathy-vibe-coding-agentic-engineering]]. Opus 4.7 is the highest-frontier reference point in Karpathy's May 2026 vocabulary.
- May 10 daily-brief framing characterized the announcement as "standard capability claims without benchmarks or technical substance" — contradicted by the actual blog content. Track for whether broader practitioner reception aligns with brief or with blog.

## Resources

- [[anthropic-opus-4-7-launch-2026-04-16]] — Anthropic's official launch announcement (April 16 2026)
- [[willison-code-w-claude-2026]] — Code w/ Claude 2026 event coverage; broader May 2026 product cluster
- [[claude-design]] — visual design capability, native to Opus 4.7
- [[claude-mythos]] — preview-line sibling
- [[mnilax-claude-md-12-rules-2026-05-09]] — community CLAUDE.md rule for token budgets, now mirrored as a native runtime feature
- [[karpathy-vibe-coding-agentic-engineering]] — Karpathy's "jagged intelligence" framing names Opus 4.7 by version
