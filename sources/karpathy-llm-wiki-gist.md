---
title: "LLM Wiki — Andrej Karpathy's Original Gist"
type: source
medium: article
url: https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f
ingested: 2026-04-21
---

## Summary
The primary source for the LLM Wiki pattern. Karpathy's original gist describing the three-layer architecture, three core operations, and supporting conventions. Intentionally abstract and modular — designed to be instantiated for a specific LLM and use case. Includes community discussion surfacing real scaling and correctness concerns.

## Key Claims / Takeaways
- Ingest updates 10-15 wiki pages per source
- log.md should use parseable prefixes: `## [YYYY-MM-DD] ingest | Title`
- Optional tool stack: qmd (search at scale), Obsidian (images), Marp (slide decks), Dataview (frontmatter queries), git (version history)
- "Humans abandon wikis because maintenance burden grows faster than value" — the core problem LLMs solve
- Schema (CLAUDE.md) is co-evolved by you and the LLM over time, not defined once
- Everything is optional and modular
- Community consensus: core insight is valid; index.md breaks at 100-500 pages (context overflow); requires secondary retrieval at scale
- @gulliveruk: scoping should be deterministic (tags, graph traversal); reasoning probabilistic — don't mix
- @ranjankumar-gh: summaries are lossy; need verification mechanisms to prevent drift
- Contradiction detection should happen at ingest time, not just during lint
- Alternative implementations: Headkey (belief graphs + confidence scores), NEBULA (human-defined entities + LLM connections), CodeDNA (opt-in wiki pointers)

## Pages Updated
- [[llm-wiki-pattern]]
- [[andrej-karpathy]]
- [[obsidian-dataview]]
- [[obsidian]]
- [[claude-code]]
- [[rag]]
