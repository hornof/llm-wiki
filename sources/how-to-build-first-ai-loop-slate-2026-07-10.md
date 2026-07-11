---
title: "Rahul (@sairahul1) — \"How To Build Your First AI Loop in 2026\" long-form thread + Andrew Ng \"prompting is gone in 3-6 months\" quote-tweet (2026-07-10)"
type: source
medium: twitter-thread
url: https://x.com/sairahul1/status/2075479271032942658
ingested: 2026-07-10
---

## Summary

Rahul (**@sairahul1**, theaibuilders.co) publishes a long-form X thread, **"How To Build Your First AI Loop in 2026,"** a step-by-step build guide that restates the by-now-canonical [[loop-engineering|Loop Engineering]] doctrine and threads it through a single tool, **[[slate|Slate]]** (by RandomLabs). A companion quote-tweet frames the thread around a **claimed [[andrew-ng|Andrew Ng]] quote**: *"100% of my tasks are done by ai agents, self-improving loops are next. Give it 3-6 months and prompting is gone."* The thread is high-quality as a tutorial but is structurally a **promotional vehicle for Slate** from an engagement-optimized account (*"Worth more than any $500 agentic course"*). Net-new to the wiki: the Slate tool, Ng's escalated (second-hand) quote, and the Forward Future Loop Library resource. The loop *doctrine* it teaches is already fully captured in [[loop-engineering]].

## Key Claims / Takeaways

### Net-new signal
- **[[slate|Slate]]** (by RandomLabs, `npm i -g @randomlabs/slate`) — a terminal AI coding agent positioned for **swarm orchestration**: auto-selects a model per step (plan with Claude, reason with GPT-5.6, search with Haiku), runs parallel isolated subagents, manages its own long-session context. Config via `slate.json` (per-role model map + permissions); context via `AGENTS.md`; reusable behavior via `.slate/skills/<name>/SKILL.md`; memory via `STATE.md`. Loop wrappers: `slate --queue loop.md` (queue-file), `slate run "$(cat loop.md)" --dangerously-skip-permissions --output-format stream-json` (headless/CI), `slate --continue` (resume). Steer/queue/interrupt modes; `slate serve`/`attach` server mode. **See [[slate]] — signal is thin; sole source is this promotional thread.**
- **[[andrew-ng|Andrew Ng]] escalated quote (second-hand, via Rahul)**: *"100% of my tasks are done by ai agents, self-improving loops are next. Give it 3-6 months and prompting is gone."* Attributed by Rahul to a 32-minute Ng video; **not directly sourced** here. A sharper, more absolutist version of Ng's [[andrew-ng-loop-engineering-3-loop-validation-2026-06-30|Jun 30 3-loop validation]]. Treat as claimed until the primary video surfaces.
- **Forward Future Loop Library** (`signals.forwardfuture.com/loop-library`) — a browsable catalog of running loops across content / engineering / operations / research. New resource; unverified.

### Loop doctrine restated (already in [[loop-engineering]])
- **Loop framing**: reprises the [[peter-steinberger|Steinberger]]/[[boris-cherny|Cherny]] "you write loops, not prompts" opening verbatim; loop cycle **Discover → Execute → Verify → Iterate → Stop**.
- **4-condition test before building a loop**: (1) task repeats ≥weekly, (2) verification is automated, (3) token budget can absorb the waste, (4) "done" is objective. *"Fail any one → use a prompt instead."* — a crisp practitioner articulation of when a loop earns its cost.
- **Failure modes** (all already tracked): **Ralph Wiggum loop** (declares done early), **goal drift** (early constraints forgotten by message 47; fix = re-read `VISION.md`), **self-preferential bias** (maker grades own homework; fix = verifier subagent with no access to maker reasoning), **agentic laziness** (objective stop condition only: "exit code 0 on both commands. That is the only done").
- **Maker-checker split** as *"the single most important structural improvement"*; **`STATE.md` as durable memory** across sessions; hard iteration cap (8 to start); human gate on irreversible actions.
- **GPT-5.6** cast as a loop *amplifier*, not replacement: *"The better the model gets, the more expensive it becomes to leave it idle between prompts."*
- **Closing**: *"Loop design is harder than prompt engineering — not easier… build it like someone who intends to stay the engineer."*

## Editorial note

This is the **promotional / tutorial-listicle register** of loop engineering — a real how-to wrapped around a paid tool and an engagement hook. The doctrine adds nothing new to the [[loop-engineering]] cluster; its value to the wiki is the tool sighting ([[slate]]), the escalated Ng quote (flagged second-hand), and the loop-library resource. Not counted as a new "canonical voice" in the cluster.

## Pages Updated
- [[slate]] (new)
- [[loop-engineering]]
- [[andrew-ng]]
