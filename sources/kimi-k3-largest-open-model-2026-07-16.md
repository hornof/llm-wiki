---
title: "Kimi K3 2.8T-A50B — Moonshot's 'largest open model ever' at Sonnet pricing (Latent Space + Willison, 2026-07-16)"
type: source
medium: article
url: https://simonwillison.net/2026/Jul/16/kimi-k3/
ingested: 2026-07-17
---

## Summary

[[moonshot-ai|Moonshot AI]] releases **[[kimi-k3|Kimi K3]]** (2026-07-16) — a **2.8-trillion-parameter MoE (~50B active)**, billed as *"the largest open model ever released,"* with weights **promised by 2026-07-27** (API/website/OpenRouter now). The [Latent Space brief](https://www.latent.space/p/ainews-kimi-k3-28t-a50b-the-largest) frames it as *"Opus-class at Sonnet pricing"*; [[simon-willison|Simon Willison]]'s companion analysis grounds the specifics and the hype. Anchor source for [[kimi-k3]].

## Key Claims / Takeaways

- **Specs**: 2.8T total params (MoE, ~50B active). Open-weight release **promised by 2026-07-27** — not yet dropped as of 2026-07-16 (website + API + OpenRouter only).
- **Capability (Moonshot self-benchmarks — caveat)**: *"mostly beating Claude Opus 4.8 max and GPT-5.5 high,"* but **losing to [[claude-fable-5|Fable 5]] and GPT-5.6 Sol**. Independent: **Artificial Analysis Elo 1547**; **#1 on Arena.ai's Frontend Code arena**.
- **Pricing**: **$3/M in, $15/M out** — matches [[claude-sonnet-5|Sonnet]] tier; a **big jump up from K2.6's $0.95/$4**. "Sonnet pricing" is a price *increase* for Moonshot, sold against the capability gain.
- **"3T-class" tell** (Willison): rounding **2.8T → 3T** for marketing — *"past the point where parameter count signals capability."*
- **Pelican benchmark**: valid SVG at **~25¢** (16,658 output tokens, 13,241 reasoning); Willison — a joke benchmark that still exposes real model characteristics, though it *"doesn't touch… agentic tool calling."*

## Why it matters

- **Open-weight scaling inflection** for the [[ai-margin-collapse]] thesis: an open (soon) model reaching upper-tier capability at Sonnet-level pricing → *"margin compression across the mid-market LLM API stack."* Enters the arena with [[deepseek|DeepSeek]] / [[qwen|Qwen]] and now [[inkling|Thinking Machines' Inkling]].
- **Two open-weights frontier-ish releases in 2 days** (Inkling 07-15 + Kimi K3 07-16) — the "whose weights do we build on" decision is heating up.

## Pages Updated
- [[kimi-k3]] (new), [[moonshot-ai]]

## Verification-pending
- Actual open-weight drop + license terms on/after 2026-07-27 (currently "promised").
- Active-parameter count ("A50B" per title; Willison's post doesn't state it) and context window.
- Independent (non-Moonshot) capability replication beyond Artificial Analysis Elo.
