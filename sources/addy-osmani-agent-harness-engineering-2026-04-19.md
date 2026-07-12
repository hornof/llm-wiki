---
title: "Addy Osmani — \"Agent Harness Engineering\" (Agent = Model + Harness; the ratchet principle + 8 harness layers)"
type: source
medium: article
url: https://addyosmani.com/blog/agent-harness-engineering/
ingested: 2026-07-12
---

## Summary

[[addy-osmani|Addy Osmani]] (Google Chrome DevRel) publishes **"Agent Harness Engineering"** (2026-04-19; resurfaced in the [2026-07-12 Daily Brief](../Daily%20Briefs/2026-07-12.md)) — a comprehensive practitioner synthesis of the discipline the wiki tracks as [[loop-engineering|loop/harness engineering]]. Its load-bearing equation is **`Agent = Model + Harness`**, and its thesis: *"A decent model with a great harness beats a great model with a bad harness."* This is the most complete single-author taxonomy of the harness the wiki has captured, and it names two principles the prior cluster only implied — the **ratchet principle** and **working-backwards-from-behavior**.

## Key Claims / Takeaways

### Core framing
- **`Agent = Model + Harness`** — the harness = all code, config, and execution logic beyond the model itself (system prompts, skill files, `AGENTS.md`, tools, sandboxes, orchestration, hooks, context management, observability).
- *"A decent model with a great harness beats a great model with a bad harness."* — the sharpest restatement yet of [[trq-dynamic-workflows-harness-2026-06-02|Thariq's "reliability comes from the harness, not the model"]] and the [[loop-engineering|loop-engineering]] "the loop, not the model, is the expensive/important part" thesis.

### Two named principles (net-new to the cluster)
- **The ratchet principle**: every agent failure becomes a *permanent* constraint — *"Every line in a good `AGENTS.md` should be traceable back to a specific thing that went wrong."* Operationalizes the [[claude-md-pattern|CLAUDE.md]] "each rule answers what mistake it prevents" discipline as a one-directional accumulator (failures ratchet into rules; rules don't regress). Pairs with [[alex-lieberman-ai-engineering-best-practices-2026-07-09|Lieberman's markdown-autophagy]] as the maintenance counterpart.
- **Working backwards from behavior**: derive harness components from desired outcomes, not speculatively — *"If you can't name the behaviour a component exists to deliver, it probably shouldn't be there."*

### The 8 harness layers
1. **Filesystem & Git** — durable state + versioning
2. **Bash & Code Execution** — general-purpose tool access
3. **Sandboxes** — safe isolated execution
4. **Memory & Search** — continual learning via context injection
5. **Context Management** — compaction, tool-call offloading, skills
6. **Long-Horizon Execution** — planning loops, verification, agent splits
7. **Hooks** — enforcement at lifecycle points (pre-commit, post-edit, …)
8. **Tool Configuration** — focused, well-named tools with clear descriptions

### Loops & verification (maps onto the existing cluster)
- Centered on **ReAct loops** (reason → act → observe → repeat) wrapped in enforcement.
- **Ralph loops** for multi-session autonomy via context resets ([[geoffrey-huntley|Huntley]] lineage).
- **Planner / Generator / Evaluator splits** to avoid self-grading bias (the maker-checker discipline: McDonald/Zodchii).
- **Sprint contracts** defining done-conditions before execution.
- **Self-verification hooks** surfacing test failures directly into the agent's reasoning loop — *"Success is silent, failures are verbose."*

### Two forward-looking framings
- **Model–harness training loop (co-optimization)**: useful harness primitives get standardized → influence model post-training → models get better at those specific actions. Harnesses are *not* model-agnostic scaffolding; they co-evolve with the weights.
- **Harness-as-a-Service (HaaS)**: the shift from building loops from scratch to configuring pre-factored runtimes — [[claude-agent-sdk|Claude Agent SDK]], Codex SDK, OpenAI Agents SDK. Vendor-side sibling of Steinberger's "fleets that design loops" prediction.

> Also credited: Viv Trivedy — *"Good agent building is an exercise in iteration. You can't do iterations if you don't have a v0.1."*

## Pages Updated
- [[addy-osmani]] (new)
- [[loop-engineering]]

## Verification-pending
- Post is dated 2026-04-19; surfaced via the 07-12 brief. Full primary was fetched for this page (not brief-only), but the Claude Code "architecture diagram" and per-layer depth were summarized, not reproduced.
