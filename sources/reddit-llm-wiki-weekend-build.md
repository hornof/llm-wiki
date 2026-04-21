---
title: "Spent a weekend actually understanding and building Karpathy's LLM Wiki"
type: source
medium: reddit-post
url: https://www.reddit.com/r/AI_Agents/comments/1sqg5ew/
ingested: 2026-04-21
---

## Summary
Practitioner post in r/AI_Agents (74 upvotes) by u/OrewaDeveloper sharing honest first-hand takeaways from actually building an LLM Wiki end-to-end. Covers what genuinely works, what breaks, and concrete use-case guidance for LLM Wiki vs. RAG. Comments add optimization tips around indexing, front-matter, and memory management.

## Key Claims / Takeaways
- Synthesis questions across documents are genuinely better than RAG — cross-document connections exist as actual wiki links
- Setup is easy: Claude Code + Obsidian + a folder
- **Lint is non-negotiable**: a wrong summary on ingest propagates across pages as "fact" — confirmed from real use
- Ingest is more token-expensive than RAG ingestion on the same source
- Sweet spot use cases: personal research <200 sources, book fan-wikis, tracking evolving topics over months, team wikis from meeting transcripts
- RAG is still better for: customer support over changing docs, legal/medical (citation traceability critical), >1000 sources or high churn
- "RAG is dead" framing is wrong — they solve different problems
- Hybrid LLM Wiki + RAG approach is being explored by OP and considered promising
- u/SprintSingh tip: global index + folder-specific index files = healthier wiki, more token-efficient ingestion/retrieval
- u/SprintSingh tip: custom front-matter per folder, LLM decision log as .md files, two-tier memory (long-term + short-term) via mem0
- u/OrewaDeveloper is also author of the Medium article and YouTube video already ingested

## Pages Updated
- [[reddit-llm-wiki-weekend-build]] (this page)
- [[llm-wiki-pattern]]
- [[rag]]
- [[orewadeveloper]]
- [[mem0]]
