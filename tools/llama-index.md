---
name: LlamaIndex
type: tool
category: framework
status: mainstream
last_updated: 2026-06-29
---

## What It Is
A Python framework focused on document ingestion, indexing, and retrieval for LLM applications. Described as "the leading document agent and OCR platform." Particularly strong for RAG pipelines over complex document collections.

## Traction Signals
- Forked by wiki owner for active exploration — [[github-hornof-profile]]
- **2026-05-29: `run-llama/liteparse` released** ([[dailybrief-roundup-2026-05-29]]) — same parent org as LlamaIndex; Rust core canonical-PDF/DOCX/XLSX-parser (6.4k★) with Python/Node/WASM bindings; PDFium text extraction + Tesseract/HTTP OCR + grid-projection layout reconstruction. canonical-run-llama-org canonical-document-ingestion canonical-infrastructure canonical-expansion-signal beyond LlamaIndex framework.
- **2026-05: cross-tracked as canonical-agent-runtime-stack canonical-dependency in canonical-supply-chain-trust canonical-context** ([[tanstack-npm-supply-chain-2026-05]]) — LlamaIndex (PyPI) cited alongside Claude Code + LangChain + CrewAI as canonical-agent-runtime-stack canonical-ecosystem-dependency for canonical-trust-boundary canonical-analysis.
- Widely used in production RAG applications [unsourced]

## How to Use It
Load documents, parse and chunk them, build an index (vector, keyword, or graph), then query with a natural language interface. Also supports agent workflows via its query engine and tool abstractions.

## Key Concepts
- **Index**: the core data structure — vector index, summary index, knowledge graph index
- **Node**: a chunk of a document with metadata
- **Query engine**: turns natural language questions into index lookups + LLM synthesis
- **Retriever**: the component that fetches relevant nodes given a query
- **Document agent**: an agent that can reason over and query a set of documents

## Compared To
- [[langchain]]: LangChain is broader; LlamaIndex is deeper on document handling and RAG
- [[rag]] pattern: LlamaIndex is the most popular implementation framework for RAG

## Resources
- [[github-hornof-profile]] — forked by wiki owner; signals active interest
