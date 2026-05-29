---
title: "METR / Tom Cunningham: AI agents face faster diminishing returns than human labor"
type: source
medium: article
url: https://digg.com/ai/oqydy7vt
ingested: 2026-05-29
---

## Summary

**Tom Cunningham** (economist at **METR**) argues that **AI agents face faster diminishing returns to scaling than human labor** does (2026-05-29 via Digg). **Ryan Greenblatt** (also METR / Anthropic-adjacent) counters that *scalability favors agent spending despite the diminishing returns curve*. Surfaced via 2026-05-29 Daily Brief; primary not deeply fetched. **First wiki-captured economist-side modeling of agent vs human-labor cost curves** at the frontier-lab labor-economics frontier. **Brief framing**: *"Economists are modeling agent cost curves vs. labor. Cunningham argues scaling costs accelerate; Ryan Greenblatt counters scalability favors agent spending. Structural framing debate, not yet resolved."*

## Key Claims / Takeaways

### Cunningham's argument (skeptic position)

- **AI agents face faster diminishing returns than human labor.**
- Mechanism (inferred from brief framing; primary not fetched): per-agent compute cost scales super-linearly with capability / reliability target, while per-human-employee cost scales sub-linearly (training amortizes, retention compounds, judgment improves with experience).
- **Implication for [[ai-roi-gap]]**: the empirical practitioner-side observations of [[sankar-token-spend-roi-gap-2026-05-25|$100K → $18K funnel]] + [[cyb3rops-four-stages-ai-coding-hype-2026-05-26|stage-3 grind phase]] now have an economist-side theoretical explanation: the diminishing-returns curve on agents is *steeper* than on equivalent human-labor investment, so the spend-vs-shipped-value funnel structurally tightens as scale increases. **First wiki-captured economist-side structural model for the ROI gap.**

### Greenblatt's counter (bull position)

- **Scalability favors agent spending despite the diminishing returns.**
- Mechanism (inferred): the *total* deployment surface is so much larger for agents than for humans (24/7 availability, parallel fan-out, geographic non-constraint) that even with steeper diminishing returns, the *expected value of marginal agent-investment exceeds equivalent human-labor investment* over realistic deployment horizons.
- **Implication**: even if Cunningham is right about the curve shape, the *integrated area under the curve* may still favor agents. This is the [[anthropic-dynamic-workflows-primary-2026-05-28|Dynamic Workflows "tens to hundreds of parallel subagents"]] thesis in economist framing — *parallelism eats curve-shape*.

### The unresolved structural question

The brief frames this as *"structural framing debate, not yet resolved."* Neither Cunningham nor Greenblatt's framing has been falsified by deployment data yet. **The resolution lives in the empirical-data layer**:

- **If Cunningham right**: practitioner reports of *escalating cost-per-unit-output as agent fleets scale* over the next 12 months should accelerate. Pattern-watch is for a third Sankar-style funnel report at materially larger agent-fleet scale.
- **If Greenblatt right**: enterprise deployment data showing *positive ROI at material agent-fleet scale* should accumulate. Cognition's [[latentspace-walden-yan-async-agents-2026-05-29|80% commit rate]] (if methodology holds) is one such data point.

### Pairs with the [[ai-roi-gap]] two-compatible-reads framing

The [[ai-roi-gap#Capital-Allocator Counter-Anchor (Anthropic Series H, May 28 2026)|Series H counter-anchor]] section names two compatible reads. The Cunningham / Greenblatt debate aligns with each:

- **Read A** (*capital correctly recognizing infrastructure value*) — Greenblatt-aligned: parallel deployment integrates favorably; lab-tier capital allocation is correct.
- **Read B** (*same calibration error at the lab tier*) — Cunningham-aligned: steeper diminishing returns on agents than on humans means the lab-tier valuation premium under-prices the curve shape.

**The unresolved debate at the economist layer mirrors the unresolved debate at the capital-allocator layer.** Both will be settled by the same empirical-data accumulation over 2026-2027.

### Strategic implication: METR as the institutional frame

- **METR** (Model Evaluation and Threat Research) is the AI-evaluation organization most-cited for agent-task-time benchmarks (the *METR Doubling Law* on agent task-horizon length). Cunningham working at METR places this economist-modeling work *inside the AI-evaluation-org institutional frame*.
- **First wiki-captured METR-affiliated economic modeling.** Track for whether METR builds out an economics arm — that would be a structural addition to the labor-market-impacts measurement framework.

### What's notably absent from the brief

- **Cunningham's specific paper / pre-print / model** — primary not surfaced
- **Greenblatt's specific counter-argument source** — primary not surfaced
- **Quantitative model parameters** — diminishing-returns exponents, parallelism multipliers, etc.
- **Time-horizon assumptions** for the integrated-curve comparison
- **Whether the framing addresses [[anthropic-labor-market-impacts-2026-03-05|the Anthropic Economic Index `observed exposure`]] framework** as a related empirical anchor

## Pages Updated

- [[ai-labor-market-impacts]] — Cunningham/Greenblatt structural-debate added as **economist-side modeling layer** for the framework; pairs with the [[ai-roi-gap]] two-compatible-reads framing
- [[ai-roi-gap]] — Cunningham's faster-diminishing-returns argument added as economist-side theoretical anchor for the gap; Greenblatt's counter added as the parallelism-eats-curve-shape rebuttal
- [[ai-native-organizations]] *(if relevant section exists)* — agent-vs-human-labor cost-curve debate as input to org-design decisions
- METR — no entity page yet; defer pending second-source mention

Verification-pending: Cunningham's primary paper; Greenblatt's counter source; quantitative model parameters; time-horizon assumptions; whether the framing engages with the Anthropic Economic Index.

## Adjacent sources

- [[sankar-token-spend-roi-gap-2026-05-25]] — practitioner-side empirical data Cunningham's model would explain
- [[anthropic-labor-market-impacts-2026-03-05]] — empirical-side labor-market framework that the economist debate sits above
- [[anthropic-dynamic-workflows-primary-2026-05-28]] — *"tens to hundreds of parallel subagents"* is the parallelism-eats-curve-shape mechanism in product form
- [[latentspace-walden-yan-async-agents-2026-05-29]] — Cognition 80% commit-rate as a Greenblatt-aligned data point
- [[cyb3rops-four-stages-ai-coding-hype-2026-05-26]] — practitioner-side hype-cycle framing the economist debate explains structurally
