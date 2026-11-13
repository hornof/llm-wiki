---
title: "Jensen Huang resigns after 33 years leading NVIDIA"
type: source
medium: article
url: https://latent.space/p/ainews-jensen-huang-resigns-after-33-years-leading-nvidia/
ingested: 2026-11-13
---

## Summary

Latent Space's AINews issue for 2026-11-12 (covering 11-11 to 11-12). The headline is Nvidia's CEO change, already ingested from Nvidia's release in [[nvidia-ceo-transition-2026-11-12]]; this issue adds the SEC filing date and the board's investigation. The more useful news for the wiki is lower down: **Google launched Gemini 4 Hydrogen**, a fast tier beside Carbon and Argon, which the wiki hadn't recorded. It also carries a claim that Chinese models' weights show they were initialized on Blackwell GPUs, and one-line items on OpenAI's Daybreak products and Anthropic's IPO. AINews aggregates tweets and Reddit; the figures below are as it reports them, mostly vendor claims.

## Key Claims / Takeaways

- **Gemini 4 Hydrogen (Google's claims):** *"a speed-first model positioned alongside Carbon and Argon."* It *"completes tasks 2.5x faster than Gemini 3.8 Flash"*. Price *"$1.50/$7.50 per million input/output tokens, with a 95% discount on cached input"*, *"four thinking levels (low, medium, high and xhigh) and a 1M context window."* Google reports *"57% on Terminal-Bench 4.0"*.
- **Hydrogen availability:** *"available on all Gemini API tiers, including a free tier in AI Studio. It is the default model in Search AI Mode"*. In Antigravity, *"Carbon plans while Hydrogen writes and tests code"*, which Google says reaches near-Carbon results *"with 24% less quota"*.
- **Hydrogen, independent measurements (Artificial Analysis):** at xhigh it *"scores 54, one point behind Claude Sonnet 5.5 (max) and GPT-6.1 Sol (max)."* It has *"an 8% hallucination rate on AA-Omniscience, versus 43% for Sonnet and 52% for Sol."* On Terminal-Bench 4.0 AA measured *"54% on Terminal-Bench 4.0 at both high and xhigh, below Sonnet at 64% and Sol at 56%."*
- **Hydrogen pricing complaint:** Willison *"says Hydrogen is only a 25% discount on the Carbon/Argon token price, though those models reportedly double in price on Dec 1"*. A Reddit commenter compared it with *"prior Flash-like pricing around $0.20/$1.00"*.
- **Nvidia transition details:** *"The SEC filing dates the board’s acceptance to November 11. NVIDIA announced the change on November 12."* The independent directors appointed outside counsel on November 10 *"to conduct the investigation they announced on November 8."* The board *"has opened a search."*
- **Blackwell fingerprints in Chinese weights:** Will Depue *"reports six Chinese models, including DeepSeek-V4-Pro, Kimi K3 and MiniMax-M3, were initialized on Blackwell systems"*. He estimates *"2–3K Blackwells each for the largest runs."* Critics answer that this is *"about 6MW, a small fraction of China's roughly 24GW of installed compute"*, so the result could mean export controls are working. Unreviewed.
- **OpenAI:** *"OpenAI launched Daybreak Defense Factory and Daybreak Red Team"*. See [[openai-daybreak-red-team-defense-factory-2026-11-12]].
- **Anthropic IPO:** *"pricing is reportedly set for next Wednesday"* (a tweet by Theo; not from Anthropic). The roadshow claims Claude got one of its models doing prompt processing on AMD *"in about 3 days with almost no human intervention"*.
- **Also listed, not followed up:** Mercor's OWE-Bench (*"Fable 5.2 at 54.6%, GPT-6 Astra at 44.2% and Opus 5.5 at 41.6%"*), NVIDIA's Alpamayo 2 Edge self-driving model, Baidu's ERNIE 5.5 Flash, and Smitline, an MCP tool that lets Claude Code place phone calls.

## Pages Updated

- [[gemini]] — Hydrogen row in the model table
- [[google]] — current models, Traction Signals
- [[nvidia]] — Traction Signals
