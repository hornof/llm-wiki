---
name: Training Data Quality
type: concept
maturity: active-research
last_updated: 2026-09-10
---

## Definition
Two linked ideas about training data as a first-class constraint. **(1) Quality-over-scale**: the quality and curation of training data is a more important lever than raw scale for improving model capability and efficiency (contrasted with the "scale hypothesis" — more parameters + more tokens = better models). **(2) Supply is contested and degrading**: the stock of good data is becoming both **legally contested** (provenance/IP) and **quality-degraded** (AI-generated content saturating the corpus) — making *where the data comes from* as load-bearing as *how much* there is. The proposed escape hatch for both is **synthetic experience** ([[simulation-scaling]]).

## Why It Matters
If data quality — not compute — is the binding constraint, competitive advantage shifts from compute budgets to **data curation and sourcing**. Labs that figure out what to train on (and what to discard) outperform those that simply scale. And as real, clean, rights-cleared data gets scarcer and noisier, the *data moat* reprices: proprietary clean corpora become more valuable, scraped web text becomes riskier (legally and qualitatively). This is the unifying lens under [[amazon|data-acquisition capex]], [[simulation-scaling|synthetic data]], and model-collapse risk.

## Key Evidence
- Llama 3's information compression: ~0.07 bits/token vs. ~1.5 bits/token for well-structured English — models hold a "5% resolution image" of the internet they trained on — [[thread-aakashgupta-1b-model]]
- GPT-4o runs at ~200B parameters and outperforms the original 1.8T GPT-4 — [[thread-aakashgupta-1b-model]]
- Inference costs for GPT-3.5 level performance fell 280x (2022–2024), driven by smaller, cleaner, better-architected models — [[thread-aakashgupta-1b-model]]
- Karpathy's claim (via Dwarkesh): 1B parameter model on clean data could match 1.8T frontier model — [[thread-aakashgupta-1b-model]]
- **[[dwarkesh-patel|Dwarkesh Patel]] — "Pretraining progress is mostly coming from data" (2026-09-09, dwarkesh.com, [[dailybrief-roundup-2026-09-10]])**: a **6-year decomposition of scaling-law progress** attributing the curve primarily to **data, not architecture** — *"the next bottleneck isn't a better transformer, it's text that hasn't been seen before."* The strongest analysis-side statement of this page's whole thesis: reframes frontier R&D-spend allocation from an algorithm problem to a **platform/corpus problem** (which routes into the [[#The Supply Squeeze — contested + degrading (Aug 2026)|supply-squeeze]] + model-collapse threads). *(Distinct from [[dylan-patel|Dylan Patel]] — this is Dwarkesh.)*

## The Cognitive Core Hypothesis
Karpathy proposes separating:
- **Cognitive core**: small (~1B param) model containing only algorithms for reasoning — no encyclopedic memorization
- **External memory**: retrieval system queried when facts are needed

A 1B reasoner + retrieval > 1.8T model trying to do both. The [[rag]] and [[llm-wiki-pattern]] patterns both reflect this — offload memory to structured external stores, keep the model lean.

## Frontier-Lab Annual Data Spend (May 2026)

[[data-as-moat-frontier-2026-05-30]] surfaces (via Digg, 2026-05-30) the **first wiki-captured concrete-dollars quantification** of frontier-lab data-acquisition spend:

- **$10-15B/year** annual data-acquisition spend at the frontier-lab tier
- **$20K per specialized task** at the standard data-curation surface
- **$500K per high-quality task dataset** at the upper bound
- **Supply-side is thin** — few vendors can supply at scale

**Hot take (verbatim)**: *"Frontier labs are now spending more on data than on compute. The economics flipped and nobody noticed."*

**Insightful (verbatim)**: *"Data vendors just became the real moat. If $10-15B training budgets chase $20K tasks and supply is thin, the labs building defensible data pipelines win — not the labs with the biggest GPUs."*

**Quantification of the strategic implication below**: this is the *cognitive-core-hypothesis-meets-capital-expenditure* moment. Data quality is *both* the cognitive constraint *and* now provably the largest single line-item in the frontier-lab training budget. The compounding logic: better data → better models → more revenue → more data spend → deeper moat. **Anthropic's [[anthropic-series-h-65b-965b-2026-05-28|$965B valuation]] and [[anthropic-47b-runrate-willison-2026-05-29|$47B run-rate]] both live downstream of this loop.**

