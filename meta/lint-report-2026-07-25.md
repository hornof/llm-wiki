---
type: meta
title: "Lint Report 2026-07-25"
created: 2026-07-25
updated: 2026-07-25
tags: [meta, lint]
status: applied
---

# Lint Report: 2026-07-25

Delta cycle covering the 07-23 (Buzz) and 07-25 (Claude Opus 5 + Prentis/FLUX 3 + governance) ingests. Clean except **one staleness/contradiction fixed**.

## Results

| Check | Result |
|---|---|
| Orphan entity pages | **0** |
| Stale tool/model pages (>60d) | **0** |
| Tools missing a Traction Signals section | **0** |
| `sources/` missing a `Pages Updated` section | **0** |
| New ghost / broken links this cycle | **0** |
| Orphans among new pages | **0** — `claude-opus-5` (4 inbound), `prentis` (2), `flux-3` (2) |
| **Contradiction / staleness** | **1 → fixed** |

## Fix applied
- **`index.md`** described `claude-opus-4-8` as the *"current recommended Claude Code model,"* which the 07-25 [[claude-opus-5]] launch made stale (Opus 5 is now the default). Updated the line to *"superseded as default by Opus 5 (2026-07-24)."* The `claude-opus-4-8.md` body itself carries no "current" claim (no contradiction there).

## Notes
- Only dangling link: `[[agi-debate.canvas]]` in `index.md` — canvas embed artifact (category-F per [[ghost-node-audit-2026-07-06]]).
- No new ghosts — one-off names (Reid Hoffman, Mark Pincus, Black Forest Labs, Cognition/Poke) kept as plain text.
- `prentis` / `flux-3` lightly linked (2 inbound each: roundup + index) but not orphans — single-source entities, expected.
- iCloud `glob` caveat still applies — findings verified via per-target `os.path.exists`.

## Actions
Fixed the Opus-4.8 "current" staleness in `index.md`; recorded here.
