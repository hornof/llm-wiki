---
name: Claude Desktop
type: tool
category: platform
status: gaining-traction
last_updated: 2026-05-08
---

## What It Is

Anthropic's desktop application for macOS and Windows. Hosts Claude conversations with **persistent Projects** (folder-scoped contexts that re-read files at session start), acts as an **MCP host** (users configure local MCP servers via `claude_desktop_config.json`), and — as of May 2026 — hosts the **[[claude-cowork]]** autonomous-execution tab where Claude takes a brief and runs the task end-to-end across files, apps, and the browser. Distinct from [[claude-code]] (terminal-native CLI for agentic coding) and from claude.ai (web). Same model family, different harness.

Download: [claude.ai/download](https://claude.ai/download). Requires a Claude Pro or higher subscription for full access.

## Traction Signals

- **Default MCP host for personal-agent tutorials.** April 2026 viral X tutorial by [[seelffff]] uses Claude Desktop (not Claude Code) as the MCP host for a personal life-management agent stack — Filesystem MCP + [[playwright-mcp]] + a custom 25-line Telegram MCP — and explicitly recommends Claude Desktop because "Projects in Claude Desktop have persistent memory and read your folder." — [[seelffff-personal-ai-agent]] / [[personal-ai-agent-claude-desktop-mcp]]
- **Cowork tab graduated to a first-class surface** (May 2026): Claude Desktop now hosts [[claude-cowork]], Anthropic's autonomous-execution surface for non-coding workflows. Practitioner cheat sheet [[claude-cowork-cheatsheet-2026-05-07]] documents 38+ built-in MCP connectors, the **MCP → Chrome → Computer Use** priority ladder, Plugins, Skills (`SKILL.md`), Scheduled Tasks, Dispatch (mobile pairing). Claude Desktop is the *host*; Cowork is the autonomous mode within it.
- **Native scheduled-tasks support cited** as a near-term capability for "scheduled morning briefing" at 7am — practitioner expects Claude Desktop to run agent commands on cron without Claude Code in the loop. [unsourced beyond the seelffff post; verify before relying]
- **Claude Pro–only agent stacks possible**: Claude Desktop + MCP unlocks browser automation, filesystem read/write, and external push delivery on a $20/mo subscription with no API keys. Lowers the barrier from "developer with API budget" to "anyone with Claude Pro."

## How to Use It (MCP host)

1. Install Claude Desktop and sign in with Claude Pro.
2. Edit `~/Library/Application Support/Claude/claude_desktop_config.json` (macOS) and add MCP servers under `"mcpServers"`. Each server is a `command` + `args` (and optional `env`) that Claude Desktop spawns over stdio.
3. Restart Claude Desktop.
4. Create a Project, add a folder, and the agent (governed by the Project's `CLAUDE.md`) will read those files at session start.

Example config skeleton (from [[personal-ai-agent-claude-desktop-mcp]]):

```json
{
  "mcpServers": {
    "playwright": { "command": "npx", "args": ["@playwright/mcp@latest"] },
    "filesystem": { "command": "npx", "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/folder"] },
    "telegram":   { "command": "node", "args": ["/path/to/server.js"], "env": { "BOT_TOKEN": "...", "CHAT_ID": "..." } }
  }
}
```

## Key Concepts

- **Project**: a folder-scoped context with persistent memory; auto-reads files at session start. Equivalent of a project workspace with always-attached files.
- **MCP host**: Claude Desktop is one of several MCP hosts ([[claude-code]] is another). It spawns MCP servers as subprocesses and routes the model's tool calls.
- **CLAUDE.md as system prompt**: same pattern as [[claude-code]] — the project-level CLAUDE.md is read at the start of every session as the agent's instructions.

## Compared To

- **[[claude-code]]**: terminal-native, designed for software engineering with full shell access. Claude Desktop has Projects + MCP but no shell; better for "non-coding agentic tasks" (research, browsing, life management) where the agent doesn't need a dev shell.
- **claude.ai (web)**: simplest, no MCP, no local files. Use for quick chat, not agents.
- **ChatGPT Desktop / GPT-Image-2 stacks**: ChatGPT now also has MCP support (per third-party reports, not yet ingested into wiki); functional overlap with Claude Desktop on the agentic-stack side, but the practitioner content currently in this wiki centers on Claude Desktop.

## Caveats

- The seelffff tutorial is currently the only first-hand walkthrough in this wiki. Promote `gaining-traction` → `mainstream` only after multiple independent practitioner sources or a primary Anthropic announcement of Desktop-as-agent-platform.
- Native scheduled-tasks claim is from the practitioner post and has not been verified against Anthropic primary docs in this wiki.

## Resources

- [claude.ai/download](https://claude.ai/download) — official download
- [[seelffff-personal-ai-agent]] — first-hand viral tutorial using Claude Desktop as the MCP host for a personal life-management agent
- [[personal-ai-agent-claude-desktop-mcp]] — wiki-side how-to derived from the source
- Related: [[mcp]] — the protocol Claude Desktop hosts; [[playwright-mcp]] — the most-used MCP server in this wiki's practitioner content
