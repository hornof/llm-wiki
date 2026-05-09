---
name: Claude Cowork
type: tool
category: platform
status: gaining-traction
last_updated: 2026-05-08
---

## What It Is

**Claude Cowork** is [[anthropic]]'s autonomous-execution surface for non-coding workflows — a tab inside [[claude-desktop]] that takes a brief in plain English and runs the task end-to-end across files, apps, and the browser. Anthropic's positioning ([[claude-cowork-cheatsheet-2026-05-07]]):

> "Cowork isn't a chatbot you guide step-by-step. It's an autonomous agent you delegate to."

Cowork sits in Anthropic's three-surface product line:

- **Claude.ai (Chat)** — back-and-forth conversation, ideation, feedback
- **Claude Cowork** — autonomous execution, file delivery, workflow automation, scheduled tasks
- **[[claude-code]]** — software development, debugging, refactoring

Recommended workflow: *"Brainstorm in Chat → execute in Cowork → iterate in Chat."*

Surface details: no CLI, no terminal, no config files. Cowork is a tab inside the Claude Desktop app. Default model is **Claude Sonnet 4.6**, switchable to Opus by asking Claude in-session.

## Traction Signals

- **Named publicly 2026-05-05** as a plugin host alongside [[claude-code]] in the [[claudeai-financial-services-agents-2026-05]] launch; one of three deployment surfaces for Claude for Financial Services agents
- **Confirmed as Anthropic Academy curriculum subject** via [[anthropic-academy-courses-catalog-2026-05]] — "Introduction to Claude Cowork" is a first-party course; Cowork is treated as a label-stable product, not a marketing flourish
- **Practitioner cheat-sheet community page** ([[claude-cowork-cheatsheet-2026-05-07]]) — comprehensive practitioner-side documentation including the priority ladder, 38+ named connectors, file output catalog, CLAUDE.md folder instructions, scheduled tasks, Dispatch, Plugins, Skills, and full plan-availability matrix
- **38+ built-in MCP connectors** named in the practitioner cheat sheet; custom remote MCP servers available on Team/Enterprise plans

## How to Use It

### The Context Formula

> Outcome + Context + Constraints

Concrete example: *"Create a slide deck [outcome] using the data in Q1-metrics.xlsx [context] — keep it under 10 slides, use our brand colors, and include a summary slide [constraints]."*

### First Steps Checklist

1. **Global Instructions** — Settings > Cowork > add role, tone, preferences
2. **Select a folder** — grant Cowork file I/O on a working folder
3. **Connect services** — `+` > Connectors to link Gmail, Slack, Drive, etc.
4. **Install Chrome extension** — "Claude in Chrome" from Chrome Web Store for browser automation
5. **Try a small task first** — rename files, create a spreadsheet

### CLAUDE.md as Folder Instructions

Drop a `CLAUDE.md` file into any folder shared with Cowork. Claude reads it automatically at session start. Same name, same role, same "living document" framing as [[claude-code]]'s convention. Used to encode brand colors, naming conventions (`YYYY-MM-DD-description.ext`), team acronyms, tone preferences, regulatory constraints. **Project-level CLAUDE.md overrides global Cowork settings.**

### Self-Verification Pattern

The cheat sheet calls this *"the single biggest quality improvement you can make"*:

| Pattern               | Example prompt |
|-----------------------|---------------|
| Create then review    | "Create the report, then review it for accuracy and completeness before saving" |
| Create then test      | "Build the spreadsheet, then spot-check 5 random rows against the source data" |
| Create then compare   | "Draft the email, then compare it against the thread to make sure I haven't missed anything" |
| Multi-step checkpoint | "After each section, pause and verify the data matches the source before moving on" |

Lightest version: append *"then review it and fix any issues"* to any request.

## Key Concepts

### Tool Priority Ladder

Cowork picks a tool in a fixed order:

> **MCP Connector → Chrome Extension → Computer Use**

- **MCP Connector** — fastest, most reliable; **10× faster, 10× fewer tokens** than browser/computer use
- **Chrome Extension** ("Claude in Chrome") — any website or web app
- **Computer Use** — fallback for native desktop apps; runs on the real desktop, requires active screen, blocked from banking apps / password managers / security software

### Plugins

