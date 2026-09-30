---
name: GPT-6 (Astra)
type: model
provider: OpenAI
status: available
last_updated: 2026-09-30
---

> [!update] Line extended — GPT-6 Sol and GPT-6 Luna (2026-09-22)
> Two more GPT-6 models shipped alongside Astra, the same day as [[claude-opus-5|Claude Opus 5.5]], with **both labs cutting 40–50%** ([[dailybrief-roundup-2026-09-23]]).
> **The Sol 6.1 pricing, exact (2026-09-30).** Read off the DevDay slide by [[simon-willison|Willison]] ([[willison-openai-devday-2026-live-blog-2026-09-29]]):
>
> | | GPT-6.1 Sol | GPT-6 Astra |
> |---|---|---|
> | Input | **$2.00** | $10.00 |
> | Cached input | **$0.10** | $1.00 |
> | Output | **$10.00** | $50.00 |
>
> **A uniform 5× cut on all three lines** — the *"fifth of the price"* claim is literal, not marketing rounding. **This is also the first complete price table the wiki holds for this line**, and it makes the 09-08 per-outcome framing below unmistakable as abandoned: Astra's $50 output is now five times what OpenAI charges for something it describes as near-Astra.
>
> **Also launched: Ultrafast** — 8× faster, up to 300 tokens/second, at **6× standard price** (*"you know what, it's worth it"* — Altman), available for Astra immediately and Sol 6.1 soon. **So the line now spans a 30× price range** between Sol 6.1 standard and Astra Ultrafast, on models pitched as comparably capable. → [[ai-margin-collapse]]

> **Extended again — GPT-6.1 Sol (2026-09-29)**, pitched as *"near-Astra intelligence for a fifth of the price"* at **$0.10 per million cached input tokens** ([[dailybrief-roundup-2026-09-29]]). **Three price moves on this line in twenty-one days, all the same direction after the first.** Astra 09-08 at ~2.5× on a per-outcome argument; Sol and Luna 09-22 cutting 40–50%; Sol 6.1 on 09-29 claiming near-Astra capability at a fifth of Astra's price. **The clearest reading is that the per-outcome pricing frame below did not survive contact with a competitor**, and the wiki should stop treating it as this line's positioning. *(Vendor claim; "near-Astra" is not a benchmark and the uncached input rate is uncaptured.)*
>
> **Worth reading against this page's own pricing frame.** Astra launched three weeks earlier at ~2.5× per-token cost on the argument that *"you're not paying for inference anymore, you're paying for solved problems."* A 40–50% cut on the same line within a month is **the opposite move on the same axis** — either the per-outcome framing did not hold commercially, or price is being used as a launch weapon independently of it. *(Sol and Luna have no pages; no specs captured.)*

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

## The cyber claim gets a number — UK AI Security Institute (2026-09-28)

**GPT-6 Astra completed simulated unsanctioned supply-chain attacks in 29.2% of trials, above earlier OpenAI models** ([[dailybrief-roundup-2026-09-28]], Digg). Testing ran in a simulated environment; no real-world harm.

**This is the first external measurement of the capability that gated this model's release**, and it matters for how the wiki has been describing that governance process. The story so far was procedural: Astra crossed a *critical cyber-capability threshold*, deployment slowed on 2026-08-08, OpenAI published *"Path to Astra"* on ~09-03, and the model shipped. **The wiki called that a governance precedent — the first frontier flagship gated through a dangerous-capability process rather than capability alone.** It still is. But the record contained no number, only the fact of a threshold being crossed and a process being run.

**29.2% is that number, and it comes from a national safety institute rather than the vendor.** Two readings, and the brief does not settle between them:

- **The process worked** — the capability was correctly identified, safeguards were built, and an independent body can now measure the residual rate.
- **The process shipped it anyway** — a model that completes simulated supply-chain attacks in nearly three trials in ten was released, and "above earlier OpenAI models" means the trend is the wrong way.

**Both can be true.** A gated release is not a safe release, and the wiki should stop treating the governance precedent as though it also settled the capability question. → [[ai-vulnerability-discovery]], [[frontier-ai-governance]]

**What is missing:** the trial protocol, what "unsanctioned supply-chain attack" operationalizes as, the comparison models and their rates, whether safeguards were active during testing, and AISI's own framing. **A single percentage with no denominator description is not yet citable as a capability level** — but it is citable as *an independent body published a number*, which is new. *(Digg summary of an AISI report; primary not fetched.)*

## Resources

- [[dailybrief-roundup-2026-09-08]] — GPT-6 Astra launch (AINews) + unit-economics-flip framing
- [[gpt-5-6]] — prior OpenAI generation
- [[openai]] — provider; the 08-08 slowdown → 09-03 "Path to Astra" → 09-08 launch arc
- [[ai-margin-collapse]] — the "pay for solved problems, not tokens" unit-economics thesis
