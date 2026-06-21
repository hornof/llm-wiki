---
title: "0xCodez (3rd substantive surface) — 'How to master Dynamic Workflows in Claude Code: 6 patterns and 14 steps Anthropic engineers actually use' — 3 failure modes (agentic-laziness + self-preferential-bias + goal-drift) + 3 core API functions (agent + parallel + pipeline) + 6 canonical-patterns (2026-06-21)"
type: source
medium: twitter-thread
url: https://x.com/0xCodez/status/2062127385923776831
ingested: 2026-06-21
---

## Summary

**0xCodez (Lev Deviatkin; @0xCodez)** publishes (2026-06-03 original; cross-device-clipped 2026-06-21; saved as `_raw/How to master Dynamic Workflows in Claude Code 6 patterns and 14 steps Anthropic engineers actually.md`) **"How to master Dynamic Workflows in Claude Code: 6 patterns and 14 steps Anthropic engineers actually use"** — **STRUCTURALLY MAJOR canonical Dynamic-Workflows guide**. **3rd substantive 0xCodez surface** (extends [[0xcodez-fable-5-14-step-self-improving-agent-2026-06-11|Jun 11 Fable 5]] + [[0xcodez-14-step-loop-engineering-roadmap-2026-06-20|Jun 20 14-step Loop-Engineering-roadmap]]) = **canonical entity-page now confirmed past 2-surface threshold + 3-surface canonical-voice-tier**. **First wiki-captured Dynamic Workflows shipped May 28, 2026 canonical-launch-date anchor**. **First wiki-captured "9 out of 10 builders haven't tried Dynamic Workflows even once" canonical-anchor**. **First wiki-captured 3 canonical-failure-modes Dynamic-Workflows-solve articulation**: **agentic-laziness + self-preferential-bias + goal-drift** ("named directly in the Anthropic launch writing"). **First wiki-captured 3 canonical-core-API functions for Dynamic Workflows**: `agent()` + `parallel()` (barrier) + `pipeline()` (streaming). **First wiki-captured 6 canonical-patterns Anthropic engineers actually use for canonical-applications**: migrations + research + sorting + root-cause + triage + evals. **First wiki-captured "A workflow is a harness Claude writes" canonical-Dynamic-Workflows canonical-definition**. **First wiki-captured "per-agent isolation + per-agent model choice + per-agent isolation level (worktree/remote)" canonical-3-isolation-dimensions articulation**. **First wiki-captured "ultracode" canonical-trigger-word for Dynamic Workflows + interrupted-session canonical-resume capability**. Pairs structurally with [[anthropic-dynamic-workflows-primary-2026-05-28|Anthropic Dynamic Workflows primary canonical-source]] + [[movez-kimi-opus-300-agent-self-improving-loop-2026-06-18|0xMovez canonical-playbook]] + [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|McDonald verifier-discipline-first canonical-corrective]] at the **canonical Dynamic-Workflows + Loop-Engineering canonical-cluster** layer.

## Key Claims / Takeaways

### Canonical-launch + canonical-status anchors

- **Dynamic Workflows shipped**: **May 28, 2026** in Claude Code
- **Adoption-anchor**: *"9 out of 10 builders haven't tried Dynamic Workflows even once, even though they shipped two weeks ago"*
- **Application-canonical-anchor**: *"They write 50 prompts when one workflow would do"*

**First wiki-captured Dynamic Workflows shipped May 28, 2026 canonical-launch-date anchor** (confirms [[anthropic-dynamic-workflows-primary-2026-05-28|prior anthropic-dynamic-workflows-primary-2026-05-28 source canonical-date]]). **First wiki-captured "9 out of 10 builders haven't tried Dynamic Workflows even once" canonical-adoption-gap anchor**.

### "A workflow is a harness Claude writes" canonical-definition

> *"The default Claude Code harness has Claude plan and execute in the same context window. For most coding work, this is great. For long-running, parallel, or adversarial work, it breaks down."*
>
> *"A Dynamic Workflow is **Claude writing its own custom harness for the task** — a JavaScript file with a few special functions that spawn and coordinate subagents, plus standard JavaScript (Math, JSON, Array) to process the data flowing between them."*

