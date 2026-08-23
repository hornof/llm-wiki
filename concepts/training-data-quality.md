---
name: Training-Data Quality & Supply
type: concept
maturity: emerging
last_updated: 2026-08-23
---

## Definition

The thesis that the **supply of good training data is becoming both contested and degraded** — a binding constraint on model progress that is distinct from compute or architecture. Two forces converge: **provenance/IP pressure** (who owns and can lawfully use the data) and **saturation/collapse** (as AI-generated text floods the internet, the corpus stops being a clean mirror of human thought). The proposed escape hatch is **synthetic experience** — see [[simulation-scaling]].

## Why It Matters

For anyone building or evaluating AI companies, this reprices the data moat: **real, clean, rights-cleared data is getting scarcer and more valuable, while scraped web text is getting noisier.** It bears directly on model-quality trajectories (garbage-in over successive training cycles) and on legal/cost exposure (rights-cleared corpora cost money, as [[amazon|Amazon's rare-book acquisition]] shows). It also explains why [[simulation-scaling|simulation-as-scaling-law]] is getting oxygen — if real data hits walls, manufactured data is the only lever left.

## Current State (Aug 2026)

- **Provenance/IP shock — data has an acquisition cost** ([[amazon|Amazon rare-books]], #247): 404 Media tracked scarce physical books being destructively scanned into an Amazon AI-training facility. *"The corpus your model trains on is partly determined by whoever can afford to buy it first."* Data-sourcing becomes a capitalized, contestable supply chain — copyright law lagging the arbitrage.
- **Saturation / model-collapse risk — the "hall of mirrors"** (Pew Research, *"How Much of the Internet Is Written with AI?"*, 2026-08-20, [[dailybrief-roundup-2026-08-23]]): a quantitative estimate of AI-generated-content prevalence online. The structural worry the brief names: *if most new internet text is AI-generated, training-data quality collapses in 2–3 cycles — the internet stops being a mirror of human thought and becomes a hall of mirrors.* The empirical anchor for the long-discussed **model-collapse** concern. *(Pew study; the collapse timeline is inference, not measured.)*
- **The escape hatch — synthetic experience**: [[simulation-scaling]] (Joon Sung Park / Simile AI, *"10% worse, 100× cheaper, 10000× faster"*) is the direct response — if real data is contested and degrading, manufacture it. The two theses are complements: training-data-quality names the problem, simulation-scaling proposes the fix.

## Related Concepts

- [[simulation-scaling]] — the synthetic-data answer to the real-data ceiling.
- [[ai-margin-collapse]] — data as one more input whose economics reshape who can build frontier models.
- [[reverse-information-paradox]] — who captures the learning / value from data flows.
- [[amazon]] — the rare-book acquisition datapoint (provenance side).

## Key Papers / Posts

- [[dailybrief-roundup-2026-08-23]] — Pew "How Much of the Internet Is Written with AI?" (saturation/collapse side)
- [[dailybrief-roundup-2026-08-17]] — 404 Media Amazon rare-books investigation (provenance/IP side)
