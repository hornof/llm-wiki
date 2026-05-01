---
title: I Built an AI Agent That Manages My Life
type: source
medium: blog-post
url: https://x.com/seelffff/status/2050007245216256051
published: 2026-04-30
ingested: 2026-05-01
---

## Summary

X longform tutorial by [[seelffff]] documenting a personal life-management agent built on [[claude-desktop]] + three MCP servers (Filesystem, [[playwright-mcp]], custom Telegram). Frames the system as "the difference between an AI assistant and an AI agent": tells-you-things vs. does-things. Total incremental cost: $0 on top of an existing Claude Pro subscription (~$20/mo). Setup time: ~20–30 minutes. Includes the full `claude_desktop_config.json`, the 25-line Telegram MCP server (`server.js`), a starter `CLAUDE.md`, and example output from the `gm` morning-briefing command.

The system architecture is intentionally simple:

```
YOU → Claude Desktop (the brain)
        ├── Filesystem MCP → ~/agent-system/{CLAUDE.md, tasks.md, context.md, notes.md}
        ├── Playwright MCP → real Chrome (TechCrunch, X, Polymarket, anywhere)
        └── Telegram MCP   → your phone
```

`CLAUDE.md` is positioned as the **entire intelligence of the agent** — no code, no configuration, just plain English commands (`gm`, `x post idea`, `motivate me`, `fact`, `polymarket check`, `research [topic]`, `done: [task]`, `check progress`, `evening review`). Same schema-driven configuration pattern as [[tomcrawshaw-claude-code-blueprint]] but inside Claude Desktop instead of Claude Code, and aimed at non-coding life-management instead of software engineering.

## Key Claims / Takeaways

- **AI assistant vs. AI agent (the framing)**: an assistant tells you things; an agent does things — reads real files, browses real websites, sends real push notifications.
- **MCP as "USB ports for AI"** — community shorthand reused here; useful pedagogical metaphor for non-developers.
- **Claude Pro–only agent stack ($0 incremental)**: no API keys, no AWS, no paid OpenAI plan, no developer account. Filesystem MCP + Playwright MCP both run via `npx`; Telegram MCP is 25 lines of Node code; Telegram bot is free. This expands the agent-builder population from "developers with API budget" to "anyone with Claude Pro."
- **CLAUDE.md as agent brain.** Plain-English imperative commands ("Open TechCrunch with Playwright. Find the 3 most important AI or tech stories from the last 24 hours. Get real headlines.") work. Specificity beats abstraction: "Browse TechCrunch" beats "find news"; "Write a contrarian take about AI automation" beats "write a post idea."
- **Four-file personal-memory pattern**: `CLAUDE.md` (instructions) + `tasks.md` (daily habits) + `context.md` (about you) + `notes.md` (research output). The agent reads `context.md` before any personalized output; this is the personal-scale analog of the [[company-brain]] factual-memory layer.
- **Push beats pull**: the durable advantage of this stack vs. Notion/Obsidian/Zapier/Todoist isn't capability — it's that the agent reaches you on Telegram, the app you're already on, instead of waiting for you to open it. "When life gets busy, you stop" opening apps. Telegram inverts the relationship.
- **Real browser, not scraping**: Playwright MCP is "a real Chrome" — if you're logged in, the agent is logged in. Distinguished from generic AI assistants whose web access is summarized/cached/stale.
- **Persistence comes from Projects**: "Projects in Claude Desktop have persistent memory and read your folder." Adding the `~/agent-system` folder to a Claude Desktop Project is what makes the four-file memory loop work.
- **Roadmap items the author plans next**: scheduled morning briefing (Claude Desktop's native scheduled-tasks support), weekly review with habit-completion deltas, X-post drafting workflow, learning tracker, mood log. All are "just a new section in CLAUDE.md plus, in some cases, a new MCP server."
- **Comparison table** (author's claim, light editorial trust required):
  - Browses real websites: this stack ✓ / Notion AI ✗ / Zapier partial / Generic AI apps ✗
  - Reads local files: this stack ✓ / others ✗
  - Customizable commands: unlimited / others limited
  - Extra cost: $0 / others $8–20+/mo

## Caveats

- **Single-author practitioner post.** Strong how-to provenance (full code, full config) but no peer or third-party validation. Wait for a second independent practitioner reproduction before promoting Claude Desktop's MCP-host status beyond the entry in [[claude-desktop]].
- **Native scheduled-tasks claim is unsourced** beyond the post itself; the author treats it as known but it has not been verified against Anthropic's primary docs in this wiki.
- **Telegram bot security note** in the source: treat the bot token like a password; revoke via `/revoke` in BotFather if exposed.
- **Headlines in the example output** ("Anthropic raises at $900B valuation," "OpenAI files suit against xAI over Grok training data," etc.) appear in the source as reproductions of what the agent produced on a specific morning. They are illustrative, not wiki-claimable facts; do not propagate them as primary signals to other pages.

## Connection to Other Wiki Threads

- **Same pattern at different scale**: this is the personal-scale analog of [[company-brain]]. seelffff's `CLAUDE.md + context.md + tasks.md + notes.md` is the [[ashwingop]] **factual memory** layer compressed to a single user. The agent-must-read-context-before-personalizing claim is the same as Ashwin's "memory participates; knowledge bases wait."
- **Validates [[playwright-mcp]] as default browser-automation MCP**: third independent practitioner use ([[heygurisingh-career-ops]], [[alfiejcarter-linkedin-claude-stack]], now this) — the third signal needed to consider promoting playwright-mcp from `emerging` toward `gaining-traction`.
- **Independent CLAUDE.md-schema endorsement**: matches [[tomcrawshaw-claude-code-blueprint]]'s "CLAUDE.md is the trick" claim and the broader [[claude-code]] schema-driven configuration pattern. Different harness ([[claude-desktop]] vs. [[claude-code]]) but identical configuration philosophy.

## Pages Updated

- [[seelffff]] (new) — author
- [[claude-desktop]] (new) — Claude Desktop as MCP host for personal-agent stacks
- [[personal-ai-agent-claude-desktop-mcp]] (new) — tutorial page derived from this source
- [[playwright-mcp]] — third independent practitioner traction signal added
- [[mcp]] — added Claude Desktop as a host context; consumer-grade agent stack as a new use pattern
