---
type: meta
title: "Lint Report 2026-07-26"
created: 2026-07-26
updated: 2026-07-26
tags: [meta, lint]
status: applied
---

# Lint Report: 2026-07-26

Delta cycle covering the **07-26 ingest** (Anthropic's official Claude-5 context-engineering rules — the only ingest since the 07-25 lint). **Fully clean — no fixes.**

## Results

| Check | Result |
|---|---|
| Orphan entity pages (excl. sources/owner/meta) | **0** |
| Stale tool/model pages (>60d) | **0** |
| Tools missing a Traction Signals section | **0** |
| `sources/` missing a `Pages Updated` section | **0** |
| New ghost / broken links this cycle | **0** |
| Orphans among 07-26 new pages | **0** — both new files are `sources/` pages (roundup + Thariq primary), inbound-linked from the entity pages they updated |
| Contradiction / staleness | **0** |

Corpus totals: 790 files, 789 entity/source pages, 1027 link-targets.

## Delta detail (07-26 ingest)

- **New:** `sources/dailybrief-roundup-2026-07-26`, `sources/thariq-anthropic-context-engineering-claude-5-rules-2026-07-24`. Both carry `Pages Updated` sections; both are referenced by the entity pages they touched.
- **Edited:** `concepts/context-engineering` (+ vendor-canonical "new rules" subsection), `concepts/claude-md-pattern` (+ `[!update]` callout), `people/thariq-shihipar` (6th surface), `companies/deepseek` (unverified compute-gap leak), `concepts/ai-labor-market-impacts` (Stanford brief). All `last_updated` bumped to 2026-07-26.
- Every wikilink introduced in the delta resolves to an existing page (authoritative per-target check).

## Scan false-positives (noted, not defects)

- **7 "ghost" links in `claude-md-pattern.md`** (`[[forrest-chang\|…]]`, `[[mnilax-claude-md-12-rules-2026-05-09\|…]]`, etc.) are **valid `[[slug\|alias]]` escaped-pipe links inside a markdown table** — correct Obsidian syntax (the `\|` prevents the alias pipe from being read as a table-column separator). All 7 target slugs exist; pre-existing in the lineage table, not introduced this cycle. The lint regex simply didn't strip the table-escaped `\`.
- **Large historical ghost backlog** surfaces if the raw scan is run corpus-wide: hundreds of one-off `[[handle]]` names inside June `sources/` roundup + cluster pages. This is the known long-tail — the health-check is scoped to the **delta since the last lint**, consistent with every prior cycle. Not a regression.
- **`[[agi-debate.canvas]]`** in `index.md` — canvas-embed artifact (category-F per [[ghost-node-audit-2026-07-06]]). Recurring known non-defect.

## Actions

None required — clean cycle. Report filed for the record.
