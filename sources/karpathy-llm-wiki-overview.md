---
title: "Andrej Karpathy's LLM Wiki: Create Your Own Knowledge Base"
type: source
medium: article
url: https://medium.com/@urvvil08/andrej-karpathys-llm-wiki-create-your-own-knowledge-base-8779014accd5
ingested: 2026-04-24
---

## Summary
A Medium article by Urvil Joshi (@urvvil08) summarizing Karpathy's LLM Wiki pattern in depth. Covers the compilation metaphor, three-layer architecture, three core operations, a full step-by-step setup walkthrough (Claude Code + Obsidian), the compounding property demonstrated across two source ingests, an honest RAG vs. LLM Wiki comparison, and the Vannevar Bush Memex connection. Originally ingested from a hand-written stub; re-ingested 2026-04-24 from full web clip.

## Key Claims / Takeaways
- **Karpathy's tweet**: April 2, 2026 — "Something I'm finding very useful recently: using LLMs to build personal knowledge bases for various topics of research interest. In this way, a large fraction of my recent token throughput is going less into manipulating code, and more into manipulating…"
- **Core metaphor**: raw sources compiled into a wiki the same way source code is compiled into a binary — do the work once, reuse efficiently
- **Karpathy quote**: "Obsidian is the IDE; the LLM is the programmer; the wiki is the codebase."
- **Karpathy on bookkeeping**: "The tedious part of maintaining a knowledge base is not the reading or the thinking — it's the bookkeeping. Humans abandon wikis because the maintenance burden grows faster than the value. LLMs don't get bored, don't forget to update a cross-reference, and can touch 15 files in one pass."
- **Schema file**: CLAUDE.md for Claude Code; AGENTS.md for OpenAI Codex or other agents
- **Compounding property**: second ingest (Software 2.0) automatically updated pages created by the first ingest (Bitter Lesson) and added cross-links no human created — the wiki gets denser, not just bigger
- **Setup path**: Claude Code + Obsidian; start by pasting Karpathy's gist into Claude with context about your topic; Claude asks clarifying questions then writes CLAUDE.md
- **LLM Wiki sweet spot**: ~100–500 curated sources; RAG better for millions of dynamic docs
- **Key risk**: errors propagate across linked pages (unlike RAG where hallucinations stay local to one answer) — lint is non-negotiable
- **Memex connection**: Vannevar Bush's 1945 vision of a personal curated knowledge store where connections between documents matter as much as the documents themselves; LLMs finally solve the bookkeeping problem that made Memex impractical

## Pages Updated
- [[andrej-karpathy]]
- [[llm-wiki-pattern]]
- [[rag]]
- [[obsidian]]
- [[claude-code]]
