---
name: claude-mem
type: tool
category: cli
status: gaining-traction
last_updated: 2026-07-12
---

## What It Is

**claude-mem** (by **Alex Newman** / `thedotmack`) provides *"persistent context across sessions for every agent"* — it *"captures everything your agent does during sessions, compresses it with AI, and injects relevant context back into future sessions."* Installed as a [[claude-code|Claude Code]] plugin, it gives agents durable **institutional memory** so they don't re-learn project history each session. It is the "Memory Keeper / persistent memory" tile (Developers dept) in [[charliejhills-claude-whole-company-42-skills-2026-07-12|Charlie Hills' "Claude as a company" chart]].

## Traction Signals

- **~87k GitHub stars / ~7.5k forks** (per [github.com/thedotmack/claude-mem](https://github.com/thedotmack/claude-mem), 2026-07-12); featured on Trendshift and in Awesome Claude Code.
- Very high release cadence (**296 releases**; v13.10.2 latest as of 2026-07) — active maintenance.
- Cross-gateway support: Claude Code plus OpenCode, Antigravity CLI, and [[openclaw|OpenClaw]] gateways. Apache-2.0 (chosen explicitly to allow embedding in developer tools, local agents, MCP servers, enterprise systems).

## How to Use It

- **Install**: `npx claude-mem install`, or `/plugin marketplace add thedotmack/claude-mem` → `/plugin install claude-mem`. Operates automatically after restart.
- Ships a **`mem-search` skill** for natural-language memory queries; `<private>` tags exclude sensitive content.

## Key Concepts

- **5 lifecycle hooks** (SessionStart, UserPromptSubmit, PostToolUse, Stop, SessionEnd) capture tool usage — the same hook surface [[addy-osmani-agent-harness-engineering-2026-04-19|Addy Osmani's harness taxonomy]] names as an enforcement layer.
- **Compression → semantic summaries**: captured activity is AI-compressed rather than stored raw.
- **Storage**: SQLite + FTS5 full-text search plus a Chroma vector DB for hybrid semantic + keyword search; a Bun worker service exposes retrieval via **MCP tools** (`search`, `timeline`, `get_observations`).
- **Progressive disclosure** — layered 3-tier retrieval with token-cost visibility (the same principle in Claude Code's own `/usage`).

## Compared To

- **[[mem0]]** — both are agent-memory layers; claude-mem is Claude-Code-plugin-native (hooks + skill), mem0 is a framework-agnostic memory library.
- **[[skill-md|SKILL.md]] as outer-loop memory** — claude-mem automates the *conversational/episodic* memory that SKILL.md files capture *procedurally*; complementary, not competing.
- **[[superpowers]] / [[context7]]** — sibling third-party Claude-skill packs; claude-mem is the memory/continuity specialist.

## Resources
- [github.com/thedotmack/claude-mem](https://github.com/thedotmack/claude-mem) — Apache-2.0; Alex Newman
- [[charliejhills-claude-whole-company-42-skills-2026-07-12]] — surfaced as the Developers "Memory Keeper" tile
