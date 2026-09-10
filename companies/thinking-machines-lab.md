---
name: Thinking Machines Lab
type: company
status: active
last_updated: 2026-09-10
---

## What It Is

Thinking Machines Lab is an AI research and product company founded in 2025 by Mira Murati, former CTO of OpenAI. Headquartered in San Francisco. Has raised $2B. Listed on Forbes 2026 AI 50 as one of four female-led companies on the list. Its stated mission — *"build AI that extends human will and judgment"* — leans toward **customization and human-in-the-loop** framing rather than a race to the single strongest model (surfaced via its **"The Future Worth Building Is Human"** manifesto, [[dailybrief-roundup-2026-07-11]]). First public research output — **TML-Interaction-Small** and the [[interaction-models]] framing — shipped as a limited research preview on May 11 2026.

*(Page merged 2026-09-10 from the former `thinking-machines` + `thinking-machines-lab` split — same company.)*

## Key People

- **Mira Murati** — founder and CEO; former OpenAI CTO; one of the most prominent AI leaders to leave a frontier lab and found a new venture

## Products & Research Output

- **[[inkling|Inkling]]** (2026-07-15) — the lab's **first shipped model**: an **open-weights** 975B-MoE (41B active) model released with full weights on Hugging Face + broad inference-partner support, alongside a **Tinker** fine-tuning platform (50%-off launch promo) — [[thinking-machines-inkling-open-weights-launch-2026-07-16]]. Shipping a *deliberately-not-#1, customization-first open* model is itself the positioning: *"a good open-weights base for customization."* The [[dailybrief-roundup-2026-07-16|brief]] read it as *"a credibility move, not a commodity one"*; the commercial wedge is **adaptation infrastructure** (Tinker), not just a model.
- **TML-Interaction-Small** (limited research preview, 2026-05-11) — 276B-parameter Mixture-of-Experts model with **12B active parameters** trained to handle continuous multimodal interaction (audio / video / text) natively, on time-aligned micro-turns. Beats GPT-realtime-2.0 and Gemini-3.1-flash-live on Thinking Machines' first-party interaction benchmarks (FD-bench v1.5: 77.8; Audio MultiChallenge APR: 43.4%). The headline architectural claim is **SOTA real-time voice without external voice-activity detection** — VAD absorbed into the model itself — though that specific phrasing came from Latent Space / AINews recap and should be verified against the primary blog before external citation. Wider release planned later in 2026. Establishes the lab's [[interaction-models]] thesis: interaction as a first-class primitive, not an external scaffold. — [[thinking-machines-interaction-models-2026-05-11]]

## Traction Signals

- $2B raised — [[forbes-ai-50-2026]]
- Forbes 2026 AI 50 inclusion; described as one of four female-led companies on the list
- Murati's pedigree (OpenAI CTO who oversaw ChatGPT launch) gives the lab credibility and talent draw
- **#1 on Paraform Talent Density Index, May 4 2026** — ahead of [[openai]] (#2) and [[anthropic]] (#3); [[brianlamanna-paraform-talent-density-2026-05]]
- **2026-05-11**: first public research/product output — **TML-Interaction-Small** + [[interaction-models]] framing. Establishes the lab as a research-output entity, not just a balance sheet — [[thinking-machines-interaction-models-2026-05-11]]
- **2026-08-27: co-founder Barret Zoph resurfaces at Google** ([[dailybrief-roundup-2026-08-27]], TechCrunch): Zoph — a **Thinking Machines co-founder** who was *"ousted before joining OpenAI"* — is now at **Google** (role/scope unknown). An elite-researcher churn datapoint threading the top labs (Thinking Machines → OpenAI-that-didn't-happen → Google), and a founder-departure signal for a lab whose thesis is largely its talent density. *(TechCrunch; role not detailed.)*

## Compared To

- **Frontier labs ([[openai|OpenAI]], [[anthropic|Anthropic]], [[google-deepmind|Google DeepMind]])** — Thinking Machines differentiates on **open weights + customization** ([[inkling|Inkling]] + Tinker) rather than closed frontier-model supremacy.
- **Open-weights players ([[deepseek|DeepSeek]], [[moonshot-ai|Moonshot]], [[qwen|Qwen]])** — a *US* frontier lab entering the open-weights arena those Chinese labs have led; ties to the [[ai-margin-collapse|open-weights ecosystem]] thread.

## "Resume Raises" Context

Thinking Machines Lab is one of three $1B+ raises in approximately two months (early 2026) by senior AI researchers founding new labs with no products, revenue, or customers:
1. AMI Labs (LeCun) — $1B at $3.5B (March 2026)
2. Thinking Machines Lab (Murati) — $2B at $12B
3. [[ineffable-intelligence]] (David Silver, ex-DeepMind) — $1.1B at $5.1B (April 2026)

— [[ric-rtp-david-silver-ineffable]]

## Resources

- [[forbes-ai-50-2026]] — AI 50 list inclusion, funding, female-led companies context
- [[ai-50-2026-snapshot]] — landscape context
- [[ric-rtp-david-silver-ineffable]] — "resume raises" context
- [[brianlamanna-paraform-talent-density-2026-05]] — talent-density #1 ranking (May 2026)
- [[thinking-machines-interaction-models-2026-05-11]] — TML-Interaction-Small research-preview blog (May 11 2026)
- [[thinking-machines-inkling-open-weights-launch-2026-07-16]] — Inkling open-weights + Tinker launch (Jul 2026)
- [[inkling]] — the lab's first shipped model (open-weights 975B-MoE)
- [[interaction-models]] — concept page; native multimodal real-time interaction
