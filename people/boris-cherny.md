---
name: Boris Cherny
type: person
affiliation: Anthropic (Claude Code creator)
signal_sources: [conference, twitter, podcast]
last_updated: 2026-06-08
---

## Who They Are

Boris Cherny is the creator of [[claude-code]] at [[anthropic]] — started as a side project in **September 2024**. Confirmed speaker at Sequoia's AI Ascent 2026 conference, **Code w/ Claude 2026** (May 6 2026 — closed out the event-keynote arc alongside Cat Wu), and **WorkOS Acquired Unplugged** (June 2 2026). Per [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn's 2026-06-07 synthesis]]: Claude Code *"now reportedly sits behind close to four percent of all public commits on GitHub"* (verification-pending primary).

## Their Current Focus

[[claude-code]] product surface, the architectural consolidation toward the [[claude-agent-sdk]], and — as of June 2026 — **[[loop-engineering|loop-engineering]] as primary job-description**. Cherny self-describes the abstraction transition at the WorkOS Acquired Unplugged talk (2026-06-02):

> *"Now it's actually leveled up, I think, again, to the next wave of abstraction where I don't prompt Claude anymore. I have loops that are running. They're the ones that are prompting Claude and figuring out what to do. My job is to write loops."*

**3-stage personal-ladder** (Van Horn framing):
1. **Autocomplete coding** (pre-2025)
2. **5-10 parallel Claude sessions, human-prompted** (~2025)
3. **Loop-authored, ~couple-hundred agents reading GitHub/Slack/Twitter** (now)

**IDE-deletion-November-2025 receipt**: per [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn]], Cherny *"deleted his IDE in November and has not opened it since."* Concrete behavioral marker for the loop-engineering transition at the Anthropic-creator layer.

## Notable Takes

- Confirmed speaker at Sequoia AI Ascent 2026 — [[ai-ascent-2026]]
- **Code w/ Claude 2026** (founder-of-product reflection): *"Everything we are seeing today still feels magical to me."* — captures the from-the-creator stance on the May 2026 product expansion — [[willison-code-w-claude-2026]]
- **WorkOS Acquired Unplugged talk** (2026-06-02, [[mvanhorn-wtf-is-a-loop-2026-06-07]]): *"My job is to write loops."* First wiki-captured Cherny-direct-voice articulation of loop-engineering as primary job-description at the Claude Code creator layer.
- **259 PRs in 30 days self-citation** (2025-12-27 via Simon Willison, surfaced in [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn synthesis]]): *"In the last 30 days, 100% of my contributions to Claude Code were written by Claude Code. I landed 259 PRs."*
- **5-tip recipe for running Opus autonomously for hours/days** (2026-06-05 X, [[bcherny-5-tips-opus-autonomous-2026-06-05]]):
  1. Auto mode for permissions
  2. Dynamic workflows (orchestrate hundreds/thousands of agents)
  3. `/goal` or `/loop` to nudge until done
  4. Claude Code in the cloud (close-laptop pattern)
  5. Self-verify end to end (Chrome extension for web, iOS/Android sim MCP for mobile, full server-startup for backend)
- **Context-rot counter-claim** (2026-06-08 X reply, [[bcherny-5-tips-opus-autonomous-2026-06-05]]): *"Context rot isn't a thing with 4.8 imo, but curious if that's been your experience also."* Direct contradiction of [[linas-beliunas-claude-goal-guide-2026-05-14|Linas's "context rot silently degrades long runs"]] framing — Cherny disputes for [[claude-opus-4-8|Opus 4.8]] generation.
- **5-archetype long-horizon-workload taxonomy** (2026-06-08 X reply, [[bcherny-5-tips-opus-autonomous-2026-06-05]]): feature-building / language-migration / framework-migration / iterative-profiling-and-optimization / flaky-test-resolution.
- **Canonical `/loop` starter** (via [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn]]): */loop babysit all my PRs. Auto-fix build issues, and when comments come in, use a worktree agent to fix them.*
- **Cron-under-the-hood disclosure** (via [[mvanhorn-wtf-is-a-loop-2026-06-07|Van Horn]]): *"Boris literally runs his on cron. The /loop command in Claude Code uses cron under the hood."*
- **`/usage` slash command surfaced** (2026-06-08 X reply, [[bcherny-5-tips-opus-autonomous-2026-06-05]]): *"Run `/usage` to see a breakdown of the specific skills, mcps, and plugins that are using your tokens."* First wiki-captured per-skill / per-MCP / per-plugin token-breakdown primitive.

## Where to Follow

- X: [@bcherny](https://x.com/bcherny)
- Wiki sources: [[bcherny-5-tips-opus-autonomous-2026-06-05]], [[mvanhorn-wtf-is-a-loop-2026-06-07]], [[willison-code-w-claude-2026]], [[ai-ascent-2026]]
- Related concept: [[loop-engineering]]
