---
title: "PlainBoard: an open-source Kanban board where Claude agents plan and work through tickets"
type: source
medium: reddit-post
url: https://www.reddit.com/r/ClaudeAI/comments/1xzhada/plainboard_an_opensource_kanban_board_where/
ingested: 2026-11-23
local_source: "_raw/PlainBoard an open-source Kanban board where Claude agents plan and work through tickets.md"
---

## Summary

An r/ClaudeAI build post (u/de_hannes, 2026-11-18), with the GitHub README fetched 2026-11-23 (`_raw/plainboard-repo-2026-11-23.txt`). PlainBoard is a self-hosted, MIT-licensed Kanban board: you talk to a manager agent, it writes tickets and assigns them to a team of Claude agents, and finished branches are merged, checked once and landed. The thread is more useful than the tool. Most replies say they built the same thing, and they list about a dozen alternatives.

## Key Claims / Takeaways

- **Why it was built** (post): the author's idea notes outgrew a side repo because *"Claude Code forgot to check things and didn't delete old notes, and the repo became useless."*
- **Built by the models it runs** (post): planned with *"Claude Code Opus 5.5 on high"*, then mostly Fable 5.2, which read the logs and database of the author's running instance to fix agent loops that *"did things multiple times, wrote unnecessary tests/code and burned a lot of tokens."*
- **How it lands work** (README): *"Finished branches are merged together, checked once, and what passes goes into your main branch."* The user never assigns tickets or merges. 149 GitHub stars when fetched (*"Star149"*).
- **Security note** (post): *"agents have full shell and network access inside the runner container, so only give them the credentials they need."*
- **The thread's verdict** (mod-bot summary of 50 comments): *"AI Kanban boards are posted here constantly"*, after which *"a parade of other users stepped forward"* to say they'd built one too. Alternatives named: Linear, Plane, backlog.md, Vibe Kanban, multica, kangentic, taskview, papi, Obsidian's Kanban plugin.
- **A reply worth keeping** (u/oplaffs): *"why the responsibility for working efficiently and saving tokens always falls on the user."*

## Pages Updated

- [[owner/project-ideas]] (item 2, build posts)
