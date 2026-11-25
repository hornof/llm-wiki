---
title: "[AINews] Jensen Is Back! and OpenAI Shows Its Pretraining Curve, joined by Microsoft"
type: source
medium: article
url: https://latent.space/p/ainews-jensen-is-back-and-openai-shows-its-pretraining-curve-joined-by-microsoft/
ingested: 2026-11-24
local_source: "_raw/ainews-jensen-back-pretraining-curve-2026-11-23.txt"
---

## Summary

AINews for 2026-11-23, plus Simon Willison's GLM-5.4 note. Two follow-ups matter: Microsoft AI is the first outside lab to join Pachocki's shared-limits proposal ([[pachocki-perplexity-and-intelligence-2026-11-22]]), publishing its own score on OpenAI's evaluation set; and Z.ai shipped GLM-5.4, its first looped transformer, a week after Thinking Machines' Inkling 2 Mini used the same idea. The Huang material repeats [[nvidia-huang-reinstated-2026-11-23]] except for the hearing date.

## Key Claims / Takeaways

- **Microsoft joins** (AINews): *"With OpenAI's permission, Microsoft AI reported MAI-2 Base at 0.819 on OpenAI's eval set."* It *"lands in GPT-5.6 Sol base-model territory."* AINews: *"We’d need at least a couple more top labs to join this effort"*, *"most notably of course, Anthropic."*
- **Objections collected** (AINews, from X): post-training may be *"more than 75% of FLOPs"*, so pretraining perplexity may be the wrong pacing metric; part of the curve may come from model-generated pretraining data; and *"Anthropic redacted pretraining metrics from its METR report"*.
- **OpenAI's internal model** (AINews): *"An unreleased internal model already sits below GPT-6.2 Astra"* on the curve.
- **Huang's hearing** (AINews): *"Jensen’s Senate hearing is still due in 8 days"*, i.e. about December 1. The 11-23 brief said December 3 for the Senate and December 1 for the House. Unresolved.
- **GLM-5.4, a looped transformer** (Z.ai quoted by Willison): *"a group of weight-shared layers runs for multiple iterations"*, giving *"a deeper network without increasing the parameter count."* AINews: adapted from the GLM-5 base *"rather than pretrained from scratch"*; adds vision. Coding Plan only; API waits on safety evaluation; *"No benchmarks have been published yet"*.
- **The same idea, a week apart** (Willison): Inkling 2 Mini *"is a looped transformer, running the middle layers of the model three times for every token."*
- **Neon traffic** (AINews): Perplexity reports Gemini 4 Neon growing *"+10.6%/day in Ask"*, which Aravind Srinivas calls organic switching from Opus 5.5 and Sol 6.2.

## Pages Updated

- [[frontier-ai-governance]]
- [[z-ai]]
- [[glm-5-2]]
- [[inkling]]
