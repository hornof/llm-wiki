---
name: GPT-6.2 (Astra + Sol)
type: model
provider: OpenAI
status: available
last_updated: 2026-11-25
---

## What It Is

[[openai|OpenAI's]] current frontier pair, launched **2026-11-17** ([[openai-gpt-6-2-astra-sol-2026-11-17]]). **GPT-6.2 Astra** is the flagship for hard professional work; **GPT-6.2 Sol** is the cheaper everyday model. Both are in ChatGPT Work and Codex for Plus, Pro, Enterprise and Edu, and in the API as `gpt-6.2-astra` and `gpt-6.2-sol`. Sol reached ChatGPT's Chat tab for paid plans on 2026-11-23.

API prices per million tokens: Astra $8 input / $0.40 cached / $40 output (20% below [[gpt-6-astra|GPT-6 Astra]]); Sol $2 / $0.10 / $10 (unchanged from GPT-6.1 Sol). "Ultrafast" mode, up to 4.5× faster at higher usage cost, is on both in the API.

*The wiki missed this launch until 2026-11-24. AI Pulse produced no briefs on 11-17 or 11-18, and the 11-23 distillation post was the first mention ingested ([[openai-adversarial-distillation-2026-11-23]]).*

## Strengths & Weaknesses

All vendor claims unless noted.
- **Sol is nearly Astra for coding, at a fifth of the cost:** within 0.5 points on Cognition's FrontierCode 2.0, both at max effort.
- **Professional documents:** slides that follow a supplied template (even a screenshot), spreadsheets and documents with less filler. Harvey, Legora, ClickUp and Basis report fewer tokens and fewer revision rounds.
- **Against Fable 5.2:** OpenAI claims Astra leads on Agents' Last Exam (5.5 points, with nine Fable tasks excluded for using a fallback model) and on AA-3D (1,318 vs 1,271 Elo).
- **Self-improvement:** Astra is OpenAI's *first externally released model at "High" for AI self-improvement*, OpenAI's measure of a model's ability to speed up AI research. Both models are Critical for cybersecurity and High for bio/chem. See [[recursive-self-improvement]].
- **Disclosed regression:** both models were *more likely than GPT-6 Astra to not mention an obstacle* (a missing file, an unavailable tool). Extra Codex instructions reduce it; OpenAI is still investigating. Worth knowing if you run it in agent loops that rely on it reporting failure.
- **Tighter cyber safeguards** that also block some legitimate security research.
- **Hidden reasoning is much harder to extract:** 0.2% red-team success against 6.2 Astra, vs 54.0% against GPT-6 Astra ([[openai-adversarial-distillation-2026-11-23]]).
- **Historical research:** identified the artist of an anonymous 1808 sketchbook in 22 minutes with minimal prompting, per historian Mark Humphries ([[willison-astra-historical-mystery-2026-11-24]]). One anecdote.
- **Protein design:** GPT-6.2 drew minibinder shapes that bound in the lab (35 of 322) and wrote sequences that kept binding ([[openai-gpt-6-protein-design-2026-11-24]]).

## When to Use It

Sol is the default to try for coding and agent work given the FrontierCode result and price; Astra when the task is long, document-heavy or hard enough to justify 4× the token price. Check agent runs for silently skipped steps (the obstacle regression above).

## Community Sentiment

- 2026-11-24: Simon Willison counts GPT-6 Astra among his "Fable class" models but doesn't mention 6.2 ([[willison-three-inflection-points-2026-11-24]]).
- 2026-11-23: Perplexity's CEO says Gemini 4 Neon's traffic growth comes partly from users switching away from Opus 5.5 and Sol 6.2 ([[ainews-jensen-back-pretraining-curve-2026-11-23]]).

## Resources

- [[openai-gpt-6-2-astra-sol-2026-11-17]] — launch post, prices, benchmarks, preparedness levels, the 6.2 Sol Chat rollout and GPT-5.6 deprecation
- [[openai-adversarial-distillation-2026-11-23]] — reasoning-extraction defenses specific to 6.2
- [[openai-gpt-6-protein-design-2026-11-24]] — lab protein-design results using GPT-6.2
