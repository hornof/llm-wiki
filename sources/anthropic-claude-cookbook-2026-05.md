---
title: Claude Cookbook (Anthropic platform site)
type: source
medium: article
url: https://platform.claude.com/cookbook/
ingested: 2026-05-11
---

## Summary

Official Anthropic catalog of **81 practical guides across 15 categories** for building with Claude — surfaced into the wiki via [[bibryam]]'s May 11 2026 X post amplifying the resource. Covers agents, tool use, RAG, evals, multimodal apps, [[claude-code]] skills, integrations, and production workflows. Functions as Anthropic's first-party developer-onboarding catalog adjacent to (but distinct from) [[anthropic-academy-courses-catalog-2026-05]].

## Key Claims / Takeaways

- **Scale**: 81 guides, 15 categories — large enough to function as a navigable reference, not just a sampler. (Bibryam's count, captured from cookbook landing-page surface.)
- **Curated guide highlights** (from the cookbook landing page itself):
  - **Programmatic tool calling (PTC)**: Claude writes code that calls tools programmatically in the code-execution environment. **Architecturally adjacent to [[code-mode]]** — same shape (agent writes code that calls tools through a runtime; tool definitions enter context only at import lines). Confirms that the [[code-mode]] pattern Anthropic published in November 2025 has propagated into the official cookbook as a named primitive.
  - **Tool search with embeddings**: scale Claude applications to thousands of tools using semantic embeddings for dynamic tool discovery. **Companion technique to PTC** for the MCP-scaling problem — same surface as [[akshay-pachaar-mcp-vs-cli-2026-05-09]] discusses (search+execute pattern reducing Cloudflare tool-context from 1.17M → 1K tokens, 98.7% reduction).
  - **Automatic context compaction**: manage context limits in long-running agentic workflows by automatically compressing conversation history. Production-pattern primitive for long-running agents — same problem [[claude-cowork-cheatsheet-2026-05-07]] surfaces under Scheduled Tasks and Dispatch.
- **Companion to [[anthropic-academy-courses-catalog-2026-05]]**: the Academy is structured courses (16 entries surfaced May 5 2026); the Cookbook is structured snippets/recipes (81 entries surfaced May 11 2026). Two complementary first-party self-serve learning surfaces.

## Why This Matters for the Wiki

- **Confirms [[code-mode]] / programmatic tool calling has landed as official Anthropic guidance** (not just a Nov 2025 blog post / Akshay Pachaar's May 9 practitioner reframing).
- **Maps the production-pattern catalog** for the next round of [[claude-code]] / [[claude-agent-sdk]] tutorials and skills. Useful as an index when looking for canonical Anthropic-blessed examples on a specific pattern.
- **No new entity pages required** — this is a reference-catalog source. The interesting entries (PTC, tool search, compaction) all already have concept-level coverage in the wiki under [[code-mode]], [[mcp]], and [[akshay-pachaar-mcp-vs-cli-2026-05-09]].

## Pages Updated

- [[code-mode]] — Programmatic Tool Calling confirmed as named cookbook primitive (cross-reference)
- [[anthropic]] — official cookbook surface added to Resources
- bibryam (one-off X post surfacing; not a tracked person — no entity page created)
