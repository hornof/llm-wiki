---
name: Context7
type: tool
category: api
status: gaining-traction
last_updated: 2026-07-12
---

## What It Is

**Context7** (by **Upstash**) is *"Up-to-date Code Docs For Any Prompt"* — an [[mcp|MCP]] server (and CLI/skill) that fetches **real-time, version-specific library documentation and code examples** and injects them into a coding agent's context *before* generation, so the model doesn't hallucinate APIs or lean on stale training data. It is the "Docs Fetcher / live library docs" tile (Developers dept) in [[charliejhills-claude-whole-company-42-skills-2026-07-12|Charlie Hills' "Claude as a company" chart]].

## Traction Signals

- **~59k GitHub stars / ~2.8k forks** (per [github.com/upstash/context7](https://github.com/upstash/context7), 2026-07-12).
- **Broad client integration**: Cursor, [[claude-code|Claude Code]], OpenCode, and 30+ additional MCP clients — one of the more widely-wired MCP servers, alongside [[playwright-mcp|Playwright MCP]].
- Maintained by Upstash (a commercial serverless-data vendor), MIT-licensed — a durable-maintenance signal.

## How to Use It

- **MCP mode**: point the client at `https://mcp.context7.com/mcp` with a `CONTEXT7_API_KEY` header; server package `@upstash/context7-mcp`.
- **CLI / Skills mode**: `npx ctx7 setup` (OAuth, auto-generates an API key); CLI `ctx7`.
- Exposes two tools — `resolve-library-id` and `query-docs`; target a library with slash syntax, e.g. `/supabase/supabase`.

## Key Concepts

- **Library ID resolution** — resolve a human name to a canonical library ID, then query version-aware docs.
- **Version-aware retrieval** — docs pinned to the version the project actually uses, not a training-cutoff snapshot.
- **Docs-in-context vs. training memory** — a retrieval answer to the "model's knowledge is stale" problem, complementary to the [[okf|OKF]] knowledge-file approach.

## Compared To

- **[[playwright-mcp|Playwright MCP]]** — both are widely-integrated MCP servers, but Context7 supplies *knowledge* (live docs) where Playwright supplies *action* (browser control).
- **[[superpowers]] / [[claude-mem]]** — sibling third-party entries in the Claude-skills ecosystem; Context7 is the docs-retrieval specialist.

## Resources
- [github.com/upstash/context7](https://github.com/upstash/context7) — MIT; Upstash
- [[charliejhills-claude-whole-company-42-skills-2026-07-12]] — surfaced as the Developers "Docs Fetcher" tile
