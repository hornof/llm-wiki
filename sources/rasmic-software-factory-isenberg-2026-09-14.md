---
title: "Building a Software Factory that actually works — Ras Mic on The Startup Ideas Podcast"
type: source
medium: video
url: https://www.youtube.com/watch?v=_LCeJZFIsd4
published: 2026-09-14
ingested: 2026-09-22
---

## Summary

**Ras Mic** (@Rasmic) with [[greg-isenberg|Greg Isenberg]], ~30 minutes, published **2026-09-14**. Mic shares his screen and walks through the actual system he runs: a **four-step software factory — isolate, build, prove, ship**.

**The wiki's first Isenberg video source with a full transcript**, and the most complete end-to-end agentic-delivery pipeline it holds. It is also the clearest statement yet of the position that the durable asset is **neither the model nor the harness**.

## Key Claims / Takeaways

### What a software factory is — and what it isn't

> *"A software factory is completely harness and model agnostic, meaning it doesn't matter what m[odel]…"*

Mic defines it as **a workflow, a set of skills, and domain knowledge, packed into markdown files** — not a product, not a platform. The section title says it plainly: **"A Software Factory Is Markdown Files."**

This cuts directly across [[domain-specific-harness]]. [[pieter-levels|Levels]] argues the labs absorb the harness; [[omarsar0-should-you-build-a-harness-2026-09-12|Saravia]] argues you must own it. **Mic's position is that the valuable layer sits above both** — portable markdown that runs on any model and any harness, so neither lock-in nor absorption touches it. He is pointed about the vendors: *"there's been a lot of like startups who have started… but a software factory is completely harness and model agnostic."*

### The four steps

| Step | Mechanism |
|---|---|
| **1 · Isolate** | Every feature starts in a **fresh git worktree branched from `origin/main`**. *"A work tree acts like a copy of the app."* Each agent gets its own station; one agent cannot disturb another's. |
| **2 · Build** | A **"code structure" skill** forces service-layer architecture. Rationale is blunt: *"Models get the job done, and they often get it done in a sloppy way, so the skill supplies the guideline."* Target is code **a hired developer can read**. |
| **3 · Prove** | **Evidence-driven testing** — the agent records a **before state and an after state** as **video, screenshots, or numbers**. |
| **4 · Ship** | **Greptile scores the PR**, and the agent **loops back to build until it earns 5/5**. |

### The two ideas worth extracting

**Evidence-driven testing generalises the verification problem.** Step 3 is not "write tests" — it is *make the change externally observable* by capturing before/after as video, screenshots or numbers. That is the same move as the [[chrisjz-universe-atlas-fable-verification-2026-07-16|universe atlas's deterministic URLs]], which let the agent re-enter the exact frame a human saw. Both close the gap between what the operator perceives and what the agent can inspect. Mic's payoff: **he reviews the visual proof instead of the raw code.**

**`agents.md` should hold workflow, not facts.** *"Most people fill it with facts the agent already reads from the code base. He fills his with a workflow instead."* A sharp, testable correction to how the wiki has described [[claude-md-pattern|the CLAUDE.md pattern]] — and it lands the same week [[dailybrief-roundup-2026-09-20|Claude Code shipped `AGENTS.md` support]]. The instruction file's job is to supply what the codebase *cannot* state: the order of operations.

### Scale and tooling

- **Up to 15 features in parallel**, reviewed via visual proof rather than diffs.
- **GPT-6 Astra** as his workhorse — named as *"the model with the lowest hallucination rate."*
- **Greptile** as the PR scorer and loop gate.

### The factory analogy

Isenberg maps the four steps onto a physical plant: a custom order gets its own station, the assembly line builds it, **quality control tests it**, shipping sends it out. Mic agrees and says he may rename his skills to match.

## Pages Updated

- [[loop-engineering]]
- [[agentic-engineering]]
- [[claude-md-pattern]]
- [[domain-specific-harness]]
- [[greg-isenberg]]

## Notes

- **Full transcript captured** in the `_raw` clipping — unusually good for a video source, and the reason this page can quote mechanisms rather than summarise vibes.
- **Self-reported and undemonstrated at scale.** "Up to 15 features in parallel" and the 5/5 Greptile gate are his account of his own system; no throughput, defect-rate or quality figures. The **absence of a quality measure** is the same gap flagged on [[developer-productivity-measurement]] — evidence-driven *proof* is not a change-failure rate.
- Heavily sponsored (Brex read, two of Isenberg's own businesses linked, a paid "create your own software factory" link). The mechanisms stand on their own; the urgency is sales.
- **Ras Mic — create-candidate, held.** First wiki surface. Page on a second.
