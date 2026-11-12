---
title: "SkillsBench: Benchmarking How Well Agent Skills Work Across Diverse Tasks"
type: source
medium: paper
url: https://arxiv.org/abs/2602.12670
ingested: 2026-11-12
---

## Summary

An arXiv paper (Xiangyi Li et al., v1 2026-02-13, latest v4 2026-06-14) that measures whether Agent Skills help, by running agents on tasks with deterministic checkers under matched conditions with and without skills. It's the first controlled measurement of skills the wiki holds. Only the v1 and v4 abstracts were read, not the paper. [[perplexity-agent-skills-guide-2026-05-01|Perplexity's guide]] cites it.

## Key Claims / Takeaways

- **Curated skills help on average (v1):** *"Curated Skills raise average pass rate by 16.2 percentage points"*, over *"7 agent-model configurations over 7,308 trajectories"*.
- **Unevenly:** *"+4.5pp for Software Engineering to +51.9pp for Healthcare"*, and *"16 of 84 tasks show negative deltas"*. Coding gains the least.
- **Model-written skills don't help (v1):** *"Self-generated Skills provide no benefit on average, showing that models cannot reliably author the procedural knowledge they benefit from consuming."*
- **Short beats complete:** *"Focused Skills with 2--3 modules outperform comprehensive documentation"*, and *"smaller models with Skills can match larger models without them."*
- **v4 updates the numbers:** *"Curated Skills raise the average pass rate from 33.9% to 50.5%"* across *"18 model-harness configurations"*. **The v4 abstract no longer mentions the self-generated condition.** The paper wasn't read, so it's unknown whether that result was dropped, changed or only cut from the abstract. Perplexity's quote matches v1.

## Pages Updated

- [[skill-md]] — new 2026-11-12 section, answers part of the 2026-10-06 open question
