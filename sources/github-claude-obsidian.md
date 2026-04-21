---
title: "claude-obsidian — AgriciDaniel/claude-obsidian"
type: source
medium: github-repo
url: https://github.com/AgriciDaniel/claude-obsidian
ingested: 2026-04-21
---

## Summary
A full Claude Code plugin implementing Karpathy's LLM Wiki pattern with Obsidian. 10 skills covering ingest, query, lint, save, autoresearch, and canvas. Remarkable traction: 2,626 stars and 307 forks in ~2 weeks. Built by Agrici Daniel. Extends the base pattern with a hot cache (session memory), autonomous research loop, visual canvas layer, and MCP integration.

## Key Claims / Takeaways
- **Hot cache** (`wiki/hot.md`): updated at end of every session; next session starts with full recent context — solves cold-start problem
- **Batch ingestion**: parallel agents for processing multiple sources simultaneously
- **/autoresearch**: 3-round autonomous research loop; configurable via `program.md` (preferred sources, confidence rules, max rounds)
- **/canvas**: visual layer — add images, PDFs, notes, zones; companion claude-canvas adds 12 templates and 6 layout algorithms
- **Contradiction flagging**: `[!contradiction]` callouts with cited sources written at ingest time — not deferred to lint
- **8-category lint** vs. simpler approaches
- **Six wiki modes**: Website, GitHub, Business, Personal, Research, Book/Course — can be combined
- **Cross-project power move**: point any Claude Code project at the vault via CLAUDE.md so all projects draw from the same knowledge base
- **MCP integration**: Option A (Local REST API + mcp-obsidian) or Option B (filesystem mcpvault, no plugin needed)
- **Obsidian Bases** (native, v1.9.10+, August 2025) is now the primary dashboard — Dataview is legacy fallback
- **Obsidian Web Clipper** browser extension sends web pages directly to `.raw/` in one click — solves URL ingest friction
- Multi-model support: Claude, Gemini, Codex, Cursor, Windsurf
- Community: 2,800+ member Skool community, YouTube tutorials, blog deep dive

## Pages Updated
- [[claude-obsidian]]
- [[agrici-daniel]]
- [[hot-cache]]
- [[claude-canvas]]
- [[obsidian]]
- [[obsidian-dataview]]
- [[llm-wiki-pattern]]