**First wiki-captured "A workflow is a harness Claude writes" canonical-Dynamic-Workflows canonical-definition**. **First wiki-captured "JavaScript file with special functions + standard JavaScript" canonical-Dynamic-Workflows canonical-technical-articulation**.

### 3 canonical-failure-modes Dynamic-Workflows-solve

> *"To know when a workflow is the right tool, you have to know what it fixes. The longer Claude works on a complex task in a single context window, the more it becomes susceptible to three specific failure modes — named directly in the Anthropic launch writing"*

| Failure mode | Canonical-articulation |
|---|---|
| **Agentic laziness** | *"Claude stops before finishing a complex, multi-part task and declares done after partial progress. Addresses 20 of the 50 items in a security review and calls the rest 'handled.'"* |
| **Self-preferential bias** | *"Claude prefers its own results when asked to verify or judge them against a rubric. A verifier with skin in the game can't be a fair verifier."* |
| **Goal drift** | *"The gradual loss of fidelity to the original objective across many turns, especially after compaction. Each summarization step is lossy. 'Don't do X' constraints quietly disappear at turn 47."* |

**First wiki-captured 3 canonical-failure-modes Dynamic-Workflows-solve articulation** (agentic-laziness + self-preferential-bias + goal-drift). **First wiki-captured "named directly in the Anthropic launch writing" canonical-attribution**. **First wiki-captured "A verifier with skin in the game can't be a fair verifier" canonical-self-preferential-bias canonical-articulation** — pairs structurally with [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15|McDonald "an agent grading its own homework grades generously"]] + [[zodchii-builder-checker-looping-team-2026-06-16|Zodchii blind-reviewer canonical-discipline]] + [[anatolikopadze-loops-explained-2nd-surface-2026-06-21|AnatoliKopadze "the model that did the work is far too generous a grader"]] at the **canonical-verifier-conflict-of-interest canonical-cluster** layer (4-voice convergence).

**First wiki-captured "agentic laziness" canonical-failure-mode framing**. **First wiki-captured "goal drift" + "'Don't do X' constraints quietly disappear at turn 47" canonical-compaction-loss canonical-failure-mode framing**.

### Static vs Dynamic workflows canonical-distinction

- **Static workflows**: *"generic: written once to handle every edge case. They work, but they have to be conservative."*
- **Dynamic Workflows**: *"Claude writes this workflow for this task. The harness is tailor-made."*

**First wiki-captured Static-vs-Dynamic workflows canonical-distinction**. **First wiki-captured "the harness is tailor-made" canonical-Dynamic-Workflows canonical-positioning**.

> *"The reason the dynamic version wins isn't the search step — both can search. It's that the workflow gets to **shape itself around your context**."*

**First wiki-captured "shape itself around your context" canonical-Dynamic-Workflows canonical-positioning**.

### 3 canonical-core-API functions

> *"Three functions do most of the work in a workflow. Knowing them is enough to read any workflow Claude writes for you and to nudge Claude when you want a specific shape."*

| Function | Canonical-behavior |
|---|---|
| **`agent()`** | spawn a subagent |
| **`parallel()`** | **barrier**: fans out, then waits for everything before returning |
| **`pipeline()`** | **streaming**: each item flows through every stage independently |

> *"Pick by the question: do I need all results before I can do anything next? Yes → parallel. No → pipeline (cheaper, faster overall)."*

**First wiki-captured 3 canonical-core-API functions for Dynamic Workflows** (`agent()` + `parallel()` + `pipeline()`). **First wiki-captured parallel-as-barrier + pipeline-as-streaming canonical-distinction articulation**. **First wiki-captured "pick by the question: do I need all results before doing anything next?" canonical-decision-rule articulation**.

### 6 canonical-patterns Anthropic engineers actually use

Per 0xCodez canonical-articulation: **6 canonical-patterns Anthropic-engineers-actually-use** for canonical-applications:

