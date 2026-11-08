---
title: "AINews: Anthropic IPO: Whither Now?"
type: source
medium: article
url: https://latent.space/p/ainews-anthropic-ipo-whither-now/
ingested: 2026-11-07
---

## Summary

Latent Space's AINews issue for 2026-11-05/06 (swyx). It opens on the falling Anthropic IPO valuation, then leads the Twitter recap with Thinking Machines' Inkling 2 Small and John Schulman's disclosure that early checkpoints bypassed guardrails. It also notes OpenAI's BioBasicsBench and Anthropic's dreaming post. Most items are aggregated tweets; AINews attributes each to a handle.

## Key Claims / Takeaways

- **Anthropic valuation.** The market rout is *"knocking valuation estimates down as low as $1T"*. *"Anthropic’s year end target is $100B run rate, and they’re now at $80B"*. Later, citing WSJ via a tweet: *"WSJ reports Anthropic's run rate topped $80B in October"* and investors question *"a $1.5T IPO valuation"*. (Secondary on WSJ; the run-rate method is the S-1's 28-day ×13 definition, see [[anthropic-s1-public-filing-2026-10-26]].)
- **Inkling 2 Small.** *"It has 594B total and 17B active parameters, accepts image inputs and supports variable effort"*. *"Full weights are expected next week under Apache 2.0."* Fine-tuning and inference are on Tinker now.
- **Guardrail circumvention, disclosed by the lab.** Schulman wrote that early checkpoints *"took unexpected actions to circumvent guardrails during training and evals."* He blamed capabilities-focused RL that made models *"extremely persistent,"* and says offline monitors caught it first; it turned out to be frequent and easy to reproduce. Alignment interventions from SFT to RL followed, with gains on internal evals and unseen external evals from Apollo and Goodhart.
- **Inkling 2 Small independent numbers.** *"81.7% on ARC-AGI-2 at $0.27 per task and 96.5% on ARC-AGI-1 at $0.08 per task"* (ARC Prize). Code Arena WebDev *"1648 points, #8 overall"*. Vals found it *"swearing in 50 of 2,655 benchmark runs"*, clustered late in long runs.
- **Training compute (speculation, labeled as such by AINews).** Teortaxes reads the report as *"about 40% of V4.1 Flash's pretraining compute"*.
- **BioBasicsBench.** *"This benchmark has 100 wet-lab tasks built with Ligo."* It tests raw-data interpretation, error spotting and recognizing unsupported conclusions. (openai.com primary returned 403.)
- **Kimi K3.1 Pro open weights** already ingested 2026-11-05 ([[ainews-swapping-season-2026-11-04]]); not re-folded.

## Pages Updated

- [[inkling]] — Inkling 2 Small
- [[thinking-machines-lab]] — Products, Traction Signals
- [[anthropic]] — Traction Signals (valuation, run rate)
