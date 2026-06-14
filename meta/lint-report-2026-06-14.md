---
type: meta
title: "Lint Report 2026-06-14"
created: 2026-06-14
updated: 2026-06-14
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-06-14

## Summary

- **Pages scanned**: 504 (excluding `_raw/`, `Daily Briefs/`, `.git/`, `.obsidian/`, `meta/`, `archive/`)
- **Frontmatter gaps**: **0**
- **Stale `last_updated`** (>60 days) on tools/models: **0**
- **Orphan content pages** (no inbound wikilinks): **0** (new ingest pages all have ≥2 inbound links)
- **Real fixable**: **4 entity-page candidates past 2-surface threshold** (`andy-jassy` 4 surfaces; `shane-legg` 5 surfaces; `matei-zaharia` 2 surfaces; `sarah-guo` 2 surfaces) + **2 wrong-slug fixes** (`[[concepts/agentic-coding]]` → `[[agentic-engineering]]`; `[[concepts/hallucination]]` backtick-quote) + **1 single-surface theker backtick-quote**
- **Unprocessed `_raw/` drops**: **0** net-new
- **Lint branch**: `lint/2026-06-14`

**Wiki health structurally excellent**. 0 orphans / 0 frontmatter gaps / 0 stale dates. The 2026-06-14 Daily Brief + Nadella ingest sequence landed cleanly with no typo regressions in the new pages. **Major signal**: the 2026-06-13 Anthropic-USG-conflict + 2026-06-14 Nadella+brief ingests **promoted 4 prior single-source defers past the 2-surface threshold** simultaneously — pattern-watch flags from `lint-report-2026-06-13` now actionable for entity-page creation.

### Net delta vs `lint-report-2026-06-13`

| Metric | pt13 lint | This lint | Δ |
|---|---|---|---|
| Total pages | 496 | **504** | +8 (Nadella + 3 brief sources + 4 lint-applied pages: elon-musk + google + intel + lint report) |
| Orphans (real) | 0 | **0** | — |
| Frontmatter gaps | 0 | **0** | — |
| Stale `last_updated` | 0 | **0** | — |
| Real fixable typo regressions | 1 (theker) | **2** (concepts/agentic-coding wrong-slug + concepts/hallucination needs backtick) | +1 net (new from 2026-06-14 ingest sources) |
| New entity-page candidates past 2-surface threshold | 1 (elon-musk; now created) | **4** (andy-jassy + shane-legg + matei-zaharia + sarah-guo) | +3 (pattern-watch flags from prior lint now actionable) |
| Unprocessed `_raw/` drops | 0 | **0** | — |

## Dead Links

### Past 2-surface threshold — entity pages worth creating (4 unique / ~13 occurrences) — REAL FIXABLE

| Target | Surfaces | Substantive references | Recommended action |
|---|---|---|---|
| `[[andy-jassy]]` | **4** | (1) [[wsj-amazon-jassy-anthropic-crackdown-2026-06-13]] — primary Jun 13 disclosure (Amazon CEO direct-USG-Anthropic-crackdown actor); (2) [[davidsacks-anthropic-fable-5-export-control-jailbreak-2026-06-13]] — trusted-partner-identity resolved; (3) [[models/claude-fable-5]] — Jun 13 export-control event source; (4) [[people/satya-nadella]] — Anthropic-USG-conflict cluster cross-reference | **Create `people/andy-jassy.md`** — **structurally load-bearing**: Amazon CEO + Anthropic largest-investor-channel + AWS Bedrock partner + USG-warning-channel direct-actor. Closes ~4 dead-link refs. Pattern-watch from prior lint now actionable. |
| `[[shane-legg]]` | **5** | (1) [[shane-legg-four-pathways-agi-superintelligence-2026-06-12]] — focused source already exists; (2) [[karpathy-loopcraft-stacking-loops-2026-06-12]]; (3) [[0xcodez-fable-5-14-step-self-improving-agent-2026-06-11]]; (4) [[dailybrief-roundup-2026-06-12]]; (5) [[companies/google]] | **Create `people/shane-legg.md`** — **structurally load-bearing**: DeepMind co-founder; **focused source page already exists** (4-pathway AGI framework Jun 12); 5 substantive surfaces. Pattern-watch from prior lint now actionable. |
| `[[matei-zaharia]]` | **2** | (1) [[zaharia-omnigent-multi-agent-meta-harness-2026-06-13]] — focused source; (2) [[dailybrief-roundup-2026-06-13]] | **Create `people/matei-zaharia.md`** — Apache Spark creator; Omnigent meta-harness open-source author; Loop Engineering 6th canonical voice. Pattern-watch from prior lint now actionable. |
| `[[sarah-guo]]` | **2** | (1) [[dailybrief-roundup-2026-06-11]]; (2) [[dailybrief-roundup-2026-06-14]] — Latent Space podcast "model labs vs agent labs" + "what's untrainable" framings | **Create `people/sarah-guo.md`** — Conviction Capital founder; investor-side Loop Engineering 8th canonical voice candidate. |

