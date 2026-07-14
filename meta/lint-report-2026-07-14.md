---
type: meta
title: "Lint Report 2026-07-14"
created: 2026-07-14
updated: 2026-07-14
tags: [meta, lint]
status: clean
---

# Lint Report: 2026-07-14

Delta cycle covering the 07-13 (context-engineering + Self-Writing Vault) and 07-14 (Nadella Reverse Information Paradox + Vorflux + Mira correction) ingests. **Clean — no fixes required.**

## Results

| Check | Result |
|---|---|
| Stale tool/model pages (>60d) | **0** |
| Tools missing a Traction Signals section | **0** — `vorflux`, `mira` both carry sourced signals |
| `sources/` missing a `Pages Updated` section | **0** |
| New ghost / broken wikilinks in 07-13 & 07-14 pages | **0** |
| Orphans among new pages | **0** — `context-engineering` (5 inbound), `reverse-information-paradox` (6), `vorflux` (2), `mira` (3) |

## Notes

- **`[[backlinks]]`** in `chewadot-self-writing-vault-8-rules-2026-06-29` + `llm-wiki-pattern` is a **false positive** — it sits inside inline-code backticks (`` `[[backlinks]]` ``), which Obsidian renders as literal text, not a link. No ghost node created.
- **`[[agi-debate.canvas]]`** (index) is a canvas embed reference (category-F artifact per [[ghost-node-audit-2026-07-06]]).
- **`[[rahulgs]]` / `[[samueljmcd]]` / `[[sydney-runkle]]`** in `loop-engineering` are the known dual-slug people tail from the standing audit — pre-existing, not introduced by the recent ingests.
- The Mira correction (07-14) cleanly resolved a prior "Mira = model" misattribution and the previously-dangling `[[mira]]` link — no residue.
- Out-of-band this window: the `claude-review` CI workflow was temporarily instrumented for debugging (a 401 auth incident) and **restored byte-exact** to canonical; not wiki content, noted for completeness.
- iCloud `glob` caveat still applies — all graph findings verified with per-target `os.path.exists`, not raw `glob`.

## Actions

None beyond this report.
