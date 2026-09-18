---
title: "DX Core 4 — a unified framework for measuring developer productivity"
type: source
medium: article
url: https://getdx.com/research/measuring-developer-productivity-with-the-dx-core-4/
ingested: 2026-09-17
---

## Summary

Two companion pieces from **DX** — the *Engineering Enablement* newsletter announcement by **Abi Noda** and the accompanying whitepaper — introducing the **DX Core 4**, a framework that folds **DORA, SPACE and DevEx** into one prescriptive set of metrics. Authored by Noda and **Laura Tacho** (DX CTO) with **Nicole Forsgren**, **Michaela Greiler** and **Tom Zimmerman**.

**Published circa December 2024** — this is older reference material ingested now, not news. It is captured because the wiki has spent September 2026 accumulating agentic-coding throughput claims (*80% of code*, *8× output*, *98% not handwritten*) **with no measurement framework to read them against**, and this is the framework the field already agreed on.

## Key Claims / Takeaways

### Why it exists

DORA, SPACE and DevEx each answer a different question and none answers *"what should we measure?"*:

- **DORA** — prescriptive metrics, but limited to system performance
- **SPACE** — a framework for defining your own metrics, *"which is difficult to actually do"*
- **DevEx** — developer experience and self-reported measures, *"isolated from the broader concept of productivity"*

Noda's stated trigger: executives asking *"So what exactly should we be measuring?"* and his own answer being *"It depends."*

### The four dimensions and their primary metrics

| Dimension | Primary metric | Purpose |
|---|---|---|
| **Speed** | **Diffs (or PRs) per engineer** | flow of work through the system |
| **Effectiveness** | **Developer Experience Index (DXI)** — 14 standardized Likert items | the drivers behind speed and quality |
| **Quality** | **Change Failure Rate** | *"ensures that a focus on speed does not come at the cost of stability or reliability"* |
| **Impact** | **% of time on new capabilities** | feature work vs maintenance/KTLO |

### The counterbalancing rule — the load-bearing part

The framework's central discipline is that **throughput metrics must never stand alone**:

> *"It is critical that this metric is never used at the individual level or tied to performance evaluations. Additionally, it must be counterbalanced with other oppositional metrics like the Developer Experience Index."*

Three stated preconditions for using diffs-per-FTE at all: **counterbalance with an oppositional metric; set no targets or rewards against it; communicate how it will be used.** And the design principle behind the whole thing: *"Multiple dimensions are needed… changes to one dimension, such as speed, may negatively affect others."*

They are explicit that speed metrics in isolation *"often incite fear and counterproductive behaviors."* They also concede diffs-per-FTE is contested and defend it as a *signal* used carefully — noting Meta, Microsoft and Uber rely on it.

### Collection

Three methods, deliberately mixed: **system metrics** (precise, continuous, preferred where feasible), **self-report** (fast, works where system data doesn't exist), and **experience sampling** (in-the-flow data tied to specific tasks). The pitch is *"deployable in weeks, not months"* by starting with surveys and adding instrumentation later.

### Claimed results

Deployed at **300+** companies across tech, finance, retail and pharma: **3–12% increase in engineering efficiency**, **14% increase in R&D time on feature development**, **15% improvement in employee engagement**.

## Pages Updated

- [[developer-productivity-measurement]] (NEW)
- [[agentic-engineering]]

## Notes

- **Vendor-authored.** DX sells the platform that measures this, the whitepaper ends in a demo link, and the DXI is DX's own proprietary index. The **lineage is independent and credible** (Forsgren's DORA, SPACE, the DevEx ACM Queue paper); the **benchmark numbers are not** — 300+ companies and the 3–12% figure are unaudited self-report.
- **Date reconstructed, not confirmed.** The newsletter references the DevEx framework as published *"last year"* and links a LinkedIn post whose activity ID places it in **December 2024**; neither `_raw` file carries an explicit date. Treat "circa Dec 2024" as inferred.
- **Authors are create-candidates**, all single-surface here: Abi Noda, Laura Tacho, Nicole Forsgren, Michaela Greiler, Tom Zimmerman.
