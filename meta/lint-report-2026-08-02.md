---
type: meta
title: "Lint Report 2026-08-02"
created: 2026-08-02
updated: 2026-08-02
tags: [meta, lint]
status: applied
---

# Lint Report: 2026-08-02

Delta cycle covering the four ingests since the 07-30 lint — **#227** (engineering-stack ladder pt2), **#228** (YC QM harness + Isenberg opportunities), **#229** (stateless MCP / coalition-230+ / Claude cloud computers / DeepSeek V4 Flash), **#230** (Chamath 6-layer guide / grill-driven dev / market-signal markdown / Google tools). **2 fixes applied.**

## Results

| Check | Result |
|---|---|
| Orphan entity pages | **0** |
| Stale tool/model pages (>60d) | **0** |
| Tools missing a Traction Signals section | **0** |
| `sources/` missing a `Pages Updated` section | **0** |
| New ghost links from delta ingest pages | **0** |
| Pre-existing entity-page ghosts | **2 → fixed** |

Corpus: 821 files / 820 pages / 1003 link-targets.

## Fixes applied

Both were **pre-existing** bare person-links (not introduced by #227–230), surfaced this cycle because those ingests edited the host pages. Each sat beside its full source-page link, so both were **unlinked to plain text** — no navigation lost, consistent with the one-off-name convention and prior cycles.

- **`concepts/company-brain`** — `[[eric-siu]]` (introduced by the 2026-06-15 Eric-Siu ingest; surfaced because #230 added the Greg-Isenberg market-signal fold). Source `eric-siu-single-brain-5-layer-company-brain-2026-05-29` stays linked on the same line.
- **`people/greg-isenberg`** — `[[theo-tabah]]` (introduced by the 2026-06-13 ingest; surfaced because #228 added the "biggest opportunities" fold). Source `gregisenberg-theo-tabah-ai-native-masterclass-2026-06-08` remains the anchor.

## Delta detail (#227–230)

New pages: `tools/qm` (#228) + 5 new source pages (`beamnxw-harness-loop-graph-engineering`, `raw-batch-roundup-2026-07-30-pt2`/`-07-31`/`-08-02`, `dailybrief-roundup-2026-07-31`). All verified present; every wikilink introduced by the four ingests resolves. Notable self-correction landed cleanly in #229 (the "ETCLOVG paper" note → @beamnxw's actual explainer).

## Not in scope (known long-tail / false positives)

- **Historical June one-off `[[handle]]` backlog** in `sources/` pages (unchanged; lives in source pages, not entity pages).
- **`[[index]]` / `[[log]]`** — resolve in Obsidian (root files); scan false-positives.
- **`[[agi-debate.canvas]]`** — canvas-embed artifact.

## Watch-items (not defects)
- **`Hermes`** and **`herdr`** — recurring harness names still kept as plain text (create-candidates alongside `openclaw` on a next substantive surface).

## Actions
Applied the 2 unlinks (`eric-siu`, `theo-tabah`); recorded here.
