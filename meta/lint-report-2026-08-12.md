---
type: meta
title: "Lint Report 2026-08-12"
created: 2026-08-12
updated: 2026-08-12
tags: [meta, lint]
status: applied
---

# Lint Report: 2026-08-12

Delta cycle covering the four ingests since the 08-04 lint — **#236** (Jeff Dean / DiscoLoop + SKILL.md), **#237** (Astra / DOE Genesis / Tokenpocalypse), **#238** (autonomous-company / safety-test containment), **#239** (Muse Glimmer / BioAI / Cognition $40B / Daybreak). **Owner consulted on 2 judgment calls; 1 new page + 1 real refresh + fixes applied.**

## Results

| Check | Result |
|---|---|
| Orphan entity pages | **0** |
| Tools missing a Traction Signals section | **0** |
| `sources/` missing a `Pages Updated` section | **0** |
| New ghost links from delta ingest pages (#236–239) | **0** |
| Pre-existing entity-page ghosts | **3 → fixed** |
| Stale tool/model pages (>60d) | **3 → resolved (2 freshness-bump, 1 real refresh)** |

Corpus: 837 files / 836 pages / 1017 link-targets (→ +2: `companies/amazon` new; Cowork refreshed).

## Fixes applied

### Entity-page ghosts (3, pre-existing — not from #236–239)
- **`companies/anysphere`** — `[[origin]]` + `[[tomas-reimers]]` (Anysphere founder's same-day Git-for-agents side-launch): **unlinked to plain text** (one-off names, no pages warranted).
- **`companies/microsoft`** — `[[amazon]]` was flagged `canonical-page-pending`. **Resolved by creating the page** (see below) rather than unlinking — Amazon is a major recurring entity (AWS, Anthropic's compute/capital partner, the 4-vendor cluster) and [[andy-jassy]] (its CEO) already dangled from it. *(Owner-approved.)*

### Stale tool/model pages (3)
Handled per **content-availability**, not a blanket date-bump:
- **`tools/bun`** (68d) + **`models/claude-mythos`** (64d) — **freshness date-bump only.** Both are stable-content pages (Bun's Zig→Rust port is a completed historical receipt; Mythos is an announced model) with no new material surfaced in the delta. Honest freshness bumps, not refreshes.
- **`tools/claude-cowork`** (65d) — **real content refresh** (owner-approved; fetched [claude.com/product/cowork](https://claude.com/product/cowork)). Cowork has broadened past "a tab in Desktop": now **desktop + web (rolling out) + mobile beta + ChromeOS**, with **visual step-transparency, unattended/parallel execution, an effort control**, Enterprise **observability (OpenTelemetry) + private plugin marketplaces**, and a **domain migration** (`anthropic.com/product/*` → `claude.com/product/*`). This is the correct model for stale *active-product* pages — refresh, don't hollow-bump.

## New page
- **`companies/amazon`** (stub) — created to close the `microsoft`→`amazon` pending link + the `andy-jassy` dangle. Covers AWS, the Anthropic compute/capital partnership, and the 4-vendor cluster; flagged for expansion on the next Amazon-heavy ingest.

## Delta detail (#236–239)
New pages this window: `discoloop-ai`, `jeff-dean`, `forward-deployed-engineer` (wait — that was #233, pre-lint), `muse-glimmer`, `replit` (#234, pre-lint). This lint's window (#236–239) added `discoloop-ai`, `jeff-dean`, `muse-glimmer` + source pages — all verified, **0 new ghosts introduced.**

## Not in scope (known long-tail / false positives)
- **Historical June/July one-off `[[handle]]` backlog** in `sources/` pages (`dean-ball`, `life-sci-bench`, `boston-childrens-hospital`, `gpt-5-4`, `in-the-weights`, `thomas-dimson`, …) — live in source/cluster pages, not entity pages. Unchanged.
- **`[[index]]` / `[[log]]`** root-file false positives; **`[[agi-debate.canvas]]`** artifact.

## Watch-items / standing create-candidates
- **`Hermes`**, **`herdr`** — recurring harness names, still plain-text.
- **`aws`** — referenced but no page (folds into the new `amazon` for now).
- **Freshness-bumped emerging pages** (`bun`, `claude-mythos`) will want a *real* refresh, not another bump, on their next stale cycle.

## Actions
Applied: 3 ghost fixes, 2 freshness bumps, 1 Cowork refresh, 1 new Amazon stub. Recorded here.
