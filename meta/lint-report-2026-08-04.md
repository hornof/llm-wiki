---
type: meta
title: "Lint Report 2026-08-04"
created: 2026-08-04
updated: 2026-08-04
tags: [meta, lint]
status: applied
---

# Lint Report: 2026-08-04

Delta cycle covering the three ingests since the 08-02 lint — **#232** (recap/catch-up brief), **#233** (Forward-Deployed Engineer), **#234** (Replit self-driving company / Anthropic+Volta / open-weight safety gap). **1 fix applied.**

## Results

| Check | Result |
|---|---|
| Orphan entity pages | **0** |
| Tools missing a Traction Signals section | **0** |
| `sources/` missing a `Pages Updated` section | **0** |
| New ghost links from delta ingest pages (#232–234) | **0** |
| Entity-page ghosts (any entity page) | **0** |
| Stale tool/model pages (>60d) | **1 → fixed** |

Corpus: 828 files / 827 pages / 1009 link-targets.

## Fix applied

- **`tools/marble` — stale (62d)**, `last_updated` 2026-06-03 → 2026-08-04. **Freshness bump, not a substantive refresh**: no new World Labs / Marble information surfaced in the intervening ingests, and the existing content (World Labs' 3D world-generation product; the Fei-Fei Li renderer/simulator/planner taxonomy) is stable and uncontradicted. Flagged as a **watch-candidate for a real refresh** the next time World Labs or Marble surfaces — it's `status: emerging`, so a genuine update (not just a date bump) will eventually be warranted.

## Delta detail (#232–234)

New pages: `concepts/forward-deployed-engineer` (#233), `companies/replit` (#234) + source pages (`sairahul1-fde-no-bs-guide`, `raw-batch-roundup-2026-08-02-pt2`, `dailybrief-roundup-2026-08-02`/`-08-04`). All verified present; every wikilink introduced by the three ingests resolves. #234 touched dense pages (`openai`, `anthropic`, `frontier-ai-governance`, `ai-native-organizations`, `jack-clark`) with **zero new ghosts**.

## Not in scope (known long-tail / false positives)

- **Historical June one-off `[[handle]]` backlog** in `sources/` pages (`aiedge`, `alex-albert`, `ben-thompson`, `dean-ball`, `extropic`, `guillaume-verdon`, `stratechery`, `pentagon`, …) — these live in June cluster/roundup *source* pages, not entity pages; unchanged from every prior cycle. (The lint's substring match surfaces them because `anthropic-*`/`openai-*` source slugs share a prefix with the entity pages.)
- **`[[index]]` / `[[log]]`** — resolve in Obsidian (root files); scan false-positives.
- **`[[agi-debate.canvas]]`** — canvas-embed artifact.

## Watch-items (not defects)
- **`Hermes`** + **`herdr`** — recurring harness names still plain-text (create-candidates alongside `openclaw`).
- **`marble`** — emerging product page now on a pure freshness-bump; wants a real refresh on next surface.

## Actions
Applied the marble date bump; recorded here.
