---
title: "A practical guide to shipping with Claude Code"
type: source
medium: twitter-thread
url: https://x.com/addyosmani/status/2125492213903978917
ingested: 2026-11-25
local_source: "_raw/A practical guide to shipping with Claude Code.md"
---

## Summary

Addy Osmani's X article on using Claude Ship, written *"based on my experience on the Claude Code team"*. It covers the three agents (Code Review, PR Steward, Claude Approvals), the `/code-review`, `/ship` and `/steward` commands, where to write recurring lessons down (CLAUDE.md, REVIEW.md, a `verify` skill, a `steward` skill), and how to roll out an approval policy from observe mode to enforcement. It adds operational detail and safety caveats that the launch post ([[claude-ship-launch-2026-11-23]]) didn't have.

## Key Claims / Takeaways

- **Status** (Osmani): *"Code Review is generally available, and the other two are in beta."* `/ship` works *"even before an admin has turned on any of the agents."*
- **What `/ship` does**: commits pending changes *"as if you had run git add -A"*, pushes, opens the PR, runs `/code-review` and fixes what it judges valid, then watches the PR *"for up to seven days"* for failing checks, conflicts and comments. It won't commit rule files (CLAUDE.md, REVIEW.md, `.claude/`, `.github/`) or files that look like secrets, and in public repos it commits nothing.
- **The watch runs as you, locally**: it uses your quota, stops if the laptop closes, needs its own checkout, and won't run in bypass-permissions mode. It *"pushes at most 3 times for a given issue"* before escalating to the author.
- **Security caveat** (Osmani): the watch merges the base branch and runs your tests, so *"anyone who has the ability to land changes on the base branch has the ability to run commands on your machine during the watch."* Its commits also skip git hooks.
- **`/steward`** runs only the watch, for an existing PR. It's distinct from the cloud PR Steward, which runs as `claude[bot]`.
- **Rule of thumb for rules**: *"a pattern has to be repeated on at least 2 PRs to be considered for a rule"*, a person approves the rule PR, and rules get deleted when stale. Repeated setup goes in `.claude/skills/verify/SKILL.md`, PR housekeeping in `.claude/skills/steward/SKILL.md`.
- **Approval policy**: `.claude/approvals.yml` on the default branch; start in `mode: observe`; *"Claude's approvals count as real approvals on GitHub"*; with auto-merge and author-only policies, PRs can merge *"without anyone doing anything"*. A policy that names Code Review starts billed reviews even in observe mode.
- **Responsibility** (Osmani): *"the person who called the agent is responsible for a change. It's as if they typed it themselves."*

## Pages Updated

- [[claude-code]]
- [[addy-osmani]]
