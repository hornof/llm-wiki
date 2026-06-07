---
title: "Linas Beliūnas — The Complete Claude /goal Guide for AI Agents (2026-05-14)"
type: source
medium: blog-post
url: https://linas.substack.com/p/the-complete-claude-goal-guide
ingested: 2026-06-08
---

## Summary

[[linas-beliunas|Linas Beliūnas]] publishes (2026-05-14; surfaced in wiki 2026-06-07 via [@linasbeliunas X amplification](https://x.com/linasbeliunas/status/2063610115970748772)) **a load-bearing canonical practitioner-content guide on Claude Code's `/goal` slash command**. **First wiki-captured comprehensive canonical practitioner-content guide on `/goal`**. The guide articulates the **3-element formula for writing goal conditions that work** + **reliability architecture for multi-hour agent runs** + **3 production-grade prompt templates** specifically for fintech (deep competitive research + code-heavy builds + ongoing portfolio/market monitoring). Pairs structurally with [[anthropic-dynamic-workflows-official-docs-2026-06|Anthropic Dynamic Workflows canonical docs]] which note *"pair with `/goal` for hard completion requirements"* — Linas's guide is the **operator-side companion** to the Anthropic-canonical canonical docs.

## Key Claims / Takeaways

### The thesis

> *"You give an agent a complex task — a sector deep dive, a backtesting pipeline, a daily intelligence digest — and it either halts for confirmation every three steps, loops indefinitely without finishing, or delivers a plausible-looking output that quietly fails to meet the actual requirements. The bottleneck is rarely the model. It's the spec."*

**Pattern**: `/goal` is Claude Code's mechanism for turning a session into an autonomous loop. The bottleneck is goal-condition-quality, not model capability.

> *"`/goal` is Claude Code's mechanism for turning a session into an autonomous loop: **the agent runs, verifies whether the goal condition is met, and continues until it is — without checking in with you**."*

**First wiki-captured concrete framing of `/goal` as session-into-autonomous-loop mechanism** with verifies-until-met semantics.

### The 3-element formula for goal conditions

The guide articulates a **3-element formula** for writing `/goal` conditions that work (specific elements verification-pending — primary content paywalled but referenced in framing):

1. **How `/goal` actually evaluates conditions** (and why most conditions are unevaluable)
2. **The 3-element formula** for writing conditions that work
3. **The reliability architecture** that determines whether a multi-hour agent run completes

### Reliability architecture framing

> *"Anthropic's own research on long-running agents shows that **reliability comes from the harness, not the model**."*

**Pattern**: extends [[trq-dynamic-workflows-harness-2026-06-02|Thariq's harness-for-every-task framing]] to the `/goal`-specific case — reliability is harness-bound, not model-bound. **First wiki-captured operator-side instantiation of the Anthropic-canonical harness-reliability framing**.

### "Context rot" framing

> *"Context rot silently degrades long runs well before the window fills."*

**First wiki-captured "context rot" framing in the wiki** as a distinct failure mode separate from context-window-overflow. Pairs structurally with [[trq-dynamic-workflows-harness-2026-06-02|Thariq's 3-failure-mode framework]] — *goal drift* is the closest framework-match; *context rot* operates at the same layer but distinct.

### Pairs with Anthropic Dynamic Workflows canonical docs

The [[anthropic-dynamic-workflows-official-docs-2026-06|Anthropic canonical Dynamic Workflows docs]] explicitly recommend *"pair with `/goal` for hard completion requirements"* + *"pair with `/loop` for repeatable workflows."* Linas's guide is the **first wiki-captured operator-side comprehensive canonical guide on `/goal`** — establishes the bidirectional canonical-docs ↔ practitioner-content relationship at the `/goal` primitive layer.

### Pairs with companion guides

The guide cites 2 companion pieces:
- **[The System for Never Hitting Claude's Limits](https://linas.substack.com/p/claude-usage-limits-system)** — context-engineering + model-selection discipline for long `/goal` runs (verification-pending if wiki-captured)
- **[End-to-End Guide to Claude Code Routines](https://linas.substack.com/p/claude-code-routines-guide)** — copy-paste routines for autonomous code review + deploy verification + deal flow screening (verification-pending if wiki-captured)

**First wiki-captured Linas Beliūnas 3-guide canonical-practitioner-content stack** (`/goal` + Claude limits + Routines).

### Fintech-vertical framing

Linas specifically targets the fintech vertical:
- Sector deep dive (competitive research)
- Backtesting pipelines (code-heavy builds)
- Daily intelligence digest (ongoing portfolio + market monitoring)

Adds *"data sensitivity tiers, environment segregation, regulatory output flagging, simulation-only constraints"* as fintech-specific constraints the generic frameworks omit. **First wiki-captured fintech-vertical-specific practitioner-content for Claude Code primitives**.

### Cross-cutting framings

- **First wiki-captured comprehensive canonical practitioner-content guide on Claude Code's `/goal` primitive**
- **First wiki-captured operator-side comprehensive guide for any single Claude Code primitive** — Anthropic Dynamic Workflows docs cover multiple primitives; Linas's guide goes deep on `/goal` specifically
- **First wiki-captured "context rot" framing** as distinct from context-window-overflow
- **First wiki-captured fintech-vertical-specific practitioner-content** for Claude Code primitives
- **Establishes Linas as Claude-Code-primitive-canonical-practitioner-content voice**: 1st surface was [[linas-beliunas]] entity page (May 5 wiki capture); 2nd-3rd surfaces are this `/goal` guide + the [[linas-beliunas-dynamic-workflows-guide-2026-06-04|Dynamic Workflows guide]] paired-published surfaces. **First wiki-captured Linas-as-Claude-Code-practitioner-content cluster** with 2 substantive standalone guides + 1 amplification X post in ~3 weeks.

### Notably-absent (verification-pending)

- **Primary guide content** is partially paywalled / Substack-subscriber-only — only the *outline* + *framing* + *companion-guides references* are surfaceable in current ingest
- **Specific 3-element formula content** — verification-pending; needs paid-subscriber primary fetch
- **Specific 3 production-grade prompt templates** — verification-pending
- **Specific `/goal` mechanism deep-dive** (how does Claude Code internally evaluate goal-conditions?) — verification-pending
- **Comparison with `/loop` primitive** — verification-pending
- **Specific token-cost data** for long `/goal` runs

## Pages Updated

- [[linas-beliunas]] — first canonical practitioner-content guide; 2nd wiki surface; major update to Notable Takes
- [[claude-code]] — `/goal` canonical-practitioner-content guide added under Resources
- [[trq-dynamic-workflows-harness-2026-06-02]] — back-link as operator-side companion to Anthropic-canonical harness framing
- [[anthropic-dynamic-workflows-official-docs-2026-06]] — back-link as operator-side companion-guide

## Adjacent sources

- [[linas-beliunas-dynamic-workflows-guide-2026-06-04]] — companion Dynamic Workflows guide
- [[anthropic-dynamic-workflows-official-docs-2026-06]] — Anthropic-canonical docs that recommend `/goal` + `/loop` pairing
- [[trq-dynamic-workflows-harness-2026-06-02]] — Thariq's harness framing
- [[linas-beliunas]] — entity page
- [[claude-md-pattern]] — 3-tier canonical content-template stack (project + domain + role) — `/goal` is a session-orchestration primitive that operates alongside the 3-tier stack

## Verification-pending

- Specific 3-element formula content
- Specific 3 production-grade prompt templates (fintech vertical)
- Specific `/goal` evaluation mechanism deep-dive
- Comparison with `/loop` primitive
- Specific token-cost data for long `/goal` runs
- Whether the companion guides (Claude Usage Limits + Routines) are wiki-captured
- Whether Linas publishes paid-only content with sufficient public framing that wiki coverage stays substantive
