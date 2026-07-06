---
title: "sqlite-utils 4.0rc2, mostly written by Claude Fable (for about $149.25)"
type: source
medium: article
url: https://simonwillison.net/2026/Jul/5/sqlite-utils-fable/
ingested: 2026-07-06
---

## Summary

[[simon-willison|Simon Willison]] shipped `sqlite-utils` 4.0rc2 with most of the work done by [[claude-fable-5|Claude Fable 5]], spending **$149.25** total, and published a full itemized cost breakdown. The constraint — his Fable allowance expiring at the July 7 price change — is what forced the "actually ship it" decision. Surfaced in the [[dailybrief-roundup-2026-07-06|2026-07-06 Daily Brief]].

## Key Claims / Takeaways

- **Workflow**: upgraded to Claude Max ($200/mo) to maximize Fable allowance before July 7. Opened with a single directive — *"Final review before shipping a stable 4.0 release — very important to spot any last minute things that would be a breaking change if we fix them later."* Ran **37 prompts across 30 files → 34 commits**.
- **Catastrophic bug caught**: Fable found a data-loss bug in `delete_where()` that never committed changes and poisoned the DB connection for subsequent operations — the kind of bug that, if shipped, forces an emergency major-version bump.
- **Fable's contributions**: fixed transaction handling throughout the codebase; generated transaction docs; ran Python 3.12 autocommit compatibility testing; fixed `db.query()` / `INSERT ... RETURNING` edge cases; wrote release notes Willison rated better than his own. He notes reviewing the doc edits first was "an *excellent* way to build an initial understanding of what has changed."
- **Cost breakdown (via AgentsView)**:
  | Component | Cost |
  |---|---|
  | Main session (claude-fable-5) | $141.02 |
  | API-surface sweep agent | $2.40 |
  | Transactions/atomic review agent | $2.39 |
  | Post-rc1 commits review agent | $1.72 |
  | Migrations review agent | $1.40 |
  | Prompt-counting agent (claude-opus-4-8) | $0.32 |
  | **Total** | **$149.25** |
- **Takeaway on judgment**: AI didn't remove the SemVer judgment call — Willison's policy of keeping incompatible major versions rare stayed in the *decision-making*, not the execution. Catching the data-loss bug pre-release meant a safe `4.0.1` patch path instead of an emergency `5.0`.

## Why it matters

Concrete, itemized data point on AI-assisted OSS: a real maintainer, a real release, a real dollar figure. Complements the [[ai-margin-collapse]] economics from the *cost* side (what a serious agentic coding session actually bills) and the [[dailybrief-roundup-2026-07-03|Fable-5 burn-rate cluster]].

## Pages Updated

- [[simon-willison]] (updated)
- [[claude-fable-5]] (updated — real-world OSS usage + cost)
- [[dailybrief-roundup-2026-07-06]]
