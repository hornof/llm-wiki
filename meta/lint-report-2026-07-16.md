---
type: meta
title: "Lint Report 2026-07-16"
created: 2026-07-16
updated: 2026-07-16
tags: [meta, lint]
status: clean
---

# Lint Report: 2026-07-16

Delta cycle covering the 07-16 ingest (Thinking Machines' Inkling open-weights launch + Claude `web_fetch` exfiltration). **Clean — no fixes required.**

## Results

| Check | Result |
|---|---|
| Orphan entity pages | **0** |
| Stale tool/model pages (>60d) | **0** — 07-15 refresh of claude-design/dac/river cleared the batch |
| Tools missing a Traction Signals section | **0** |
| `sources/` missing a `Pages Updated` section | **0** |
| New ghost / broken links this cycle | **0** |
| Orphans among new pages | **0** — `thinking-machines`, `inkling`, `mira-murati` = 5 inbound each |

## Notes
- Only flagged item: `[[agi-debate.canvas]]` in `index.md` — a canvas embed reference (category-F artifact per [[ghost-node-audit-2026-07-06]]), not a broken link.
- Care during the 07-16 ingest paid off: `mira-murati` was created (not left as a ghost), and a `[[lethal-trifecta]]` reference was unlinked to plain text (no such page) — so no new ghosts entered.
- iCloud `glob` caveat still applies — findings verified via per-target `os.path.exists`.

## Actions
None beyond this report.
