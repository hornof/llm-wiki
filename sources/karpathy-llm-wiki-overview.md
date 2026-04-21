---
title: "Andrej Karpathy's LLM Wiki: Create Your Own Knowledge Base"
type: source
medium: article
url: https://medium.com/@urvvil08/andrej-karpathys-llm-wiki-create-your-own-knowledge-base-8779014accd5
ingested: 2026-04-21
---

## Summary
A Medium article summarizing Andrej Karpathy's LLM Wiki pattern — building a persistent, LLM-maintained knowledge base structured as a compiled wiki rather than raw document retrieval. Covers the three-layer architecture, three core operations, and how it compares to RAG.

## Key Claims / Takeaways
- Core metaphor: raw sources are "compiled" into a wiki the same way source code is compiled into a binary — do the work once, reuse efficiently
- Karpathy quote: "Obsidian is the IDE; the LLM is the programmer; the wiki is the codebase."
- Three operations: Ingest, Query, Lint
- LLM Wiki sweet spot is 100–500 curated sources; RAG is better for millions of dynamic docs
- Key risk: errors in the wiki can propagate across linked pages (unlike RAG where hallucinations are isolated)
- Connects to Vannevar Bush's 1945 Memex vision
- Recommended tooling: Claude Code + Obsidian

## Pages Updated
- [[andrej-karpathy]]
- [[llm-wiki-pattern]]
- [[rag]]
- [[obsidian]]
- [[claude-code]]
