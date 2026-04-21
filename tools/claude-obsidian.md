---
name: claude-obsidian
type: tool
category: claude-code-skill
status: gaining-traction
last_updated: 2026-04-21
---

## What It Is
A Claude Code plugin implementing Karpathy's LLM Wiki pattern with Obsidian as the vault. 10 skills covering the full wiki lifecycle: setup, ingest, query, lint, save, autoresearch, and visual canvas. Built by [[agrici-daniel]]. MIT license.

## Traction Signals
- 2,626 stars and 307 forks on GitHub in ~2 weeks (created 2026-04-07) — [[github-claude-obsidian]]
- Extends Karpathy's original pattern with session memory, autonomous research, and visual canvas
- Active community: 2,800+ member Skool group, YouTube tutorials

## How to Use It

**Option 1 — Clone as vault (recommended):**
```bash
git clone https://github.com/AgriciDaniel/claude-obsidian
cd claude-obsidian
bash bin/setup-vault.sh
```
Open the folder in Obsidian, then open Claude Code in the same folder and type `/wiki`.

**Option 2 — Install as Claude Code plugin:**
```bash
claude plugin marketplace add AgriciDaniel/claude-obsidian
claude plugin install claude-obsidian@claude-obsidian-marketplace
```

## Key Concepts
- **[[hot-cache]]** (`wiki/hot.md`): updated at session end; next session starts with full recent context — no cold start
- **/autoresearch**: 3-round autonomous research loop configurable via `program.md`
- **/canvas**: visual layer for adding images, PDFs, notes, and zones to Obsidian canvas files
- **Contradiction flagging**: writes `[!contradiction]` callouts at ingest time (not deferred to lint)
- **Six wiki modes**: Website (A), GitHub (B), Business (C), Personal (D), Research (E), Book/Course (F)
- **Cross-project power move**: point any Claude Code project's CLAUDE.md at this vault so all projects share the same knowledge base
- **MCP integration**: Option A = Local REST API + mcp-obsidian; Option B = filesystem mcpvault (no plugin)

## Commands
| Command | What it does |
|---------|-------------|
| `/wiki` | Setup, scaffold, or continue session |
| `ingest [file/url]` | Create 8-15 wiki pages, update index and log |
| `ingest all of these` | Batch process via parallel agents |
| `what do you know about X?` | Query wiki with citations |
| `/save` | File current conversation as wiki note |
| `/autoresearch [topic]` | Autonomous research: search → fetch → synthesize → file |
| `/canvas` | Open/create visual canvas |
| `lint the wiki` | 8-category health check |
| `update hot cache` | Refresh hot.md with latest context |

## Compared To
- Plain LLM Wiki pattern: claude-obsidian adds session memory (hot cache), autonomous research, visual canvas, contradiction flagging at ingest, batch ingestion, MCP, and 6 wiki modes
- Smart Connections, Copilot (Obsidian plugins): those are chat interfaces; claude-obsidian autonomously creates and maintains notes

## Resources
- [[github-claude-obsidian]] — primary source
- [[karpathy-llm-wiki-gist]] — the pattern this is based on
- [[claude-canvas]] — companion tool for advanced visual canvas
