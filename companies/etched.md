---
name: Etched
type: company
focus: specialised inference silicon; LLM attention hardcoded into hardware
status: gaining-traction
last_updated: 2026-10-15
---

## What It Is

**Etched** builds specialised inference silicon that **hardcodes LLM attention into the chip.** It left stealth on **2026-06-30** with **$800M raised, a $5B valuation and $1B in signed contracts** — then **roughly doubled to $10.3B three weeks later.**

**The whole company is one architectural bet, and it is unusually legible**: that the transformer stays dominant long enough for fixed-function attention hardware to pay back. **Against [[nvidia|Nvidia's]] general-purpose GPU, that is a counter-position rather than a competing product** — Etched is faster if the architecture holds and worthless if it does not.

It arrived inside a **one-week AI-silicon cluster** alongside OpenAI's Jalapeño, Qualcomm–Modular, and the South Korean $550B memory build-out.

## Traction Signals

- **2026-07-23: raises at $10.3B valuation** ([[dailybrief-roundup-2026-07-23]], TechCrunch): *"defies skeptics"* — roughly **2× the $5B valuation from 3 weeks earlier** (Jun 30), from big-name investors, on the inference-acceleration thesis. Etched's *"no GPUs required"* claims *"need scrutiny"* (unverified) but the round signals strong investor appetite for the inference-bottleneck bet. *(Primary not fetched.)*
- **2026-06-30: left stealth** ([[etched-llm-attention-silicon-5b-valuation-2026-06-30]]) — $800M raised, $5B valuation, **$1B in signed contracts.** The contracts are the load-bearing part: **revenue-generating validation at Nvidia-competitor scale**, not a research claim.
- **The Daily Brief's read at the time remains the sharpest framing the wiki holds:** *"Hardcoding attention in silicon sounds like the obvious move, but **it only works if you're willing to bet the company on one transformer architecture staying dominant for 5+ years.** Etched just made that bet explicit — and $1B in contracts suggests the market thinks they're right."*

## Key Concepts

- **Attention in silicon** — the transformer's attention mechanism implemented as fixed hardware rather than executed on a general-purpose GPU.
- **The five-year architecture bet** — the design only pays back if transformers remain the dominant shape. **This is the risk, stated plainly, and it is the company's own framing rather than a critic's.**

## Compared To

- **[[nvidia|Nvidia]]** — specialised attention silicon against the general-purpose incumbent. **The clearest counter-position in the wiki's hardware record.**
- **[[unconventional-ai|Unconventional AI]]** — the other specialised-silicon architectural bet the wiki tracks (theirs is 1000× energy co-design). **Two companies betting the firm on different fixed choices.**
- **OpenAI Jalapeño, Google TPU, Apple Silicon, [[colossus-2|SpaceX Colossus-2]]** — the hyperscaler custom-silicon cohort. **Etched is the only one of these selling to everyone rather than to itself**, which is a different business even where the chips are comparable.
- **Cerebras, Groq, SambaNova** — the specialised-AI-silicon vendor cohort. **What architecturally distinguishes Etched from these is not captured** and is the most useful open question on this page.

## Verification-pending

- **What distinguishes Etched from Cerebras, Groq and SambaNova.** Without this the counter-positioning claim above is a story rather than an analysis.
- **The *"no GPUs required"* claim** — flagged as needing scrutiny when the $10.3B round was reported, and never scrutinised here.
- Founders and leadership roster.
- Customer roster and signed-contract deal sizes — **the $1B is the strongest number on this page and nothing behind it is captured.**
- Chip architecture and specifications (the **Sohu** name appears in reporting; unconfirmed here).
- Funding history before the stealth exit; deployment timeline and availability.

## Resources

- [[etched-llm-attention-silicon-5b-valuation-2026-06-30]] — the stealth exit, and this page's substantive source
- [[dailybrief-roundup-2026-07-23]] — the $10.3B round
- [[silicon-vertical-integration-2026-06-24-openai-jalapeno-qualcomm-modular-cluster]] — the one-week silicon cluster
- [[dailybrief-roundup-2026-06-29]] — the South Korean memory build-out
- [[nvidia]] · [[unconventional-ai]] · [[ai-energy-efficiency]] · [[kv-cache-optimization]]

> [!note] Rewritten 2026-10-15
> The 2026-07-23 version carried **28 instances of `canonical-` filler** from an automated pass, including in the `focus:` frontmatter field. Content preserved and the 2026-07-23 round entry kept verbatim; prose rewritten and two path-form wikilinks corrected to slug-form. See lint rule 7.
