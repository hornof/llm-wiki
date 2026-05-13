---
title: AINews — The End of Finetuning
type: source
medium: article
url: https://www.latent.space/p/ainews-the-end-of-finetuning
ingested: 2026-05-13
---

## Summary

Latent Space / AINews essay by **swyx**, dated May 13, 2026, arguing that the **mainstream-developer use case for finetuning has collapsed** — the immediate trigger is OpenAI's deprecation of its finetuning APIs, but swyx frames this as catch-up to a multi-year practitioner shift toward long-context prompting and constitutional-style behavioral specification. The piece is explicit that **the top 1% of AI applications still finetune** (and even RL-finetune) at scale — Cognition and Cursor are named as labs *increasing* open-model RLFT — but the bottom 99% no longer need to.

## Key Claims / Takeaways

- **Headline**: OpenAI is deprecating finetuning APIs. swyx reads this as concession, not surprise: practitioners had already moved off finetuning for most use cases.
- **Cited precedent**: Jeremy Howard flagged this transition on Fast.ai podcasts as far back as 2023.
- **Replacement strategy ("JVLP" — Just Very Long Prompts)**: extended context windows + structured behavioral specs (the post calls out **Claude's Constitution** as the canonical example) substitute for model adaptation in most cases.
- **Tier split**: "the top 1% of AI applications are building completely differently than the bottom 99%."
  - **Top 1%**: still finetune for custom ASIC strategies and **RLFT** (reinforcement-learning fine-tuning of post-trained open models). **Cognition** ($25B valuation) and **Cursor** are named as *increasing* RLFT investment.
  - **Bottom 99%**: long-context prompting + retrieval suffices.
- **Lab positions**:
  - **OpenAI**: deprecating finetuning APIs (the trigger event)
  - **Anthropic**: positioned as still investing in the surface; constitutional-style training as the canonical replacement pattern
  - **Cognition, Cursor**: increasing RLFT on open models
- **Implied use cases that remain valid for finetuning** (per swyx's framing):
  - Custom-ASIC inference economics (speed/latency at scale)
  - IP / legal lockdown that requires owning the weights
  - Specialized RLFT for agent-loop optimization (the Cognition/Cursor lane)

## Why This Matters for the Wiki

Anchors a new concept page — [[end-of-finetuning]] — that captures the **finetuning-→-long-context + constitutional-spec** transition as a *structural* shift rather than a vendor-specific announcement. The OpenAI API deprecation is the discrete trigger, but the framing matters more: the **default tool stack for AI engineering** has moved one layer up the abstraction ladder. Connects to:

- [[constitutional-ai]] — Anthropic's behavioral-spec methodology now positioned as a finetuning *replacement*, not just an alignment technique
- [[claude-md-pattern]] — owner-side analog: behavioral contracts in prose, not weight updates
- [[code-mode]] — search-and-execute tool patterns making in-context tool use cheap enough to displace finetuned tool-calling
- [[anthropic-claude-cookbook-2026-05]] — Anthropic's named primitives (PTC, Tool Search with Embeddings, Automatic Context Compaction) are the *in-context* surface this thesis predicts will dominate
- [[claude-mythos]], [[claude-opus-4-7]] — frontier base-model capability gains that close the gap finetuning was filling

Source caveat: swyx is a high-signal practitioner voice but this is **opinion synthesis**, not a survey. The "1% vs. 99%" split is rhetorical; the lab-specific positioning (Cognition / Cursor RLFT investment) is the load-bearing factual claim and should be verified before external citation.

## Pages Updated

- [[end-of-finetuning]] — new concept page
- [[openai]] — finetuning-API deprecation captured as May 2026 traction signal
- [[anthropic]] — cross-reference: constitutional-spec as in-context replacement pattern
- [[index]] — new concept entry
