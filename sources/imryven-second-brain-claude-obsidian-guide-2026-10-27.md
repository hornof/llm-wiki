---
title: "How to Build a Second Brain With Claude and Obsidian That Gets Smarter With Every Source You Save"
type: source
medium: article
url: https://x.com/imryven/status/2115046979659055476
local_source: "_raw/How to Build a Second Brain With Claude and Obsidian That Gets Smarter With Every Source You Save.md"
ingested: 2026-11-09
---

## Summary

An X article by @imryven (2026-10-27): a ten-step walkthrough for building the [[llm-wiki-pattern]] with Claude Code (Desktop's Code tab) and [[obsidian]], from an empty vault to a nightly scheduled ingest and a weekly lint. It's written for non-programmers, with copy-paste prompts. The author says plainly that they have not run it end to end. Its value for this wiki is the scheduling and permissions detail, which was checked here against Anthropic's docs ([[claude-code-desktop-scheduled-tasks-docs]]).

## Key Claims / Takeaways

- **Same layout as this wiki.** `raw/` (never edited), `wiki/`, `output/`, and a `CLAUDE.md` rulebook, with ingest, query and lint as the operations. Attributed to Karpathy's April 2026 gist.
- **Let Claude write CLAUDE.md by interviewing you**, kept *"under 200 lines"*. Move repeated procedures into skills so the rulebook stays short.
- **Keep the query honest.** Prompt with *"Using only wiki/"* and ask it to say what the wiki doesn't cover. Otherwise *"Claude fills gaps from general knowledge"*.
- **Per-project rooms.** A subfolder with its own CLAUDE.md, which Claude Code loads *"when it starts working there"*.
- **Nightly ingest as a Desktop scheduled task**, plus a weekly read-only review for contradictions, orphans and unsourced claims. Local tasks *"only fire while the desktop app is open and your computer is awake"*; cloud tasks *"can't see your local vault"*. The local-task limit is confirmed by the docs; the cloud claim is the author's. See [[claude-code-desktop-scheduled-tasks-docs]].
- **Permissions, not promises.** *"Writing "never delete files" in CLAUDE.md is a request."* Block actions with permissions or a PreToolUse hook. The Obsidian MCP server *"includes a delete tool"*.
- **Usage limits are shared** across Claude and Claude Code on Pro and Max, so start with five to ten files.
- **Packaged alternatives:** claude-obsidian (AgriciDaniel; a Claude Code plugin with `/claude-obsidian:wiki-ingest` and `wiki-query`) and obsidian-second-brain (eugeniughelbur; *"43 slash commands"*, also runs on Codex CLI, Gemini CLI and OpenCode).
- **Author's caveat:** *"I have not run this walkthrough end to end, and menu names can differ between app versions."* Time estimates are the author's.

## Pages Updated

- [[llm-wiki-pattern]] — Alternative Implementations; scheduled operation
- [[obsidian]] — Traction Signals