Verification-pending: $10-15B source; per-lab breakdown; named vendors; trend trajectory; whether synthetic-data generation reduces the spend.

## The Supply Squeeze — contested + degrading (Aug 2026)

The 2026-08 signals reframe the *supply side* of the same constraint — the data isn't just expensive to curate, it's getting harder to source cleanly and lawfully:

- **Provenance/IP shock — data has an acquisition cost** ([[amazon|Amazon rare-books]], [[dailybrief-roundup-2026-08-17]]): 404 Media tracked scarce physical books being destructively scanned into an Amazon AI-training facility. *"The corpus your model trains on is partly determined by whoever can afford to buy it first."* Data-sourcing becomes a capitalized, contestable supply chain — copyright law lagging the arbitrage. The physical-world instantiation of the $10-15B/yr data-spend loop above.
- **Saturation / model-collapse risk — the "hall of mirrors"** (Pew Research, *"How Much of the Internet Is Written with AI?"*, 2026-08-20, [[dailybrief-roundup-2026-08-23]]): a quantitative estimate of AI-generated-content prevalence online. The structural worry the brief names: *if most new internet text is AI-generated, training-data quality collapses in 2–3 cycles — the internet stops being a mirror of human thought and becomes a hall of mirrors.* The empirical anchor for the long-discussed **model-collapse** concern. *(Pew study; the collapse timeline is inference, not measured.)*
- **The retrieval/citation side — manufactured sources feeding AI recommendations** (Perplexity cites **215,128** manufactured "best software" pages, trellner.com, [[dailybrief-roundup-2026-09-03]]): three sites generated **215K+ SEO-spam pages** that AI recommendation/citation systems (Perplexity) now surface as sources. The hall-of-mirrors problem at the **inference/retrieval** layer, not just pre-training: if the *live web an AI cites* is itself AI-manufactured spam engineered to be cited, [[rag|retrieval-grounded]] answers inherit the pollution regardless of how clean the base model's training data was. Sharpens the [[ai-vulnerability-discovery|AI-code-supply-chain]] analogy into an **information-supply-chain** attack. *(Report; per-citation impact on Perplexity answers not quantified.)*
- **The collateral cost — scraping externality on OSS infra** (git.kernel.org: **AI scrapers consume more CPU than all legitimate traffic combined**, [[simon-willison|Willison]] "Creepy crawlies", [[dailybrief-roundup-2026-09-08]]): the data-collection scramble has an **infrastructure externality** — training-data crawlers now outweigh all human traffic on core OSS hosts, pushing costs onto the volunteer-run projects being scraped. The supply-side of the squeeze isn't only *"can you buy clean data"* but *"the open web is being degraded/priced by the act of harvesting it."* *(Willison report; one host's telemetry.)*
- **The escape hatch — synthetic experience**: [[simulation-scaling]] (Joon Sung Park / Simile AI, *"10% worse, 100× cheaper, 10000× faster"*) is the direct response — if real data is contested and degrading, manufacture it. The two theses are complements: this page names the problem (supply squeeze), simulation-scaling proposes the fix (synthetic supply). Note the tension with the quality-over-scale evidence above — synthetic data trades some fidelity for volume, so *"is synthetic data clean data?"* becomes the load-bearing open question.

## Strategic Implication
"Data quality is the actual constraint. The companies winning the next phase will be the ones who figured out what to train on, and what to throw away." — @aakashgupta — [[thread-aakashgupta-1b-model]]

## Related Concepts
- [[simulation-scaling]] — the synthetic-data answer to the real-data ceiling / supply squeeze
- [[ai-margin-collapse]] — data as one more input whose economics reshape who can build frontier models
- [[amazon]] — the rare-book acquisition datapoint (provenance side)
- [[rag]] — one architecture for separating reasoning from memory
- [[llm-wiki-pattern]] — another approach to externalizing knowledge

## Resources
- [[thread-aakashgupta-1b-model]] — primary source for Karpathy's 1B claim and data quality framing
- [[data-as-moat-frontier-2026-05-30]] — $10-15B/yr frontier-lab data-acquisition spend
- [[dailybrief-roundup-2026-08-23]] — Pew "How Much of the Internet Is Written with AI?" (saturation/collapse side)
- [[dailybrief-roundup-2026-08-17]] — 404 Media Amazon rare-books investigation (provenance/IP side)
