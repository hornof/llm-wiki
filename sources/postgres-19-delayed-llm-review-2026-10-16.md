---
title: "Postgres 19 delayed after AI reviewers find more bugs than humans can fix"
type: source
medium: article
url: https://www.theregister.com/databases/2026/10/16/postgres-19-delayed-after-ai-reviewers-find-more-bugs-than-humans-can-fix/5303471
ingested: 2026-10-16
---

## Summary

The Register reports PostgreSQL 19 slipping from late September / early October to around **2026-11-19**, with **8–10 significant features reverted** to PostgreSQL 20. Peter Eisentraut (leading committer, VP at EDB) attributes this "at least in part" to LLM-assisted code review, which surfaced many small edge-case defects that would otherwise have shown up years after release. Surfaced by `Daily Briefs/2026-10-16.md`; primary fetched.

## Key Claims / Takeaways

- The constraint was **per-issue overhead, not severity**. Eisentraut describes facing "a list of forty defect reports," each needing only a small fix, with the schedule running out on the cumulative handling cost. Most of the defects were called "relatively harmless."
- **LLM review improved between when features were written and when they shipped**, which raised the effective quality bar mid-cycle.
- **Not all reverts were AI-driven**: some features had architectural defects that were hard to fix in beta, and SQL/PGQ was pulled over unresolved issues (Tom Lane had warned in September of bugs "unfixable until v20").
- Eisentraut says the reverts were not caused by "vibe coding," and that the problem "should sort itself out for future development cycles" if LLM review keeps improving.
- **No tool or vendor is named**, and no total bug count is given. "Forty" is an illustration, not a tally.

*(Single trade-press article. The headline overstates the case; the body describes a triage-time problem, and attribution to LLM review is partial by the quoted committer's own account.)*

## Pages Updated

- [[ai-vulnerability-discovery]], [[claude-code]]
