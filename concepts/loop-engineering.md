---
name: Loop Engineering
type: concept
maturity: emerging
last_updated: 2026-06-08
---

## Definition

**Loop Engineering** is the practitioner-content register elevated above [[trq-dynamic-workflows-harness-2026-06-02|harness-engineering]] in mid-2026 to name the discipline of **designing small programs ("loops") that prompt coding agents on the practitioner's behalf**, observe their output, decide whether the goal is met, and re-prompt until done. The model becomes the subroutine; the human becomes the author of the loop.

Coined in reply chain to [[peter-steinberger|Peter Steinberger]]'s 2026-06-07 X post (*"you shouldn't be prompting coding agents anymore. You should be designing loops that prompt your agents"*) by Gautham Pai: *"Oh god, LinkedIn will now start a new fad, 'Loop Engineering'."* — see [[steipete-loops-engineering-vision-md-2026-06-07]]. **First wiki-captured Loop Engineering coinage 2026-06-07.**

## Why It Matters

- **Job-description shift at the Anthropic-creator layer**: [[boris-cherny|Boris Cherny]] (Claude Code creator) self-describes the abstraction transition at WorkOS Acquired Unplugged (2026-06-02) — *"I don't prompt Claude anymore. I have loops that are running... My job is to write loops."* See [[mvanhorn-wtf-is-a-loop-2026-06-07]].
- **Cost-locus shift**: per [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn synthesis]]: *"the loop, not the model, is now the expensive part."* Extends [[trq-dynamic-workflows-harness-2026-06-02|Thariq's "reliability comes from the harness, not the model"]] framing from reliability-locus to cost-locus.
- **Receipts of scale**: [[bcherny-5-tips-opus-autonomous-2026-06-05|Ray Amjad's 19-hour `/goal` run verifying ~300 user flows]]; Cherny's *"259 PRs in last 30 days"* / *"100% of Claude Code contributions written by Claude Code"* / *"IDE deleted in November"*; [[anthropic-dynamic-workflows-primary-2026-05-28|Bun Zig→Rust 11-day rewrite]] (~750K LOC, hundreds of parallel agents).

## Current State

### 5-stage Loop Engineering lineage (Van Horn synthesis)

Per [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn]]:

| Stage | Year | Surface | Description |
|---|---|---|---|
| 1 | 2022 | **ReAct paper** | Academic while-loop: model reasons, calls tool, reads result, repeats. One model, one loop, human watching. |
| 2 | 2023 | **AutoGPT** | Goal-driven self-prompting loop; famously *"spinning forever doing nothing."* Seeded *"agents are a toy."* |
| 3 | 2025-07 | **ralph loop** ([[geoffrey-huntley\|Geoffrey Huntley]]) | Bash one-liner piping same prompt file into agent repeatedly. Context-reset to anchor files each iteration. Huntley built *"an entire programming language with it for about $297."* |
| 4 | 2026 spring | **`/goal` command** (Claude Code + Codex) | Productized ralph: runs until validator model confirms task done. *"The ralph loop, built into Claude Code."* |
| 5 | 2026 mid | **Orchestration loops** | Loops supervising loops, concurrent + scheduled, durable via git-backed state. Loop = unit of work, not task. |

### Stage-5 four innovations

1. **The loop became the unit of work, not the task**
2. **Loops started supervising other loops, concurrently and on a schedule**
3. **Scheduling replaced the human kickoff** — loops run on infrastructure time, not attention time
4. **Durability became explicit** — git-backed state + crash recovery

Stage-3 ralph assumed your terminal stayed open. Stage-5 assumes it does not.

### "Cron plus a decision-maker in the body" (Van Horn definition)

> *"A cron job runs a fixed script. A loop runs a model that looks at the current state, decides what to do next, does it, checks whether it worked, and decides whether to keep going. The decision is the agent's, not yours, and not a hardcoded branch. Stack those, let one loop dispatch and supervise others, give them durable shared state, and you have something cron cannot express."* — [[mvanhorn-wtf-is-a-loop-2026-06-07]]

**Cherny disclosure** (via Van Horn): *"Boris literally runs his on cron. The /loop command in Claude Code uses cron under the hood."*

### 3 production hard-stops (Van Horn synthesis)

> *"Every serious 2026 write-up on loops converges on the same three hard stops..."*

1. **Maximum iteration count** — explicit halt at N ticks
2. **No-progress detection** — halt when state stops advancing
3. **Token or dollar budget ceiling** — halt at spend threshold

**Pattern**: production-grade loops are halt-condition-engineered, not iteration-count-optimized. Pairs with [[anthropic-dynamic-workflows-official-docs-2026-06|Dynamic Workflows]] runtime constraints (16 concurrent / 1000 total).

### Push-back primitive — "loop with something that can say no"

Per Mo (@mosyaseen) reply in [[steipete-loops-engineering-vision-md-2026-06-07|Steinberger thread]]: *"designing the loop is half of it. the other half is putting something in the loop that can say no: a test, a type check, a real error. a loop with nothing to push back is the agent agreeing with itself on repeat."*

Push-back primitives: tests, type checks, real errors, **VISION.md** (per Steinberger), continuous review (e.g., [[mvanhorn-wtf-is-a-loop-2026-06-07|roborev by Dan Kornas]] reviews every commit and feeds findings back).

**Pattern**: *"The loop is not the magic. The feedback inside it is."* (Van Horn)

### 4-stage practitioner-content evolution timeline

Steinberger framing ([[steipete-loops-engineering-vision-md-2026-06-07]]):

1. **Prompts** (pre-2024) — direct LLM interaction
2. **Harnesses** (early 2026 per [[trq-dynamic-workflows-harness-2026-06-02|Thariq]]) — custom harnesses on top of Claude Code
3. **Loops** (mid-2026 current) — designing the loop that prompts the agent
4. **Fleets-that-design-loops** (Steinberger predicts ~3 months out, ~Sept 2026)

### Multi-agent orchestration receipts

- **[[steve-yegge|Steve Yegge]] Gas Town** ([github.com/gastownhall/gastown](https://github.com/gastownhall/gastown), Jan 2026): 20-30 Claude Code instances coordinated by a **Mayor agent**, **Patrol agents** running continuous loops, state stored in git for crash recovery. First wiki-captured concrete instantiation of the *"loop supervising other loops"* pattern shipped + open source. See [[mvanhorn-wtf-is-a-loop-2026-06-07]].
- **[[zodchii-4-agent-pipeline-2026-05-30|zodchii 4-agent pipeline]]**: Planner/Coder/Tester/Reviewer with discrete handoff-files in `.pipeline/{spec,changes,test-results,review}.md`. Sibling architectural pattern: **discrete handoff** vs Yegge's **continuous-supervised**.
- **[[dailybrief-roundup-2026-05-27|PolyArch/humanize RLCR loop]]**: Claude implements + Codex reviews independently until acceptance criteria met. **Cross-vendor agent-review loop**.

## Key Papers / Posts

- **ReAct paper** (2022): [arXiv:2210.03629](https://arxiv.org/abs/2210.03629) — academic origin of the reason-act-observe-repeat loop
- **AutoGPT** (2023): goal-driven self-prompting loop; seeded *"agents are a toy"* discourse
- **[[geoffrey-huntley|Huntley]] ralph** (2025-07): [ghuntley.com/ralph/](https://ghuntley.com/ralph/) — bash-one-liner with context-reset discipline
- **[[claude-code|Claude Code]] `/goal` launch** (2026 spring) — ralph productized as Anthropic-canonical primitive
- **[[steipete-loops-engineering-vision-md-2026-06-07|Steinberger Loops Engineering tweet]]** (2026-06-07): *"you should be designing loops that prompt your agents"*
- **[[bcherny-5-tips-opus-autonomous-2026-06-05|Cherny 5-tip recipe]]** (2026-06-05): Anthropic-internal-creator-voice canonical checklist for autonomous-Opus operation
- **[[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn WTF Is a Loop synthesis]]** (2026-06-07): comprehensive synthesis-essay surfacing the 5-stage lineage + Cherny WorkOS receipts + Gas Town + roborev + Uber cap + Gartner deployment-gap

## Related Concepts

- [[claude-md-pattern]] — CLAUDE.md / VISION.md project-tier canonical content-template stack; VISION.md is Steinberger's push-back primitive
- [[trq-dynamic-workflows-harness-2026-06-02]] — Thariq's *"A harness for every task"* + 3-failure-mode framework (agentic laziness / self-preferential bias / goal drift) that loops exist to solve
- [[anthropic-dynamic-workflows-official-docs-2026-06]] — Anthropic Dynamic Workflows canonical docs (16 concurrent / 1000 total runtime constraints; pair-with-`/goal` recommendation)

## Verification-pending

- Whether *"fleets that design your loops"* (Steinberger 2026-09 prediction) materializes
- Primary source for Van Horn's *"~4% of all public commits on GitHub"* Claude-Code-share figure
- Primary source for Uber $1500/person/tool/month cap (Van Horn cites without link)
- Gartner Hype Cycle agentic-AI Peak-of-Inflated-Expectations citation primary
- Cherny *"context rot isn't a thing with 4.8 imo"* test methodology — what was the test
