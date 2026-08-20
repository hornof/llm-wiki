---
title: "How I use Claude Code — 50 tips from 6 months at Meta (John Kim / Push to Prod)"
type: source
medium: video
url: https://www.youtube.com/watch?v=mZzhfPle9QU
ingested: 2026-08-20
---

## Summary

[[john-kim|John Kim]] (L7 Senior Staff engineer at Meta; *Push to Prod*) walks through **50 [[claude-code|Claude Code]] tips** from ~6 months of 12-hour-a-day use, structured in four acts: Foundations (1–25), Daily Workflow (26–32), Power User (33–40), Advanced (41–50). The throughline is **context engineering** — *"context is king, keep it fresh and condensed"* — with the **validation loop** named as the single highest-leverage thing for reliable agentic coding. ~500K views; the wiki's 2nd John-Kim surface (promotes his [[john-kim]] page).

## Key Claims / Takeaways

- **Foundations**: run from repo root (first token zips up project context); `/init` to generate `CLAUDE.md`; keep it **concise (~300 lines)** — bloat costs tokens *and* degrades instruction-following; structure it **What / Domain / Validation**; CLAUDE.md is **hierarchical** (project + global `~/.claude`) and **read top-to-bottom = priority order**.
- **The validation loop is the most important topic** in agentic coding: a build/verify command in CLAUDE.md lets the agent *self-improve until it fixes itself* — *"a lot of [failures] get resolved when you fix the validation."* Examples: Xcode build, Playwright/`/chrome` nav, debug-logs + emulator control + tail-log reading, Perfetto traces for perf.
- **Keyboard/context primitives**: Shift+Tab (plan↔edit mode), Escape to interrupt (interrupting/course-correcting is *recommended*, not risky — CC queues prompts well), double-Escape rewind; `/clear`, `/context` (audit token hogs — MCPs are common offenders), let **auto-compaction** work, `/model`, `/resume`.
- **Git is the real safety net** (over the built-in rewind).
- **Daily workflow**: **start in Plan Mode** and argue with it before executing — *"the generation of the code is the easy part"*; fresh context beats bloated; persist/lazy-load context via a local "second brain" `CLAUDE.md`; give verification commands; **prefer Opus** for complex work; read thinking blocks for wrong assumptions and interrupt.
- **Four composability primitives**: **Skills** (recurring workflows saved as MD — *"never create manually, ask Claude to"*; commands + skills recently merged by Anthropic), **Commands** (shorthand), **MCPs** (external-service docs — *ask Claude to find/install*, but they blow up context — use sparingly), **Subagents** (isolated context for **atomic side-effect** work only).
- **Subagent contrarian**: *"bring the work to the context rather than spread the context out"* — a subagent returns output, not the path to it, so context-dependent work (testing that needs to know the code it wrote) should stay in-session. Rejects CEO/product/design multi-agent role-play as *"clowny."*
- **Advanced / parallel**: run **multiple instances** and juggle them (*"like playing StarCraft"*), iTerm split panes (Cmd-D), notifications on completion, **git worktrees** for parallel edits on one repo, `/chrome` for browser control (scrape/navigate/debug/forms). **Hooks**: PostToolUse auto-format/lint, block destructive commands — *ask Claude to add them, don't hand-maintain your environment*. Explore the **plugin ecosystem** (compositions of the four primitives).
- **Compound engineering**: commit `CLAUDE.md` to the repo (high bar, evaluated over weeks) to improve teammates' AI experience; fix-once-then-add-a-rule so the mistake never recurs.
- **Meta-framing**: *"I'm one of those engineers that are basically not writing code anymore… I still read every single line of code — reviewing is my biggest bottleneck."*

## Pages Updated
- [[john-kim]] (new), [[claude-code]]
