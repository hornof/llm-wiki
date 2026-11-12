---
title: "[AINews] D-Day (Decision Models Day)"
type: source
medium: article
url: https://latent.space/p/ainews-d-day-decision-models-day/
ingested: 2026-11-12
---

## Summary

[[latent-space|Latent Space]]'s AINews for 2026-11-11, the "System One day" of the AI Engineer Code Summit. Leads with Google's Gemini Decision 1 and gathers the first independent numbers on it, plus Agent Arena and Artificial Analysis results for [[claude-fable-5|Fable 5.2]]. Every figure is second-hand from linked posts, which weren't fetched.

## Key Claims / Takeaways

- **Gemini Decision 1 specs** (via Google's Phil Schmid): *"up to 255 multiple-choice options"*, *"up to 1,000 questions per request, has 256K context, returns answers in 150–250 ms end to end, and attaches a confidence score to every answer"*. Built by *"A small team"* in *"about six weeks"*.
- **Google's own comparison:** *"Decision 1 beating Jev 1.14 on 5 of 7 shared benchmarks, including 92.2% vs 90.0% on JevBench."* Vendor-run.
- **Independent index:** *"Decision 1 scores 66 on the Decision Index. That ties Elephant 9B and Jev 1.14"*. Per task it *"costs $345 per 1M tasks, versus $103 for Drex Max and $156 for Jev"*, and *"Average time per task is 211 ms, slower than Jev at 92 ms"*.
- **TypeSafe's scale:** Jev's maker has its *"most notable production customers since crossing $100M ARR"*.
- **Architecture pattern (Cloudflare):** fast decision models do tool selection and log extraction, and a reasoning model only diagnoses. *"this cut six LLM calls to one and about 40K tokens to 1.8K"*.
- **Fable 5.2 on Agent Arena:** *"Fable 5.2 (Max) ranks #1 with a +30.4% net improvement across 4.7K real agentic sessions"*, about *"1.6x the score of #2, Opus 5.5 (+19.5%)"*. Median cost per task is *"$7.3, versus $5.5 for Opus 5.5"*.
- **Effort settings:** Artificial Analysis finds *"moving up a model tier beats raising effort: Opus 5.5 at xhigh outscores Sonnet 5.5 at max with 40% lower cost per task"*.

## Pages Updated

- [[jev]] — Community Sentiment
- [[gemini]] — Decision 1 paragraph
- [[claude-fable-5]] — Community Sentiment