### Wrong-slug + needs-backtick-quote fixes — REAL FIXABLE (2 occurrences / 2 sources)

| Wrong | Correct | File | Note |
|---|---|---|---|
| `[[concepts/agentic-coding]]` | `[[agentic-engineering]]` | sources/dailybrief-roundup-2026-06-14.md | Wrong slug — `agentic-engineering` is the canonical concept page (Karpathy framing); `agentic-coding` not a separate concept |
| `[[concepts/hallucination]]` | `` `[[concepts/hallucination]]` `` | sources/kpmg-pulls-ai-report-hallucinations-2026-06-13.md | No `concepts/hallucination.md` page exists; single-source-mention single-surface — backtick-quote per established convention (defer concept-page until 2nd substantive concept-focus surface) |

### Single-surface theker backtick-quote — REAL FIXABLE (1 occurrence)

| Wrong | Correct | File | Note |
|---|---|---|---|
| `[[theker]]` | `` `[[theker]]` `` | sources/dailybrief-roundup-2026-06-11.md (line 61) | No `theker.md` entity page exists; single-source defer; backtick-quote per established convention |

### Single-source entity-page defers — new from 2026-06-14 ingest (3 unique / 3 occurrences) — no action

Conservative entity-creation policy applies (defer until 2nd substantive surface):

- `[[kpmg]]` (1 ref via [[kpmg-pulls-ai-report-hallucinations-2026-06-13]]; Big-4 firm; pattern-watch for 2nd surface)
- `[[india]]` (1 ref via [[india-meta-manus-geopolitical-ai-fallout-2026-06-13]]; sovereign-LLM strategic-discourse; pattern-watch for 2nd surface)
- `[[manus]]` (1 ref via [[india-meta-manus-geopolitical-ai-fallout-2026-06-13]]; identity verification-pending; pattern-watch for 2nd surface)

### Carry-over single-source entity-page defers from prior lints (~45 unique / ~45 occurrences) — no action

Carry-over single-source entity defers from rapid pt7-pt13 ingest cadence + 2026-06-14 brief. Conservative entity-creation policy applies. **Pattern-watch list for next lint** (entity-page candidates if 2nd substantive surface appears):

- `[[matt-clifford]]` — 1 ref ([[dailybrief-roundup-2026-06-13]]); ARIA Chair; pattern-watch
- `[[gabriel-petersson]]` — narrative-only refs (no wikilink); OpenAI internal-voice; pattern-watch for direct-wikilink 2nd surface
- `[[mistral]]`, `[[deepseek]]`, `[[qwen]]`, `[[llama]]`, `[[gemma]]`, `[[deepmind]]`, `[[microsoft]]`, `[[apple]]`, `[[cohere]]`, `[[trump]]`, `[[amazon]]`, `[[opik]]`, `[[evo]]`, `[[ona]]`, `[[ariael]]`, `[[allenai]]`, `[[lm-studio]]`, `[[dxc]]`, `[[aria]]`, `[[extropic]]`, `[[biohub]]`, `[[kasra]]`, `[[charity-majors]]` (3 refs; multi-lint carry-over)
- Practitioner-content register single-source defers: `[[0xCodez]]`, `[[0xwhrrari]]`, `[[aiedge]]`, `[[alex-imas]]`, `[[alex-lupsasca]]`, `[[alok-bishoyi]]`, `[[emanuel-maiberg]]`, `[[forrest-chang]]`, `[[geoffrey-irving]]`, `[[geoffrey-huntley]]`, `[[guillaume-verdon]]`, `[[igor-babuschkin]]`, `[[jeremy-howard]]`, `[[lucianw]]`, `[[malay-hazarika]]`, `[[martin-alderson]]`, `[[mcp]]` (single-surface), `[[mcpmatt-pocock]]` (mistake-slug — should be matt-pocock), `[[minchoi]]`, `[[minimax]]`, `[[moonshot-ai]]`, `[[nick-frosst]]`, `[[omnigent]]`, `[[phil-trammell]]`, `[[prometheus]]`, `[[rohan-paul]]`, `[[river-ai]]`, `[[sequent]]`, `[[spectnfa]]`, `[[tejas-kumar]]`, `[[tensorzero]]`, `[[theo-tabah]]`, `[[thepremiseofit]]`, `[[z-ai]]`, `[[anton-leicht]]`

