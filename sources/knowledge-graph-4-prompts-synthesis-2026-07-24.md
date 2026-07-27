---
title: "Graph Engineering: 4 Models to 4 Prompts — independent synthesis (KG construction with Claude structured outputs)"
type: source
medium: paper
url:
ingested: 2026-07-27
---

## Summary

An **independent, study-oriented synthesis paper** (PDF, 7pp, dated ~2026-07-24; `_raw/Graph-Engineering-4-Models-to-4-Prompts.pdf`) showing how **four Claude prompts with structured outputs replace the four trained models** a classical knowledge-graph pipeline required (NER, relation classifier, entity-resolution engine, summarizer). Built entirely on Anthropic's public **Knowledge Graph Construction Cookbook**; explicitly **not affiliated with or endorsed by Anthropic** (the cover carries a spurious "Boris Cherny" byline that the document's own acknowledgment contradicts — treat as an anonymous compiled reference, **not** an Anthropic/Cherny primary). Complements the [[graph-engineering-loops-to-graphs-synthesis-2026-07-24|loops-to-graphs synthesis]] — this is the "knowledge graph as shared memory" layer, in depth. *(Primary fetched — full text.)*

## Key Claims / Takeaways

- **Four prompts replace four trained systems**: (1) **Extraction** (Haiku) — one schema-constrained call pulls typed entities + subject-predicate-object triples, replacing NER *and* the relation classifier; (2) **Resolution** (Sonnet) — clusters surface-form variants into canonical nodes using the one-line descriptions as disambiguation context, catching *"Edwin Aldrin" → "Buzz Aldrin"* (zero character overlap) that string similarity misses; (3) **Summarization** (Sonnet) — pools mentions + graph neighborhood into hub-entity profiles no single doc contains; (4) **Querying** (Sonnet) — reasons over a serialized k-hop subgraph with edge-level citations.
- **The Pydantic schema is the only training data** — the `output_format` structured-output contract guarantees valid typed objects (*"ten thousand documents → ten thousand valid ExtractedGraph objects, zero parse errors"*). Adaptation cost drops from *weeks of labeling + training per domain* to *hours of prompt tuning* that works across any domain the model can read.
- **Model split by economics**: Haiku for high-volume extraction (10K docs ≈ single-digit dollars w/ prompt caching + Batches API 50% off); Sonnet for the judgment-heavy resolution/summarization/query calls that run far fewer times.
- **Apollo-corpus eval**: 6 docs → 36 raw entities/34 relations → resolved to 22 canonical nodes. Extraction F1 0.55–0.71 with **precision 1.00, recall 0.38–0.55** — deliberately favoring precision, because a wrong entity spawns wrong relations that propagate through multi-hop reasoning (false positives are more damaging than false negatives).
- **k=2 hops** is the multi-hop sweet spot (k=1 misses indirect links; k=3 blows the context window).
- **Integration with the 5 agent patterns**: KG as **shared memory** (workers read/write subgraphs; orchestrator context stays small), **grounding layer** (evaluator fact-checks a claimed triple against real edges + provenance — estimation → fact-checking), **persistent world model** (overnight loops resolve new docs against the canonical set; *"the agent forgets, the graph does not"*).
- **When NOT to use a KG**: single-doc QA (RAG), multi-doc single-hop (RAG+rerank). A KG earns its cost only for multi-hop chaining, multi-agent shared state, or evaluator ground-truth/provenance.
- **Production checklist failure modes**: no gold set → blind prompt changes; no resolution fallback → silent entity loss; no provenance → ungrounded answers; no connectivity monitor → fragmented graph.

## Pages Updated
- [[graph-engineering]]