1. **Classify-and-act** — Route the work before doing it. *"A classifier agent decides on the type of task, then the workflow routes to different agents or behaviors based on the answer."* Canonical-example: *"'Explain how the auth module works.' A classifier subagent reads the codebase first, estimates complexity, then routes the actual explanation task to Sonnet for a 10-file module or Opus for a 100-file one."*
2. **Fan-out-and-synthesize** — Split a task into many smaller steps. Run an agent on each step in parallel. Synthesize the results into one answer.
3. **migrations** (verification-pending specific canonical-pattern-articulation)
4. **research** (verification-pending)
5. **root-cause** (verification-pending)
6. **triage** + **evals** (verification-pending specific canonical-pattern-articulations)

**First wiki-captured 6 canonical-patterns Anthropic engineers actually use for canonical-applications** (migrations + research + sorting + root-cause + triage + evals). **First wiki-captured "classify-and-act" canonical-Dynamic-Workflow-pattern** + **first wiki-captured "fan-out-and-synthesize" canonical-Dynamic-Workflow-pattern**. **First wiki-captured "classifier-on-cheap, then route to Opus only when needed" canonical-cost-efficiency-pattern**.

### Per-agent canonical-3-isolation-dimensions articulation

> *"Three things this gives you that the default harness cannot:"*

| Dimension | Canonical-articulation |
|---|---|
| **Per-agent isolation** | *"Each subagent gets its own context window with one focused goal. No cross-contamination."* |
| **Per-agent model choice** | *"The workflow picks which model each subagent uses — Opus for hard reasoning, Haiku for cheap exploration, Sonnet for the middle."* |
| **Per-agent isolation level** | *"Worktree (isolated git checkout) or remote (no checkout). The workflow decides what each agent needs."* |

**First wiki-captured "per-agent isolation + per-agent model choice + per-agent isolation level (worktree/remote)" canonical-3-isolation-dimensions articulation**. **First wiki-captured "Opus for hard reasoning + Haiku for cheap exploration + Sonnet for the middle" canonical-model-routing canonical-allocation**.

### Canonical-trigger + canonical-resume capability

> *"Start one by either asking Claude directly ('make a workflow that...') or with the trigger word **ultracode**. If a workflow is interrupted — user action, terminal quit — resuming the session picks up where it left off."*

**First wiki-captured "ultracode" canonical-trigger-word for Dynamic Workflows**. **First wiki-captured "interrupted-session canonical-resume capability" canonical-Dynamic-Workflows feature**.

### Cross-cutting framings

- **3rd substantive 0xCodez surface** = canonical entity-page confirmed past 2-surface threshold + 3-surface canonical-voice-tier
- **First wiki-captured Dynamic Workflows shipped May 28, 2026 canonical-launch-date anchor**
- **First wiki-captured "9 out of 10 builders haven't tried Dynamic Workflows even once" canonical-adoption-gap anchor**
- **First wiki-captured "A workflow is a harness Claude writes" canonical-Dynamic-Workflows canonical-definition**
- **First wiki-captured 3 canonical-failure-modes Dynamic-Workflows-solve articulation** (agentic-laziness + self-preferential-bias + goal-drift)
- **First wiki-captured "named directly in the Anthropic launch writing" canonical-attribution**
- **First wiki-captured "A verifier with skin in the game can't be a fair verifier" canonical-articulation** — pairs in **4-voice canonical-verifier-conflict-of-interest canonical-cluster** (McDonald + Zodchii + AnatoliKopadze + 0xCodez)
- **First wiki-captured "agentic laziness" canonical-failure-mode framing**
- **First wiki-captured "goal drift" + "'Don't do X' constraints quietly disappear at turn 47" canonical-compaction-loss canonical-failure-mode framing**
- **First wiki-captured Static-vs-Dynamic workflows canonical-distinction**
- **First wiki-captured "shape itself around your context" canonical-Dynamic-Workflows canonical-positioning**
- **First wiki-captured 3 canonical-core-API functions for Dynamic Workflows** (`agent()` + `parallel()` + `pipeline()`)
- **First wiki-captured parallel-as-barrier + pipeline-as-streaming canonical-distinction articulation**
- **First wiki-captured 6 canonical-patterns Anthropic engineers actually use** (migrations + research + sorting + root-cause + triage + evals)
- **First wiki-captured "classify-and-act" + "fan-out-and-synthesize" canonical-Dynamic-Workflow-patterns**
- **First wiki-captured "per-agent isolation + per-agent model choice + per-agent isolation level" canonical-3-isolation-dimensions articulation**
- **First wiki-captured "Opus for hard reasoning + Haiku for cheap exploration + Sonnet for the middle" canonical-model-routing canonical-allocation**
- **First wiki-captured "ultracode" canonical-trigger-word for Dynamic Workflows**
- **First wiki-captured "interrupted-session canonical-resume capability" canonical-Dynamic-Workflows feature**