### Path-form trailing-backslash table-cell-escape artifacts (~25 occurrences) — false positives

Pattern: wikilinks inside markdown table cells use `\|` to escape pipes (e.g., `[[slug\|alias]]`), causing the regex scanner to capture a trailing `\` character. **Not a real dead-link** — Obsidian resolves these correctly. Examples: `[[openai-federal-ai-safety-framework-2026-06-03\]]`, `[[wharton-ai-2-7x-productivity-multiplier-2029-2026-06-08\]]`, `[[trump-narrower-ai-eo-2026-06-02\]]`, etc. (24 unique sources affected). No action.

### Path-form persistent dead-links (carryover) — pattern-watch / no action

- `[[meta/lint-report-2026-06-13]]` + `[[meta/lint-report-2026-05-11]]` — EXIST as path-form refs (resolve correctly); scanner false positives
- `[[concepts/agentic-coding]]` (1 ref) + `[[concepts/hallucination]]` (1 ref) — flagged above as wrong-slug + needs-backtick respectively

### Backtick-quoted historical-narrative refs — false positives (multi-lint carry-over)

`` `[[claude-opus-4-6]]` `` (log.md historical entry) + `` `[[theker-85m-reconfigurable-factory-robot-2026-06-11]]` `` (log.md prior-lint fix-narrative) + `` `[[claude-fable-5]]` `` / `` `[[claude-code]]` `` / `` `[[anthropic]]` `` (log.md prior-lint trailing-backslash table artifacts inside backticks). No action — backtick-quoting is the established convention for these historical references.

### Teaching-example / structural false positives (~14 occurrences) — no action

Unchanged structural patterns: `[[claude]]` / `[[concept]]` / `[[wikilink]]` / `[[wrong-slug]]` / `[[Page]]` (teaching examples in CLAUDE.md / obsidian.md / llm-wiki-pattern.md code blocks); `[[Daily]]` (path-form `[[Daily Briefs/...]]` × 5); `[[index]]` + `[[index.md]]` (self-refs); `[[agi-debate.canvas]]` (canvas file); `[[anthropic-xai-colossus-2026-05]]` (log.md archival fix-narrative).

## Unprocessed `_raw/` Drops

**0 net-new unprocessed drops**. `_raw/` contains 8 recent files; all already-ingested or explicitly skipped per prior lint reviews:

- `A frontier without an ecosystem is not stable.md` — ingested into [[satya-nadella-frontier-ecosystem-not-frontier-model-2026-06-14]]
- `Post by @gregisenberg on X 2.md`, `Post by @gregisenberg on X 1.md` — ingested into [[gregisenberg-fable-5-ban-local-models-pivot-2026-06-13]] + adjacent
- `Post by @DavidSacks on X.md` — ingested into [[davidsacks-anthropic-fable-5-export-control-jailbreak-2026-06-13]]
- `Post by @minchoi on X 2.md`, `Post by @ThePremiseOfIt on X.md` — explicitly skipped (low-signal carry-over)
- `Claude Fable is relentlessly proactive.md` + `Claude Fable is relentlessly proactive 1.md` — duplicates; ingested into [[models/claude-fable-5]] adjacent

## Pre-Lint Discipline Verification

1. `git fetch origin` → ✅
2. `git pull --ff-only` → ✅ at PR-103-merged tip
3. `gh pr list --state open` → empty
4. **Lint branch**: `lint/2026-06-14`

## Recommended Fixes

### Required (4 entity-page creations past 2-surface threshold + 3 typo fixes)

1. **Create `people/andy-jassy.md`** — 4 substantive surfaces; structurally load-bearing (Amazon CEO + Anthropic-USG-crackdown actor + AWS Bedrock partner + Anthropic largest-investor-channel); closes ~4 dead-link refs
2. **Create `people/shane-legg.md`** — 5 substantive surfaces; **focused source page already exists** (4-pathway AGI framework); DeepMind co-founder; closes ~5 dead-link refs
3. **Create `people/matei-zaharia.md`** — 2 substantive surfaces; Apache Spark creator + Omnigent meta-harness author; Loop Engineering 6th canonical voice; closes ~2 dead-link refs
4. **Create `people/sarah-guo.md`** — 2 substantive surfaces; Conviction Capital founder; investor-side Loop Engineering 8th-voice candidate; closes ~2 dead-link refs
5. **Fix `[[concepts/agentic-coding]]` → `[[agentic-engineering]]`** in `sources/dailybrief-roundup-2026-06-14.md` (wrong-slug; canonical concept exists)
6. **Backtick-quote `[[concepts/hallucination]]`** → `` `[[concepts/hallucination]]` `` in `sources/kpmg-pulls-ai-report-hallucinations-2026-06-13.md` (no concept page exists; defer)
7. **Backtick-quote `[[theker]]`** → `` `[[theker]]` `` in `sources/dailybrief-roundup-2026-06-11.md:61` (no entity page exists; single-source defer)

### Optional (pattern-watch flags for next lint)

- `[[matt-clifford]]` 2nd substantive surface watch (ARIA Chair)
- `[[gabriel-petersson]]` direct-wikilink 2nd surface watch (OpenAI internal-voice)
- `[[kpmg]]` 2nd substantive surface watch (Big-4 enterprise-AI-failure cluster)
- `[[india]]` 2nd substantive surface watch (sovereign-LLM strategic-discourse)
- `[[manus]]` 2nd substantive surface watch (identity verification-pending)
- Chinese-open-weight-vendor cluster: `[[minimax]]` + `[[moonshot-ai]]` + `[[z-ai]]` 2nd substantive surfaces
- `[[trump]]` + `[[amazon]]` entity-page candidates (multi-source recurring)
- `[[mistral]]` Series D confirmed announcement (currently rumored)
- `[[charity-majors]]` (3 refs multi-lint carry-over)
- Fix `[[mcpmatt-pocock]]` typo (should be `[[matt-pocock]]`)

## Overall Posture

Wiki health structurally excellent. The 2026-06-14 Daily Brief + Nadella ingest sequence + 2026-06-13 Anthropic-USG-conflict cluster have **promoted 4 prior pattern-watch single-source defers past the 2-surface threshold simultaneously** — exceptional yield from pattern-watch discipline.

**Major narrative tracking established**:
- **9-narrative-event 11-day Anthropic-USG-conflict crisis cluster** (now extended via India sovereignty fallout) is the most-load-bearing wiki-tracked governance event of the 2026-Q2 frontier-AI period
- **8-voice Loop Engineering canonical cluster** now extending with Zaharia (6th) + Nadella (7th) + Sarah Guo (8th-candidate at 2nd substantive surface)
- **Microsoft-Anthropic-OpenAI 1-day 3-vendor enterprise-AI-positioning cluster** (Nadella + Guo + Petersson) demonstrating cross-vendor consensus-discourse pattern

**Tracking for next lint**:
- New pattern-watches per above (matt-clifford, gabriel-petersson, kpmg, india, manus)
- `[[trump]]` + `[[amazon]]` recurring multi-source candidates
- Continued Chinese-open-weight-vendor cluster 2nd surfaces
- Open-weight model attestation pattern (Rio 3.5 = Nex N2 + Qwen 3.5 merge from brief)
