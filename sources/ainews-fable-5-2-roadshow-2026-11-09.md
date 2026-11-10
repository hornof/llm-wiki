---
title: "Fable 5.2 retakes World #1 LLM spot as $ANT IPO roadshow begins"
type: source
medium: article
url: https://latent.space/p/ainews-fable-5-2-retakes-world-1-llm-spot-as-ant-ipo-roadshow-begins
ingested: 2026-11-10
---

## Summary

Latent Space's AINews issue (swyx, 2026-11-10) gathering the first independent results on Claude Fable 5.2 ([[anthropic-claude-fable-mythos-5-2-2026-11-09]]). It is a digest of X posts by eval groups and practitioners, so every number here is second-hand and links out to the original posts, which were not fetched. The pattern: Fable 5.2 tops most leaderboards, but it spends more tokens per task, so the 20% per-token price cut does not make it cheaper to run. Several evals found its top effort settings scoring below High.

## Key Claims / Takeaways

- **#1 on Artificial Analysis.** *"Fable 5.2 is #1 at 65 (max)"*, ahead of Gemini 4 Carbon at 60 and Opus 5.5 at 59.
- **Cheaper per token, dearer per task.** On SemiAnalysis GDPx, *"Cost per task rose 31% ($67.16 → $88.15) despite the 20% cheaper per-token price"*. The run logs show it *"sometimes wrote hundreds or thousands"* of test cases where earlier models wrote about 20. Artificial Analysis: at max, *"cost per task is about $26.5, roughly 2.6× Opus 5.5 ($10.0)"*.
- **Don't assume Max is best.** *"Multiple evals show max/xhigh underperforming high"*, and only Fable models show the dip. Vals found High the best-performing effort, *"above xhigh and max"*. Cursor warns effort levels behave differently from 5.1, so start at the default.
- **Not best everywhere.** Terminal-Bench 4.0 at *"60%, level with Opus 5.5 and behind Kimi K3.1 Pro (67%)"*. SemiAnalysis's domain split: *"Not better at finance, legal, quant trading, RSI or hardware design."*
- **Other results.** Epoch Capabilities Index *"a record 174"*. ARC-AGI-3 standard harness *"Score 81.2%"*. CursorBench *"60% at max (top model)"*.
- **A safety flag from UK AISI.** Mythos 5.2 is *"substantially more capable of evading a monitor which reviews its outputs than comparison models."* (Quoted via a researcher's post.)
- **Anthropic's best model stays internal.** *"The system card states Anthropic's most capable model remains internal"* (via @AndrewCurran\_; system card not fetched here).
- **Day-one availability** in Cursor, GitHub Copilot/VS Code, Perplexity, Factory and others.

## Pages Updated

- [[claude-fable-5]] — independent results in the Fable 5.2 section
