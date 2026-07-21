---
type: meta
title: "Lint Report 2026-07-20"
created: 2026-07-20
updated: 2026-07-20
tags: [meta, lint]
status: clean
---

# Lint Report: 2026-07-20

Delta cycle covering the 07-17 (Kimi K3 + Apple-OpenAI escalation) and 07-20 (Anthropic $1.5B copyright settlement + Lila science-data-frontier) ingests. **Clean — no fixes required.**

## Results

| Check | Result |
|---|---|
| Orphan entity pages | **0** |
| Stale tool/model pages (>60d) | **0** |
| Tools missing a Traction Signals section | **0** |
| `sources/` missing a `Pages Updated` section | **0** |
| New ghost / broken links this cycle | **0** |
| Orphans among new pages | **0** — `kimi-k3` (6 inbound), `science-as-training-data-frontier` (4 inbound) |

## Notes
- Only flag: `[[agi-debate.canvas]]` in `index.md` — canvas embed reference (category-F artifact per [[ghost-node-audit-2026-07-06]]), not a broken link.
- No new ghosts introduced across two ingests — recurring/deferred entities (Sam Altman, Ben Thompson, Lila Sciences) were kept as plain text, not linked into non-existent pages.
- iCloud `glob` caveat still applies — findings verified via per-target `os.path.exists`.

## Actions
None beyond this report.
