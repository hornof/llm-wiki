---
title: "Anthropic's IPO roadshow video"
type: source
medium: article
url: https://simonwillison.net/2026/Nov/11/anthropic-ipo-roadshow/
ingested: 2026-11-11
---

## Summary

[[simon-willison|Simon Willison]] (2026-11-11) transcribed the compute section of [[anthropic|Anthropic]]'s IPO roadshow video with MacWhisper, since Anthropic published no transcript. Co-founder Tom Brown describes training and serving Claude on four chip families, porting to AMD with Mythos, and "compute multipliers". Everything below is Brown's pitch to IPO buyers as Willison transcribed it. None of it is in the S-1 text the wiki has read.

## Key Claims / Takeaways

- **Four chip families.** *"We train and serve Claude now across all four major chip families."* Willison lists them as *"AWS Trainium, Google TPUs, NVIDIA GPUs, and AMD GPUs."*
- **Why it was hard:** *"Each chip needs its own tailored software stack and inference stack, which is expensive and difficult to build."*
- **AMD port done by Mythos.** Bringing on a new chip *"took dozens of engineers months of work"*. This year *"we had Mythos try it out. It got Claude running on AMD in just three days, with basically no human intervention"*, and *"Claude ported or wrote almost 100% of the kernels."* No independent account of this exists in the wiki. [Roadshow claim.]
- **Compute multipliers.** Anthropic counts *"total effective compute, which is the multiplicative product of physical capacity times the compute multipliers that we discover."* Brown's example: *"A 4x compute multiplier means you can use 25 units of compute to train the exact same model."* He says they *"stack"*, and that *"Claude will be able to discover compute multipliers entirely by itself"*. That ties to the AI-R&D acceleration METR assessed on 2026-11-05 ([[metr-anthropic-ai-rd-acceleration-2026-11-05]]).
- **Earlier hint:** Willison points to Anthropic's September postmortem, which described bugs affecting only its TPU deployments.

## Pages Updated

- [[anthropic]] — Traction Signals
- [[claude-mythos]] — Mythos 5.2 section (AMD port)
