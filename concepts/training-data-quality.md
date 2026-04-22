---
name: Training Data Quality
type: concept
maturity: active-research
last_updated: 2026-04-22
---

## Definition
The idea that the quality and curation of training data is a more important lever than raw scale for improving model capability and efficiency. Contrasted with the "scale hypothesis" (more parameters + more tokens = better models).

## Why It Matters
If data quality is the binding constraint, then competitive advantage in AI shifts from compute budgets to data curation. Labs that figure out what to train on — and what to discard — will outperform those that simply scale.

## Key Evidence
- Llama 3's information compression: ~0.07 bits/token vs. ~1.5 bits/token for well-structured English — models hold a "5% resolution image" of the internet they trained on — [[thread-aakashgupta-1b-model]]
- GPT-4o runs at ~200B parameters and outperforms the original 1.8T GPT-4 — [[thread-aakashgupta-1b-model]]
- Inference costs for GPT-3.5 level performance fell 280x (2022–2024), driven by smaller, cleaner, better-architected models — [[thread-aakashgupta-1b-model]]
- Karpathy's claim (via Dwarkesh): 1B parameter model on clean data could match 1.8T frontier model — [[thread-aakashgupta-1b-model]]

## The Cognitive Core Hypothesis
Karpathy proposes separating:
- **Cognitive core**: small (~1B param) model containing only algorithms for reasoning — no encyclopedic memorization
- **External memory**: retrieval system queried when facts are needed

A 1B reasoner + retrieval > 1.8T model trying to do both. The [[rag]] and [[llm-wiki-pattern]] patterns both reflect this — offload memory to structured external stores, keep the model lean.

## Strategic Implication
"Data quality is the actual constraint. The companies winning the next phase will be the ones who figured out what to train on, and what to throw away." — @aakashgupta — [[thread-aakashgupta-1b-model]]

## Related Concepts
- [[rag]] — one architecture for separating reasoning from memory
- [[llm-wiki-pattern]] — another approach to externalizing knowledge

## Resources
- [[thread-aakashgupta-1b-model]] — primary source for Karpathy's 1B claim and data quality framing
