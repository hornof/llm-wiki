---
name: Training Data Quality
type: concept
maturity: active-research
last_updated: 2026-05-30
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

## Frontier-Lab Annual Data Spend (May 2026)

[[data-as-moat-frontier-2026-05-30]] surfaces (via Digg, 2026-05-30) the **first wiki-captured concrete-dollars quantification** of frontier-lab data-acquisition spend:

- **$10-15B/year** annual data-acquisition spend at the frontier-lab tier
- **$20K per specialized task** at the standard data-curation surface
- **$500K per high-quality task dataset** at the upper bound
- **Supply-side is thin** — few vendors can supply at scale

**Hot take (verbatim)**: *"Frontier labs are now spending more on data than on compute. The economics flipped and nobody noticed."*

**Insightful (verbatim)**: *"Data vendors just became the real moat. If $10-15B training budgets chase $20K tasks and supply is thin, the labs building defensible data pipelines win — not the labs with the biggest GPUs."*

**Quantification of the strategic implication above**: this is the *cognitive-core-hypothesis-meets-capital-expenditure* moment. Data quality is *both* the cognitive constraint *and* now provably the largest single line-item in the frontier-lab training budget. The compounding logic: better data → better models → more revenue → more data spend → deeper moat. **Anthropic's [[anthropic-series-h-65b-965b-2026-05-28|$965B valuation]] and [[anthropic-47b-runrate-willison-2026-05-29|$47B run-rate]] both live downstream of this loop.**

Verification-pending: $10-15B source; per-lab breakdown; named vendors; trend trajectory; whether synthetic-data generation reduces the spend.

## Related Concepts
- [[rag]] — one architecture for separating reasoning from memory
- [[llm-wiki-pattern]] — another approach to externalizing knowledge

## Resources
- [[thread-aakashgupta-1b-model]] — primary source for Karpathy's 1B claim and data quality framing
