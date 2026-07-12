---
type: meta
title: "Lint Report 2026-07-12"
created: 2026-07-12
updated: 2026-07-12
tags: [meta, lint]
status: clean
---

# Lint Report: 2026-07-12

Delta cycle after a busy day (ingests #180/#182/#185, the #185 re-target fix, and the #186 `.obsidian/` untracking). **Clean — no fixes required.**

## Results

| Check | Result |
|---|---|
| Stale tool/model pages (>60d) | **0** |
| Tools missing a Traction Signals section | **0** — the 3 new tool pages (`superpowers`, `context7`, `claude-mem`) all carry sourced Traction Signals |
| `sources/` missing a `Pages Updated` section | **0** |
| New ghost / broken wikilinks in the #185 batch | **0** (authoritative per-target existence check) |
| Orphans among new pages | **0** — `superpowers`/`context7`/`claude-mem` = 4 inbound each; `charlie-hills` = 2 |

## Notes

- **`[[agi-debate.canvas]]` in `index.md`** is a canvas *embed* reference, not a broken page link — a known extraction artifact (category F of [[ghost-node-audit-2026-07-06]]). Left as-is.
- **Ghost-node tail** unchanged from the standing [[ghost-node-audit-2026-07-06]]; the day's new pages introduced none of it. (Creating `people/addy-osmani` earlier this week *resolved* two prior ghost refs; `people/charlie-hills` + the 3 tool pages were all created with inbound links in place.)
- **`.obsidian/` untracking (#186)** verified: nothing under `.obsidian/` remains tracked; whole folder now ignored.
- iCloud `glob` caveat still applies (see [[lint-report-2026-07-10]]) — all graph findings verified with per-target `os.path.exists` / `grep`, not raw `glob`.

## Actions

None beyond this report.
