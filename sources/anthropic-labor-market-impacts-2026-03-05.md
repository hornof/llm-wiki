---
title: "Labor market impacts of AI: A new measure and early evidence"
type: source
medium: paper
url: https://www.anthropic.com/research/labor-market-impacts
ingested: 2026-05-14
---

## Summary

Anthropic Economic Index research report, 2026-03-05, by Maxim Massenkoff and Peter McCrory (with [[jack-clark]] in acknowledgements). Introduces a new measure of AI labor-market exposure — **observed exposure** — combining theoretical LLM capability (Eloundou et al. 2023's β-metric) with Anthropic's own usage data from the Economic Index, weighted to upcount automated and work-related uses. Tests the framework against US Current Population Survey data. **Headline finding: no systematic unemployment increase for highly exposed workers since late 2022, but tentative evidence that hiring of 22-25-year-olds into exposed occupations has slowed (~14% drop in job-finding rate, just barely statistically significant).** First wiki-tracked frontier-lab research that uses the lab's own usage data as the input to a labor-economics analysis — a structural move that other labs can't replicate without comparable telemetry.

## Key Claims / Takeaways

### The framework

- **`observed exposure`** = (theoretical LLM capability per Eloundou et al. β-metric) × (actual usage on Claude in work-related context) × (automated > augmentative weight) × (task-time-fraction in role).
- Inputs: O*NET ~800 occupations + their tasks; Eloundou et al. (2023) task-level β scores (1 = LLM alone can double speed; 0.5 = LLM + tools; 0 = not feasible); Anthropic Economic Index usage data across four prior reports.
- **97% of observed Claude usage** falls into tasks rated β=0.5 or β=1.0 (theoretically feasible). β=1 tasks alone account for **68% of usage**. β=0 tasks: 3%.
- AI is far from theoretical capability everywhere: Claude covers **just 33%** of Computer & Math tasks despite Eloundou et al. estimating 94% theoretical feasibility.

### Most-exposed occupations (top of Figure 3)

1. **Computer Programmers — 75% coverage** (top of the list)
2. **Customer Service Representatives** — main tasks "increasingly seen in first-party API traffic"
3. **Data Entry Keyers — 67% coverage**

### Zero-coverage occupations (bottom)

**30% of workers have zero coverage.** Examples: Cooks, Motorcycle Mechanics, Lifeguards, Bartenders, Dishwashers, Dressing Room Attendants.

### Worker characteristics — top quartile of exposure vs. zero exposure (Aug-Oct 2022 baseline)

- **16pp more likely female**
- **11pp more likely white; ~2× more likely Asian**
- **47% higher mean earnings**
- **17.4% have graduate degrees** vs. 4.5% in unexposed group (~4× difference)
- Older on average

### BLS projection cross-check

- Higher-exposure occupations have **weaker BLS 2024-2034 growth projections**: every 10pp increase in coverage → 0.6pp lower projected employment growth (weighted regression).
- **No such correlation using Eloundou et al.'s β alone** — the usage-data adjustment is what makes the framework predictive.

### Headline empirical findings

- **No systematic increase in unemployment** for highly exposed workers since ChatGPT release (late 2022). DiD estimate of the unemployment-rate gap between top-quartile and zero-exposure groups is small and statistically indistinguishable from zero. Confidence interval suggests differential increases of ~1pp would be detectable.
- **Tentative young-worker hiring slowdown**: among 22-25 year-olds, monthly job-finding rate into highly exposed occupations dropped ~0.5pp post-ChatGPT, a ~14% relative decline from 2022 baseline — *just barely statistically significant*. No equivalent decrease for workers over 25.
- Authors flag alternative interpretations: young workers may be staying in existing jobs, taking different jobs, or returning to school. Survey mismeasurement also possible.
- Echoes **Brynjolfsson, Chandar, Chen (2025) "Canaries in the Coal Mine"** which found 6-16% fall in employment for 22-25 year olds in exposed occupations using ADP payroll data.

### Methodological stance

- Authors are explicit about humility: prior approaches (Blinder's offshorability, robot-displacement studies) have weak track records. Framework is designed to be re-run as data emerges, **not** to make point predictions.
- Priority outcome is **unemployment**, not job postings or wages — most directly captures economic harm.
- Treats "AI's impact will be unmistakable" as the optimistic case; the framework is for the **ambiguous-effects** scenario.

### Citation

`Massenkoff & McCrory, "Labor market impacts of AI: A new measure and early evidence", 2026-03-05.`

## Why It Matters

- **Direct wiki-owner relevance**: Computer Programmers are the single most exposed occupation at 75% coverage. If you're a VP Eng returning to hands-on AI work, the question "what does this mean for my career trajectory" is the centerpiece of the paper, not a sidebar.
- **Young-worker hiring slowdown is the actionable signal**: 22-25 year-olds entering coding roles see ~14% lower job-finding rates post-ChatGPT. For VPE-search conversations: this affects how to think about entry-level hiring strategy, how to design new-grad pipelines, and whether to staff teams via senior-leverage or junior-pipeline patterns.
- **Anthropic-as-research-shop signal**: this is the most empirically rigorous labor-market paper from a frontier lab to date — Massenkoff (UCSD economist, originally CMU PhD) and McCrory (NBER background, Federal Reserve roots) are real labor economists, not in-house policy staff. Pairs with [[import-ai-456-clark-rsi-radical-optionality-2026-05-11|Anton Korinek's RSI / economic-growth modeling]] from the same period — Anthropic is building a real economics research program around its own usage data, distinct from the alignment research output.
- **Brynjolfsson convergence**: two independent datasets (Anthropic CPS-matched usage data + ADP payroll) now show the *same* young-worker-hiring-slowdown signal. This is the cleanest cross-confirmation the wiki has captured on any AI-labor effect.
- **Framework-as-public-good**: by publishing the construction of `observed exposure`, Anthropic is implicitly inviting other labs to publish their own usage-anchored exposure measures. This is the kind of move that turns a competitive surface (usage data) into a research surface.
- **Wikipedia-defensive against the "AI is coming for all jobs" narrative**: the data does *not* support a generalized unemployment effect. The narrow young-worker signal is the only finding that survives statistical scrutiny. This is a useful counterweight to the noisier discourse the wiki captures from X / podcasts.

## Cross-references

- [[jack-clark]] — acknowledged in paper; runs the Anthropic policy / Import AI thread that this research feeds into.
- [[import-ai-456-clark-rsi-radical-optionality-2026-05-11]] — companion Anthropic-affiliated economics research (Korinek RSI work).
- [[concepts/ai-labor-market-impacts]] — new concept page anchored on this paper's `observed exposure` framework.
- [[companies/anthropic]] — first-party research output; entity updated.
- [[anthropic-finance-agents-2026-05-05]] — Customer Service Reps named as #2 most-exposed; finance-agents launch is the product-side correlate (KYC screener, statement auditor map directly to CSR-adjacent task automation).

## Pages Updated

- [[companies/anthropic]] (updated — March 5 2026 Anthropic Economic Index labor-market-impacts paper added under Key Research Contributions; cross-references to [[ai-labor-market-impacts]] concept)
- [[concepts/ai-labor-market-impacts]] (new — anchored on `observed exposure` framework, Brynjolfsson convergence on young-worker hiring slowdown)
- [[people/jack-clark]] (updated — Anthropic Economic Index research thread added as policy-adjacent output stream)
