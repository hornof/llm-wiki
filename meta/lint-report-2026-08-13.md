---
type: meta
title: "Lint Report 2026-08-13"
created: 2026-08-13
updated: 2026-08-13
tags: [meta, lint]
status: applied
---

# Lint Report: 2026-08-13

Delta cycle covering the two ingests since the 08-12 lint — **#241** (a16z/Garry Tan "experienced-founder" clip) and **#242** (Garry Tan full transcript + Ryan Greenblatt + Grok 4.6). **3 fixes applied.**

## Results

| Check | Result |
|---|---|
| Orphan entity pages | **0** |
| Stale tool/model pages (>60d) | **0** |
| Tools missing a Traction Signals section | **0** |
| `sources/` missing a `Pages Updated` section | **0** |
| New ghost links from delta ingest pages (#241–242) | **0** |
| Pre-existing entity-page ghosts | **3 fixed / 6 left-by-design** |

Corpus: 843 files / 842 pages / 1021 link-targets.

## Fixes applied (all pre-existing, not from #241–242)

1. **`people/andy-jassy` — broken slug** `[[claude-mythos-5]]` → `[[claude-mythos|Mythos 5]]`. The model page is `claude-mythos`; `-5` was a wrong-slug dangler (a genuine broken link, not a create-marker). *(The same string in old `meta/lint-report-*` + `log.md` is left — historical records, not live links.)*
2. **`companies/anysphere` — finished the #240 unlink.** #240 only unlinked `origin`/`tomas-reimers` in the *Resources* section; the body prose still carried `[[tomas-reimers|…]]` (×2) + `[[origin|…]]`. Unlinked those to plain text for consistency. *(Tomas Reimers = Cursor/Anysphere founder — a defensible create-candidate, but kept plain-text per the #240 decision; page it via an ingest if he recurs substantively.)*
3. **`people/david-sacks`** — `[[trump|Donald Trump]]` → plain text (one-off political-figure name, no tracked-entity page warranted).

## Left by design (not defects)

These "ghosts" are the wiki's **own intentional forward-markers** or **illustrative syntax** — resolving them would misrepresent intent:
- **`tools/openclaw` → `[[hermes-agent]]`** — explicitly annotated *"single-source-defer carry-over."* Note: **Hermes / Hermes-Agent is now a strong create-candidate** — it's recurred across QM, Buzz, and Garry Tan's token-max advice (#242). Flagging for the next Hermes-heavy ingest.
- **`companies/pleias` → `[[europe-2031-initiative]]`, `[[pierre-carl-langlais]]`** — both annotated *"entity-page candidate; single-source defer."*
- **`tools/obsidian` → `[[Page Name]]`, `[[wikilink]]`** — Obsidian wikilink-syntax *examples* on the Obsidian page itself; **`[[0xwhrrari]]`** — a June one-off handle (cosmetic).
- **`concepts/llm-wiki-pattern` → `[[backlinks]]`** (illustrative, inside a quote describing a cron), **`[[index]]`** (root file, resolves in Obsidian).

## Delta detail (#241–242)
New pages: `people/ryan-greenblatt`, `people/garry-tan` (existing, deepened), source pages `garry-tan-new-rules-for-founders-a16z-2026-08-13` + `dailybrief-roundup-2026-08-13`. All verified; **0 new ghosts introduced.**

## Watch-items / standing create-candidates
- **`hermes-agent` / `Hermes`** — now recurred enough (openclaw, QM, Buzz, Garry Tan) to warrant a `tools/hermes` page on next surface.
- **`herdr`, `aws`** — standing create-candidates.
- **`bun`, `claude-mythos`** — freshness-bumped in #240; want a *real* refresh on next stale cycle.

## Actions
Applied 3 ghost fixes (slug repair + 2 unlinks); documented the by-design remainder. Recorded here.