Pre-built capability bundles, each containing: **Connectors + Custom Skills + Global Instructions + Starter Templates**. Sources: Official Registry (free→Pro), Marketplace (free→Premium), Custom (Enterprise).

### Skills

Reusable workflows stored as `SKILL.md` in a Cowork folder; triggerable from chat or schedule. Built-in skills: Schedule Task, Create Document, Web Research, Email Workflow.

### Dispatch

Mobile-to-desktop task pairing. Pair via QR code from Claude Desktop; tasks assigned from phone execute on the desktop while it's awake. **Pro/Max only.**

### Projects

Per-project folder + memory + configuration with isolation; **local-only** — no cloud sync, no team sharing.

### Scheduled Tasks

Daily / Weekly / Monthly / One-time / Custom-cron. **Local-only** — requires Claude Desktop running and the machine awake; missed tasks run when the app reopens.

## Connectors

38+ built-in MCP connectors as of May 2026:

- **Google**: Gmail, Google Calendar, Google Drive
- **Communication**: Slack
- **Project management**: Notion, Linear, Asana, Jira
- **CRM / Sales**: HubSpot, Salesforce, Apollo, Clay, Outreach
- **Dev tools**: GitHub
- **Design**: Canva
- **Docs / Legal**: DocuSign
- **Enterprise**: Microsoft 365 (Word, Excel, PowerPoint, OneDrive, SharePoint), Snowflake
- **Research**: Similarweb, FactSet

Custom remote MCP servers available on Team/Enterprise plans.

## Compared To

- **[[claude-code]]** — Cowork's coding-side sibling. Both run on the agentic loop, both read `CLAUDE.md` folder instructions, but Cowork targets non-developers (file delivery, automation, scheduled tasks) while Claude Code targets engineers (git, package managers, deployments).
- **[[claude-desktop]]** — Cowork is now a tab inside Claude Desktop; Claude Desktop is the host, Cowork is the autonomous-execution mode within it.
- **Cursor / standalone IDEs** — different audience; Cowork is for ops/research/docs work, not coding.
- **Zapier Agents / ServiceNow** — closest workflow-automation incumbents. Cowork's distinguishing pattern is the on-device, MCP-first, file-output-friendly model with CLAUDE.md as a folder-level scope.

## Plan Availability (May 2026)

| Feature                  | Pro ($20) | Max ($100–200) | Team | Enterprise |
|--------------------------|-----------|----------------|------|------------|
| Cowork mode              | ✓         | ✓              | ✓    | ✓          |
| Built-in connectors      | ✓         | ✓              | ✓    | ✓          |
| **Custom MCP servers**   | —         | —              | ✓    | ✓          |
| **Computer Use**         | ✓         | ✓              | —    | —          |
| Scheduled tasks          | ✓         | ✓              | ✓    | ✓          |
| Dispatch (mobile)        | ✓         | ✓              | ✓    | ✓          |
| Projects                 | ✓         | ✓              | ✓    | ✓          |
| Plugins & skills         | ✓         | ✓              | ✓    | ✓          |
| Chrome integration       | ✓         | ✓              | ✓    | ✓          |

**Computer Use is Pro/Max only.** Team/Enterprise routes through MCP + Chrome only — a deliberate audit/trust boundary; the cheat sheet notes "audit logging" is the gating feature for regulated workloads.

## Caveats

- All product/feature claims here trace to the practitioner cheat sheet, not first-party Anthropic docs. The page is comprehensive but not authoritative; verify against [Anthropic docs](https://platform.claude.com/docs/) before citing specific features in production decisions.
- Sonnet 4.6 default + manual Opus switch is per the cheat sheet; this could change with [[claude-opus-4-7]] availability.
- Local-only scheduling and local-only Projects are real limits — no cloud sync, no team sharing of project memory. Significant for distributed teams.

## Resources

- [[claude-cowork-cheatsheet-2026-05-07]] — practitioner interactive cheat sheet (full feature surface, May 7 2026)
- [[claudeai-financial-services-agents-2026-05]] — first vertical product line that ships into Cowork as plugins (May 5 2026)
- [[anthropic-academy-courses-catalog-2026-05]] — first-party "Introduction to Claude Cowork" course
- [[rubenhassid-anthropic-30-term-map-2026-05]] — secondary glossary placing Cowork in the Anthropic product surface
