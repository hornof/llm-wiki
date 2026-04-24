---
type: meta
title: "Lint Report 2026-04-24"
created: 2026-04-24
updated: 2026-04-24
tags: [meta, lint]
status: needs-review
---

# Lint Report: 2026-04-24

## Summary
- Pages scanned: 54 (tools: 11, concepts: 8, people: 7, companies: 3, models: 1, topics: 1, sources: 19, owner: 2)
- Issues found: 10
- Auto-fixed: 0
- Needs owner review: 10

---

## 1. Orphan Entity Pages (no inbound wikilinks)

- `owner/profile.md` — content exists but `[[owner-profile]]` in index.md resolves to the empty root stub, not this file. The actual content is unreachable.
- `owner/publications.md` — same issue.

**Root cause**: Two empty 0-byte stubs exist at root (`owner-profile.md`, `owner-publications.md`). Obsidian resolves `[[owner-profile]]` to those stubs, bypassing the real content in `owner/`.

**Suggested fix**: Delete the empty root stubs. Then update `index.md` links to `[[owner/profile]]` and `[[owner/publications]]` (path-qualified) so Obsidian resolves correctly. (Obsidian supports path-qualified wikilinks.)

---

## 2. Orphan Source Page

- `[[how-to-learn-claude-infographic]]` — source page exists but is not linked from `index.md` or any entity page.

**Suggested fix**: Add to `index.md` under Sources, or link from `[[claude-code]]`.

---

## 3. Dead Wikilinks (meaningful)

- `[[mcp]]` in `topics/agentic-ai.md:20` — no `concepts/mcp.md` or `tools/mcp.md` exists. MCP is mentioned in several pages and warranted its own page (also referenced from `tools/claude-code.md`).
- `[[learn-agentic-ai]]` in `sources/github-hornof-profile.md:24` — references a GitHub repo the owner forked; no wiki page exists.

**Not flagged** (intentional/template):
- `[[wikilink]]` and `[[Page Name]]` in `tools/obsidian.md` — example syntax in prose, not real links
- `[[LLM Wiki Pattern]]` in `CLAUDE.md` — intentional negative example of wrong wikilink format
- `[[agi-debate.canvas]]` in `index.md` — resolves correctly to `canvases/agi-debate.canvas`

---

## 4. Index Duplicate

- `[[hot-cache]]` appears **twice** in `index.md` under Concepts & Techniques (lines ~19 and ~25).

**Suggested fix**: Delete the duplicate line.

---

## 5. Unprocessed `_raw/` Files

Two `_raw/` files have no matching `sources/` page:

- `_raw/Luke Hornof 1.md` — LinkedIn profile (url: linkedin.com/in/lukehornof). Log entry says "Luke Hornof LinkedIn" was ingested, but no `sources/` page exists. The data may have been merged directly into `owner/profile.md` — verify and either file a source page or confirm it's intentionally sourceless.
- `_raw/Post by @phosphenq on X.md` (status/2047346402435518627) — **different tweet** from the ingested `thread-phosphenq-karpathy-video` (which is status/2046612983007039794). This one is about a Yann LeCun 2-hour lecture, promoting his anti-LLM/pro-world-models thesis. Has not been ingested.

Already covered (not flagged):
- `_raw/Thread by @phosphenq.md` — same URL as the ingested `thread-phosphenq-karpathy-video`

---

## 6. Missing Pages Worth Creating

- `concepts/mcp.md` — Model Context Protocol. Referenced from `topics/agentic-ai.md` (dead link), `tools/claude-code.md`, and multiple sources. Enough signal to warrant a page.

---

## Stale Dates
No pages with `last_updated` older than 60 days. All content is from April 2026. ✓

## Frontmatter Gaps
No wiki pages have unfilled `YYYY-MM-DD` placeholders (only CLAUDE.md schema templates). ✓

## Traction Signals
All `tools/` pages have non-empty Traction Signals sections. ✓

---

## Fix Priority

| # | Issue | Effort | Safe to auto-fix? |
|---|-------|--------|-------------------|
| 1 | Delete empty root owner stubs + fix index links | Low | Yes |
| 2 | Add `how-to-learn-claude-infographic` to index | Low | Yes |
| 3 | Remove duplicate `[[hot-cache]]` in index | Low | Yes |
| 4 | Create `concepts/mcp.md` stub | Medium | Yes |
| 5 | Ingest `Post by @phosphenq` (LeCun lecture) | Medium | Ask owner |
| 6 | File or verify LinkedIn source page | Low | Ask owner |
| 7 | Decide on `[[learn-agentic-ai]]` — create page or remove link | Low | Ask owner |
