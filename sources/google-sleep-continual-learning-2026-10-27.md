---
title: "The Sleep framework: A new way for LLMs to retain knowledge in continual learning"
type: source
medium: article
url: https://research.google/blog/the-sleep-framework-a-new-way-for-llms-to-retain-knowledge-in-continual-learning/
ingested: 2026-10-28
---

## Summary

Google Research (Ali Behrouz and Vahab Mirrokni, 2026-10-27) describes a training cycle that alternates a "wake" phase, where the model works and keeps new information in short-term memory, with an offline "sleep" phase, where it writes that information into its weights. In sleep, the model consolidates memory into reserved Mixture-of-Experts blocks and then "dreams": it generates practice examples, keeps the best ones and fine-tunes on them. **It targets catastrophic forgetting**, where learning new material degrades old abilities. Research blog post; the paper wasn't read. The authors note the neuroscience terms are analogies.

## Key Claims / Takeaways

- **The problem:** deployed models *"remain largely static, operating with a fixed knowledge cutoff date"*. Updating them risks catastrophic forgetting, and in-context learning forgets once the session ends.
- **The mechanism:** in sleep the model *"unlocks pre-allocated Mixture-of-Experts (MoE) memory blocks and updates its numerical weights using self-generated practice examples."* The authors say it works *"entirely within a fixed model architecture and human-defined training rules."*
- **Results the post reports:**
  - On unseen languages (Manchu, Kalamang), it held *"a near-zero performance drop"* where ICL, Cartridges and SFT forgot.
  - On long-context BABILong it showed *"near-perfect scaling up to 10M tokens"*.
  - On knowledge incorporation (SQuAD/CPT) it scored *"48.9% on single-task and 46.2% on CPT evaluations"*.
  - On math (AIME 24/25 and HMMT 25) it scored *"79.2%, 69.0%, and 46.1%, respectively"*.
- **Same word, different thing:** Anthropic's Managed Agents "dreaming" is one agent writing memories from another's work ([[latent-space-opus-5-5-brain-hands-2026-10-27]]). Google's is weight updates. One changes context, the other changes the model.

## Pages Updated

- [[end-of-finetuning]]: new section
