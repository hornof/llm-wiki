---
name: GPT-6 (Astra)
type: model
provider: OpenAI
status: available
last_updated: 2026-09-13
---

## What It Is

**GPT-6**, codenamed **Astra**, is [[openai|OpenAI's]] frontier flagship, launched **2026-09-08** and billed by AINews as *"OpenAI's biggest LLM launch of all time"* ([[dailybrief-roundup-2026-09-08]]). "Astra" is the same model line OpenAI put through a public **Preparedness-Framework** process earlier: it **slowed deployment on 2026-08-08** after Astra crossed a *critical cyber-capability threshold* (a model that can independently identify and execute cyberattacks), published **"Path to Astra: critical capabilities and frontier safeguards" on ~09-03**, and now ships the full model. The launch is thus the first frontier flagship whose release was explicitly **gated through a dangerous-capability governance process** rather than shipped on capability alone.

## Strengths & Weaknesses

- **Claimed SOTA on computer-use and coding** (AINews headline) — positions Astra at the top of the agentic-tooling + coding-agent surface where [[claude-code]] / [[claude-fable-5|Fable]] and [[gpt-5-6|GPT-5.6]] compete.
- **Unit-economics flip**: **~2.5× token cost** vs the prior generation, but **cheaper *per task*** — the framing being *"you're not paying for inference anymore, you're paying for solved problems"* (see [[ai-margin-collapse]]). Higher per-token price, fewer tokens/steps to a correct outcome.
- **Cyber capability is the safety-gating axis** — the Preparedness process that slowed it (08-08) is the reason its launch is a governance precedent; pairs with OpenAI's [[openai|Daybreak / Daybreak for Frontline Defenders]] access-controlled cyber programs.
- *Benchmarks, context window, pricing ladder, and modality details not yet captured — headline-level only (AINews). Verify before external citation.*

## When to Use It

- Agentic **computer-use** and **coding** workflows where per-task cost (not per-token price) is the metric that matters — the Spotify-Portal-style *"route the hard reasoning to the frontier"* pattern ([[ai-margin-collapse]]).

## Community Sentiment

- Launch framed as OpenAI's largest ever; Latent Space also shipped a *"Frontier AEO Tracker: What Astra Chooses"* (AI-Enabled-Outcomes analysis across frontier models) as a GTM-decision aid. Early; independent capability/pricing assessments pending.

## Capability receipt — a 27-minute route-planning session (2026-09-12)

The first concrete, externally-observed task trace on this page, via [[simon-willison|Willison]] ([[dailybrief-roundup-2026-09-13]]): using **ChatGPT Work**, Astra went from a street address to **5K and 10K route visualizations plus GPX/GeoJSON output** over a **27-minute multimodal reasoning session** — sustained tool use against map data, not a single-shot answer.

Useful for two reasons beyond the demo. It is a **long-horizon spatial-reasoning** trace, which is harder to fake than a benchmark score; and the 27-minute duration is itself the datapoint — it is the kind of run the [[ai-margin-collapse|"pay for solved problems, not tokens"]] pricing frame is built to justify. Modest scope, but this page has been headline-level since launch and needed a real one.

*(Practitioner write-up of a single session; not a benchmark.)*

## Resources

- [[dailybrief-roundup-2026-09-08]] — GPT-6 Astra launch (AINews) + unit-economics-flip framing
- [[gpt-5-6]] — prior OpenAI generation
- [[openai]] — provider; the 08-08 slowdown → 09-03 "Path to Astra" → 09-08 launch arc
- [[ai-margin-collapse]] — the "pay for solved problems, not tokens" unit-economics thesis
