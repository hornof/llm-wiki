---
type: meta
title: "Lint Report 2026-07-24"
created: 2026-07-24
updated: 2026-07-24
tags: [meta, lint]
status: clean
---

# Lint Report: 2026-07-24

Delta cycle covering the 07-21 (Bessent sanctions), 07-22 (OpenAI $750B), and 07-23 (ExploitGym reward-hacking incident + Buzz) ingests. **Clean — no fixes required.**

## Results

| Check | Result |
|---|---|
| Orphan entity pages | **0** |
| Stale tool/model pages (>60d) | **0** |
| Tools missing a Traction Signals section | **0** |
| `sources/` missing a `Pages Updated` section | **0** |
| New ghost / broken links this cycle | **0** |
| Orphans among new pages | **0** — `reward-hacking` (4 inbound), `buzz` (4), `poolside` (2) |

## Notes
- Only flag: `[[agi-debate.canvas]]` in `index.md` — canvas embed reference (category-F artifact per [[ghost-node-audit-2026-07-06]]), not a broken link.
- No new ghosts across three ingests — deferred/one-off names (Bessent, Ben Thompson, Thomas Ptacek, Eiso Kant) kept as plain text.
- `poolside` is lightly linked (2 inbound: roundup + index) but not an orphan; single-source entity, expected.
- iCloud `glob` caveat still applies — findings verified via per-target `os.path.exists`.

## Actions
None beyond this report.
