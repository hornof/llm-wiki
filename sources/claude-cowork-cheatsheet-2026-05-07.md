---
title: Claude Cowork — Interactive Cheat Sheet
type: source
medium: article
url: https://fresh-cowork.vercel.app/
ingested: 2026-05-08
---

## Summary

Practitioner cheat sheet for [[claude-cowork]] — the Anthropic product surface positioned as **"autonomous agent you delegate to"** rather than a chatbot. Covers the full mental model (outcomes-not-steps), launch path (Claude Desktop tab), tool priority ladder (MCP → Chrome → Computer Use), 38+ named built-in connectors, file-output capabilities, CLAUDE.md folder instructions, scheduled tasks, Dispatch (mobile pairing), Plugins, Skills, and plan availability. Authorless community page; useful as a snapshot of what Anthropic shipped under the Cowork name as of early May 2026 and how practitioners are framing it.

## Key Claims / Takeaways

### Positioning

- *"Cowork isn't a chatbot you guide step-by-step. It's an autonomous agent you delegate to."*
- **The Context Formula**: `Outcome + Context + Constraints`. Concrete example: "Create a slide deck [outcome] using the data in Q1-metrics.xlsx [context] — keep it under 10 slides, use our brand colors, and include a summary slide [constraints]."
- **Three-product line for Anthropic surfaces**: Chat (Claude.ai) for ideation + feedback; **Cowork** for autonomous execution + file delivery + workflow automation; **Claude Code** for software development. *"Brainstorm in Chat → execute in Cowork → iterate in Chat."*

### Launch + Surface

- **No CLI, no config files, no terminal.** Cowork is a tab inside Claude Desktop.
- Default model: **Claude Sonnet 4.6**. Users can ask Claude to switch to Opus for complex tasks.

### Tool Priority Ladder (Cowork's Internal Routing)

> MCP Connector → Chrome Extension → Computer Use

- **MCP Connector**: fastest, most reliable (10× faster, 10× fewer tokens than browser/computer use)
- **Chrome Extension** ("Claude in Chrome"): for any website or web app
- **Computer Use**: fallback for native desktop apps; requires active screen, asks per-app permission, **Pro/Max plans only**, blocked apps include banking / password managers / security software

### Built-in Connectors (38+ named)

- **Google**: Gmail, Calendar, Drive
- **Communication**: Slack
- **Project management**: Notion, Linear, Asana, Jira
- **CRM/Sales**: HubSpot, Salesforce, Apollo, Clay, Outreach
- **Dev tools**: GitHub
- **Design**: Canva
- **Docs/Legal**: DocuSign
- **Enterprise**: Microsoft 365 (Word, Excel, PowerPoint, OneDrive, SharePoint), Snowflake
- **Research**: Similarweb, FactSet
- **Custom MCP servers**: Teams/Enterprise plans can add internal tools as remote MCP servers via OAuth

### File Outputs

- **Office**: `.docx`, `.pptx`, `.xlsx`, `.pdf`
- **Web/Data/Code**: `.html`, `.csv`, `.json`, `.xml`, `.py`, `.js`, `.ts`, `.md`, `.txt`
- **30 MB file size limit** per file

### CLAUDE.md as Folder Instructions

> "Drop a `CLAUDE.md` file into any folder you share with Cowork. Claude reads it automatically at the start of every session."

Direct parallel to [[claude-code]]'s CLAUDE.md convention: same name, same role, same "living document" framing. Encodes role, tools, brand colors, preferences, naming conventions, team acronyms.

### Self-Verification Pattern

> "Ask Claude to verify its own work before delivering it. **The single biggest quality improvement you can make.**"

Patterns: create-then-review, create-then-test, create-then-compare, multi-step-checkpoint. Practitioner framing: "just add 'then review it and fix any issues' to the end of any request."

### Plugins (Capability Bundles)

A Plugin contains: Connectors + Custom Skills + Global Instructions + Starter Templates. Sources: Official Registry (free→Pro), Marketplace (free→Premium), Custom (Enterprise).

### Skills (`SKILL.md`)

Reusable workflows triggerable from chat or schedule. Stored as `SKILL.md` in the Cowork folder. Built-in skills: Schedule Task, Create Document, Web Research, Email Workflow.

Custom skill format example:
```yaml
---
name: Daily Briefing
description: Compile Slack highlights, unread emails, and calendar summary
trigger: command: /daily
---
```

### Scheduled Tasks (Local-Only)

- Frequencies: Daily / Weekly / Monthly / One-time / Custom cron
- **Local-only scheduling — not cloud-based.** Requires Claude Desktop running and machine awake; missed tasks run when app reopens.

### Dispatch (Mobile Pairing)

Assign tasks from phone, executed on desktop. Pairing via QR code from Claude Desktop. **Pro/Max only.**

### Projects

- Per-project folder, memory, configuration
- Project-level CLAUDE.md overrides global settings
- **Local-only** — no cloud sync, no team sharing

### Plan Availability Snapshot (May 2026)

| Feature                  | Pro ($20) | Max ($100–200) | Team | Enterprise |
|--------------------------|-----------|----------------|------|------------|
| Cowork mode              | ✓         | ✓              | ✓    | ✓          |
| Built-in connectors      | ✓         | ✓              | ✓    | ✓          |
| **Custom connectors**    | —         | —              | ✓    | ✓          |
| **Computer Use**         | ✓         | ✓              | —    | —          |
| Scheduled tasks          | ✓         | ✓              | ✓    | ✓          |
| Dispatch (mobile)        | ✓         | ✓              | ✓    | ✓          |
| Projects                 | ✓         | ✓              | ✓    | ✓          |
| Plugins & skills         | ✓         | ✓              | ✓    | ✓          |
| Chrome integration       | ✓         | ✓              | ✓    | ✓          |

Notable boundary: **Computer Use is Pro/Max only — Team/Enterprise don't get it yet.** This is a deliberate trust/audit boundary: Cowork on Team/Enterprise routes through MCP and Chrome only, with audit logging coming.

## Pages Updated

- [[claude-cowork]] (new)
- [[anthropic]] (updated — Cowork stub graduates to a proper tool page; Computer Use, Dispatch, Connectors, Skills, Plugins all named via Anthropic-published practitioner page)
- [[claude-desktop]] (updated — Cowork now lives as a tab inside Claude Desktop; clarifies the host/surface relationship)
- [[mcp]] (updated — 38+ named built-in connectors + custom MCP server option)
- [[claude-code]] (light cross-ref — three-surface comparison: Chat / Cowork / Code)