## Pages Updated

- [[0xcodez]] / [[lev-deviatkin]] — **3rd substantive surface added** (canonical entity-page now confirmed past 2-surface threshold + 3-surface canonical-voice-tier; pattern-watch escalation for next lint)
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — paired May 28 canonical-launch-date anchor
- [[claude-code]] — Dynamic Workflows + 3 canonical-core-API + 6 canonical-patterns + ultracode canonical-trigger-word
- [[concepts/loop-engineering]] — Dynamic Workflows as canonical-substrate; 3 canonical-failure-modes + 6 canonical-patterns + canonical-Static-vs-Dynamic distinction
- [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15]] — paired 4-voice canonical-verifier-conflict-of-interest canonical-cluster
- [[zodchii-builder-checker-looping-team-2026-06-16]] — paired 4-voice canonical-verifier-conflict-of-interest canonical-cluster
- [[anatolikopadze-loops-explained-2nd-surface-2026-06-21]] — paired 4-voice canonical-verifier-conflict-of-interest canonical-cluster
- [[movez-kimi-opus-300-agent-self-improving-loop-2026-06-18]] — paired canonical-spec-template canonical-discipline cluster
- [[claude-opus-4-8]] / [[claude-haiku-4-5]] / [[claude-sonnet]] — paired canonical-Opus-Haiku-Sonnet canonical-model-routing canonical-allocation
- [[concepts/agentic-engineering]] — 3 canonical-failure-modes + canonical-Dynamic-Workflows canonical-substrate

## Adjacent sources

- [[0xcodez-14-step-loop-engineering-roadmap-2026-06-20]] — paired 0xCodez 2nd substantive surface (Jun 20 14-step Loop Engineering roadmap)
- [[0xcodez-fable-5-14-step-self-improving-agent-2026-06-11]] — paired 0xCodez 1st substantive surface (Jun 11 Fable 5 14-step)
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — paired Anthropic May 28 canonical-primary
- [[anatolikopadze-loops-explained-2nd-surface-2026-06-21]] — paired Jun 21 2-voice canonical-Loop-Engineering cluster
- [[samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15]] — McDonald verifier-discipline-first canonical-corrective
- [[zodchii-builder-checker-looping-team-2026-06-16]] — Zodchii looping-team
- [[movez-kimi-opus-300-agent-self-improving-loop-2026-06-18]] — 0xMovez canonical-playbook
- [[sydney-runkle-langchain-4-layer-loop-engineering-2026-06-17]] — Sydney Runkle LangChain 4-layer
- [[claude-opus-4-8-dynamic-workflows-2026-05-28]] — paired canonical-Opus-4.8 + Dynamic-Workflows canonical-anchor

## Verification-pending

- Specific remaining canonical-pattern articulations (migrations + research + sorting + root-cause + triage + evals) — only classify-and-act + fan-out-and-synthesize captured in this canonical-surface
- Specific full 14-step Dynamic-Workflows canonical-roadmap articulation
- Specific Anthropic launch-writing canonical-citation for 3 canonical-failure-modes
- Specific Dynamic-Workflows canonical-availability-tier (Claude Team + Enterprise? Or Claude Code Pro?)
- Specific "ultracode" canonical-trigger-word activation context
- Specific Dynamic-Workflows canonical-resume-from-interruption canonical-implementation
