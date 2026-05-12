---
title: Agent view in Claude Code (Anthropic blog)
type: source
medium: article
url: https://claude.com/blog/agent-view-in-claude-code
ingested: 2026-05-11
---

## Summary

Primary Anthropic blog post (May 11 2026) announcing **agent view** in [[claude-code]] — a TUI surface inside the CLI for managing multiple concurrent Claude Code sessions from one place. Replaces the de-facto "tmux + multiple terminal tabs + mental ledger" pattern practitioners have been building by hand for months. Available as a Research Preview on Pro / Max / Team / Enterprise / API plans; opt-in via `claude agents`.

## Key Claims / Takeaways

- **New CLI surface**: `claude agents` opens agent view. From inside any session, **left-arrow** jumps to it. From the agent view, **right-arrow** attaches back into a session's full transcript.
- **Three columns of information per session**: whether it needs your input, the contents of its last response, when you last interacted with it. Treats the agent fleet as a *managed work queue*, not as a set of separate shells.
- **Peek-without-attach interaction model**: select a session to preview its last turn; answer inline if the session is waiting on a decision; only attach to the full transcript when you actually need to explore. Matches the [[claude-code]] practitioner pattern of *steering many, not babysitting one*.
- **`/bg` and `claude --bg [task]`** — move existing sessions to the background, or skip the foreground entirely on launch. Background sessions show their next-run time in the agent-view list (relevant for looping jobs).
- **Anthropic's named usage patterns** (from the post):
  - **Scaling concurrent sessions**: dispatch several ideas at once, each optionally paired with a [[claude-code]] skill, then return to a list of PRs ready for review.
  - **Manage long-running agents**: PR-babysitters, dashboard-updaters, looping jobs — the agent view surfaces next-run time for each.
  - **Navigate between sessions**: arrow-left during one session to start a related task, arrow-right back when the answer lands.
  - **See what shipped**: status indicators + peek title make it easy to scan which sessions produced a PR.
- **Distribution**: Pro / Max / Team / Enterprise / Claude API. Usual rate limits apply. Research Preview gating means it's not GA but is available to all paying plans, which is the broadest distribution shape Anthropic uses for previewing surfaces. Docs at `code.claude.com/docs/en/agent-view`.

## Why This Matters for the Wiki

- **Confirms multi-agent / parallel-session usage as Anthropic's named primary [[claude-code]] usage pattern**: matches the Code w/ Claude 2026 product expansion ([[willison-code-w-claude-2026]] — Multi-agent Orchestration, Outcomes, Dreaming) and the [[aakashgupta-anthropic-growth-acceleration-2026-05-09]] framing where the run-rate is being driven by enterprise users running *many* sessions, not heavier single sessions.
- **TUI-as-orchestration-surface** is a real product decision. Anthropic could have built this in the desktop GUI (or in the new [[claude-cowork]] surface) but chose to add it to the *terminal*. Strong signal that the high-leverage [[claude-code]] user still lives in the shell.
- **Adjacent to [[river]]**: agent view solves the *per-developer* parallel-session problem; [[river]] solves the *org-wide* parallel-session problem. Different scales of the same coordination challenge.
- **First product-level user-facing artifact of [[claude-code]] running many agents concurrently** — Anthropic's earlier surfaces (Routines, Remote Agents from Code w/ Claude 2026) targeted async/remote primitives; agent view is the sync/local manager.

## Pages Updated

- [[claude-code]] — new traction signal added under May 2026; agent view as a TUI multi-session manager
