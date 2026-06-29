---
name: Obsidian Dataview
type: tool
category: ide-extension
status: mainstream
last_updated: 2026-06-29
---

## What It Is
An [[obsidian]] plugin that lets you query your vault's frontmatter and content using a SQL-like syntax (DQL) or JavaScript. Turns your wiki's YAML frontmatter into a queryable database — list all pages by type, filter by status, aggregate across folders.

## Traction Signals
- Recommended in Karpathy's original LLM Wiki gist as part of the optional tool stack — [[karpathy-llm-wiki-gist]]
- One of the most-installed Obsidian plugins; effectively standard in any serious Obsidian vault
- **2026-06-29 status**: stable canonical-incumbent canonical-Obsidian-plugin; no canonical-substantive-displacement canonical-event surfaced in 2026-Q2 ingest cadence. Used in this wiki's `meta/dashboard.md` for canonical-recent-activity + canonical-seed-pages canonical-queries (per [[claude-obsidian:wiki-lint]] scaffold).

## How to Use It
Install from Obsidian's community plugins. Write queries inline in notes using code blocks tagged `dataview`. Example — list all tools with gaining-traction status:

```dataview
TABLE status, last_updated
FROM "tools"
WHERE status = "gaining-traction"
SORT last_updated DESC
```

## Key Concepts
- **DQL**: Dataview Query Language — SQL-like syntax for list/table/task queries
- **Inline fields**: `key:: value` syntax in note body (alternative to frontmatter)
- **DataviewJS**: full JavaScript API for complex queries

## Compared To
- Manual index.md: static, requires LLM to update; Dataview generates views dynamically from frontmatter
- Obsidian Search: full-text only; Dataview queries structured metadata

## Resources
- [[karpathy-llm-wiki-gist]] — listed as optional tool for querying frontmatter across wiki pages
