---
title: "How the Claude Code team does code review"
type: source
medium: article
url: https://claude.dev/blog/solving-code-review-at-anthropic/
ingested: 2026-10-16
---

## Summary

Anthropic engineering post (2026-10-15; [[addy-osmani|Addy Osmani]], Morgan Westlee Lunt, Qing Wang) on how the [[claude-code|Claude Code]] team reviews code now that Claude writes about 90% of it. The goal it states: spend as little human review time as possible without raising revert or incident rates. Machines do most of the reading. Humans approve according to the risk of the change, not who wrote it. Surfaced by `Daily Briefs/2026-10-16.md`; primary fetched.

## Key Claims / Takeaways

- **Volume**: merged PRs on Claude Code more than doubled June→September, and the share reverted fell by more than 40%. Anthropic-wide monorepo changes went from ~2,500/day in May to 30,000+/day in September (same figure as [[anthropic-redesigning-source-control-2026-10-13]]).
- **Target**: most PRs merge with at most one human in the loop. Measured by human approvals per PR (median, p95), human comments, and time waiting on a person. Revert and incident rates act as the guardrail.
- **Seven layers**: (1) pre-PR verification: tests, build, lint, plus a fresh-context subagent reviewing the diff; (2) multi-agent AI review on every PR, where a separate group of agents votes and only findings with enough agreement are posted, tagged Important / Nit / Pre-existing, and each must be fixed or resolved with a reason; (3) a separate security review, with open findings blocking merge; (4) required CI; (5) risk-tiered human approval; (6) merge queue, flags, `latest` before `stable`; (7) flag rollback without deploy, weekly on-call.
- **Risk tiers**: low (docs, copy, flagged additive changes) needs no human once checks are green; medium (ordinary product changes, caching, auto-updater, system prompts) needs one; high needs two. The change sets the tier, not the author. An agent's approval never counts as a person's. The person who prompted the agent counts as a required reviewer. An approval covers a specific commit.
- **Fix at the source**: recurring findings go into `CLAUDE.md`, skills or lint rules. Code owners write a `REVIEW.md` telling the reviewer what matters in their area.
- **Incidents become evals**: past bug-causing PRs form a daily eval set, and every reviewer change is scored against it. Comments are classified by how the author responded (fixed / wrong / intentional / irrelevant) to track noise.
- **Numbers**: internal PRs with a substantive review comment rose from 16% to 54% after the research preview. Passing after one review-and-fix round rose from 65% to 78%. PRs needing 5+ rounds fell from 8.9% to 1.5%. Mean reviews to pass fell from 2.08 to 1.32.
- **The convergence problem**: ~59% of what the reviewer kept flagging was code that predated the PR, so each round dug up a few more old bugs. One CLI PR ran 50+ rounds overnight. The fixes were a three-round cap, diff-only re-review after the first passes, flagging bug classes instead of instances, and no repeat findings.
- [[boris-cherny|Cherny]]: giving Claude a way to verify its work is "probably the most important thing" and makes results "two to three times better."
- Framing line: *"'did a human read the code?' is an imprecise proxy for 'what could go wrong with this change.'"*
- Humans keep: whether to build it, risky paths (billing, auto-updater, CI workflows), architecture, reading the evidence, owning the outcome. *"You land it, you own it."*

*(Vendor engineering blog describing its own process. All figures are internal and unaudited, and the before/after numbers have no stated measurement window.)*

## Pages Updated

- [[claude-code]], [[anthropic]], [[ai-vulnerability-discovery]]
