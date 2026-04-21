---
name: RAG (Retrieval-Augmented Generation)
type: concept
maturity: mainstream
last_updated: 2026-04-21
---

## Definition
A technique where an LLM's response is grounded by retrieving relevant chunks from a document corpus at query time, rather than relying solely on the model's training data. The retrieved chunks are injected into the prompt as context.

## Why It Matters
Solves the knowledge cutoff and hallucination problems for domain-specific or up-to-date content. The dominant pattern for production LLM applications over large document collections.

## Current State
Mainstream in production AI systems. Well-understood toolchain: embeddings → vector store → retrieval → LLM. Active research in improving retrieval quality (reranking, hybrid search, late chunking).

## Strengths & Weaknesses
**Strengths**: scales to millions of documents; hallucinations isolated to a single answer; documents stay authoritative and unmodified; good for dynamic/frequently-updated corpora.

**Weaknesses**: stateless — no knowledge compounds across queries; retrieval quality degrades with poorly chunked or ambiguous content; synthesis across many documents requires many retrieval calls.

## When to Use It
- Customer support over constantly-updated docs
- Legal/medical search where citation traceability is critical
- Anything with >1000 sources or high source churn
- Large, dynamic document collections where retrieval at query time is practical

## Related Concepts
- [[llm-wiki-pattern]] — compilation-time synthesis vs. RAG's query-time retrieval; complementary rather than competing for different scale regimes

## Resources
- [[karpathy-llm-wiki-overview]] — contains LLM Wiki vs. RAG comparison table
- [[reddit-llm-wiki-weekend-build]] — practitioner comparison with concrete use-case breakdown
