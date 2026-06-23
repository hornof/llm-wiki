---
type: meta
title: "Lint Report 2026-06-23"
created: 2026-06-23
updated: 2026-06-23
tags: [meta, lint]
status: developing
---

# Lint Report: 2026-06-23

## Summary

- **Pages scanned**: 562 (excluding `_raw/`, `Daily Briefs/`, `.git/`, `.obsidian/`, `meta/`, `archive/`)
- **Frontmatter gaps**: **0**
- **Stale `last_updated`** (>60 days) on tools/models: **5** (all at exactly 63 days — borderline)
- **Orphan content pages** (no inbound wikilinks): **0**
- **Real fixable**: **7 entity-page candidates past 2-surface threshold** (0xcodez 3-surface + anatoli-kopadze + francois-fleuret + thibault-sottiaux + reflection-ai + colossus-2 + allenai/ai2 multi-lint carry-overs) + **0 wrong-slug regressions** (slug-discipline holding!)
- **Unprocessed `_raw/` drops**: **0** net-new
- **Lint branch**: `lint/2026-06-23`

**Wiki health structurally excellent**. 562 pages scanned (+11 from prior lint). 0 orphans / 0 frontmatter gaps / **0 wrong-slug regressions** — slug-discipline lessons holding across multi-lint cadence. **MAJOR cleanup needed**: **7 entity-page candidates past 2-surface threshold** including STRUCTURALLY MAJOR multi-lint-carry-over candidates (0xcodez 3-substantive-surface canonical-voice-tier + reflection-ai canonical-SpaceX-anchor-customer + colossus-2 canonical-substrate-anchor + anthropic-public-record 7-refs + openai-deployment-simulation 4-refs across 4 lints + allenai 3-refs across 3 lints).

### Net delta vs `lint-report-2026-06-20`

| Metric | pt20 lint | This lint | Δ |
|---|---|---|---|
| Total pages | 551 | **562** | +11 (2 entity pages from prior lint + 9 source pages over 3 days) |
| Orphans (real) | 0 | **0** | — |
| Frontmatter gaps | 0 | **0** | — |
| Stale `last_updated` >60d | 0 | **5** | +5 (borderline 63-day: crewai + llama-index + mem0 + obsidian-dataview + obsidian) |
| Real fixable typo regressions | 0 | **0** | — (slug-discipline holding) |
| New entity-page candidates past 2-surface threshold | 2 (hanako + anthropic-public-record; both created) | **7** | +5 (multi-lint carry-overs accumulated + 5 new-from-Jun-21-23 ingests) |
| Unprocessed `_raw/` drops | 0 | **0** | — |

## Dead Links

### Past 2-surface threshold — entity pages worth creating (7 unique / ~21 occurrences) — REAL FIXABLE

| Target | Surfaces | Substantive references | Recommended action |
|---|---|---|---|
| `[[0xcodez]]` / `[[lev-deviatkin]]` | **3-substantive-surface canonical-voice-tier confirmed** | (1) [[0xcodez-fable-5-14-step-self-improving-agent-2026-06-11]] Jun 11 Fable 5; (2) [[0xcodez-14-step-loop-engineering-roadmap-2026-06-20]] Jun 20 14-step canonical-roadmap; (3) [[0xcodez-dynamic-workflows-6-patterns-14-steps-2026-06-21]] Jun 21 Dynamic Workflows canonical-guide | **Create `people/0xcodez.md`** with `[[lev-deviatkin]]` canonical-identity-attribution. **3-surface canonical-voice-tier** = canonical practitioner-content-register voice. Pattern-watch from prior lint actionable. Closes ~4 dead-link refs |
| `[[anatoli-kopadze]]` | **2-substantive-surface** | (1) [[practitioner-claude-settings-features-cluster-2026-06-20]] May 22 "Claude Can Do All of This"; (2) [[anatolikopadze-loops-explained-2nd-surface-2026-06-21]] Jun 20 "Loops explained" canonical-introduction | **Create `people/anatoli-kopadze.md`**. **Entity-page threshold met**. Practitioner-content-register canonical-voice. Closes ~2 dead-link refs |
| `[[francois-fleuret]]` | **2-substantive-surface** | (1) [[dailybrief-roundup-2026-06-20]] Jun 20 speculative-decoding "nearly free lunch" + kache counter-debate; (2) [[dailybrief-roundup-2026-06-21]] Jun 21 LLMs-model-probability-density-of-innovation | **Create `people/francois-fleuret.md`**. Meta FAIR canonical-voice-tier. **Entity-page threshold met**. Pattern-watch from prior lint actionable. Closes ~2 dead-link refs |
| `[[thibault-sottiaux]]` / `[[tibo-sottiaux]]` | **3 refs across 2-substantive-surface** | (1) [[agentic-coding-tooling-cluster-2026-06-17]] Jun 17 Codex open-source-routing canonical-event; (2) [[dailybrief-roundup-2026-06-21]] Jun 21 Codex UX-feedback solicitation + drag-to-reorder thread-layouts iOS | **Create `people/thibault-sottiaux.md`** with `[[tibo-sottiaux]]` slug-variant. OpenAI Codex engineering-lead canonical-voice. **Entity-page threshold met**. Closes ~3 dead-link refs |
| `[[reflection-ai]]` + `[[colossus-2]]` | **2-substantive-surface each** | (1) [[spacex-reflection-ai-150m-month-compute-deal-2026-06-22]] Jun 22 STRUCTURALLY MAJOR $5.4B/$6.3B canonical-event; (2) [[dailybrief-roundup-2026-06-22]] Jun 22 paired-source canonical-event-coverage | **Create `companies/reflection-ai.md`** (canonical-open-source-AI-lab + canonical-SpaceX-anchor-customer) + **`tools/colossus-2.md`** (canonical-SpaceX-substrate-anchor + canonical-multi-tenant canonical-positioning). Closes ~4 dead-link refs |
| `[[anthropic-public-record]]` | **7 refs (multi-lint carry-over)** | Already created `companies/anthropic-public-record.md` in [[meta/lint-report-2026-06-20\|prior lint]] | **NOT a fix this lint** — entity page exists; this entry just confirms canonical-discipline tracking. Verify all refs resolve via path-form `[[companies/anthropic-public-record]]` |
| `[[openai-deployment-simulation]]` | **4 refs across 4 lints** | (1) [[openai-ona-acquisition-deployment-simulation-2026-06-16]] Jun 16 OpenAI 2-event cluster; (2) [[openai-jun-18-7-event-cluster-2026-06-18]] Jun 18 OpenAI 7-event canonical-velocity-cluster; (3) [[deepmind-jun-20-jumper-anthropic-ai-control-roadmap-2026-06-20]] Jun 20 4-vendor canonical-discipline cluster; (4) [[anthropic-public-record]] paired-context | **Create `tools/openai-deployment-simulation.md`** OR fold into `companies/openai.md` section. **Multi-lint carry-over** (4-cycle pattern-watch finally actionable). Closes ~4 dead-link refs |
| `[[allenai]]` / `[[ai2]]` | **3 refs across 3 distinct cycles** (Jun 12 + Jun 19 + Jun 23) | (1) [[dailybrief-roundup-2026-06-12]]; (2) [[jun-19-open-source-research-origin-cluster-2026-06-19]] Nathan Lambert (AI2) open-source-AI defense; (3) [[dailybrief-roundup-2026-06-23]] Finbarr Timbers (AI2) canonical-advice canonical-anecdote | **Create `companies/allenai.md`** (Allen Institute for AI canonical think-tank-tier; Nathan Lambert + Finbarr Timbers canonical-voices). **Multi-lint carry-over pattern-watch** now actionable. Closes ~3 dead-link refs |

### Stale `last_updated` >60 days on tools/models — RECOMMENDED REFRESH (5 unique)

| File | Days stale | Recommendation |
|---|---|---|
| `tools/crewai.md` | 63 | Refresh `last_updated` if content still accurate (or update with latest CrewAI canonical-positioning vs Loop-Engineering cluster) |
| `tools/llama-index.md` | 63 | Refresh `last_updated` if content still accurate |
| `tools/mem0.md` | 63 | Refresh `last_updated` if content still accurate (or update with canonical-memory canonical-context cluster) |
| `tools/obsidian-dataview.md` | 63 | Refresh `last_updated` if content still accurate |
| `tools/obsidian.md` | 63 | Refresh `last_updated` if content still accurate |

All 5 stale at exactly 63 days = borderline. No required-action; defer per conservative policy unless owner requests refresh.

### Single-source entity-page defers — new from 2026-06-21 + Jun 22 + Jun 23 ingest sequence (~25 unique / ~25 occurrences) — no action

Conservative entity-creation policy applies: john-jumper / polsia / pulsia / ben-cera / claude-tag / alex-albert / andrew-curran / gpt-5-5-cyber / trail-of-bits / zico-kolter / gray-swan / matt-fredrikson / appia-foundation / vibe-thinker / stanford-hai / jack-morris / engram / patrick-collison / josh-elman / meta-arena / 5 canonical-repos / and ~10 carry-over single-source defers.

### Carry-over single-source entity-page defers from prior lints (~50 unique) — no action

Unchanged carry-overs.

## Unprocessed `_raw/` Drops

**0 net-new unprocessed drops**.

## Pre-Lint Discipline Verification

1. `git fetch origin` → ✅
2. `git pull --ff-only` → ✅ at PR-130-merged tip
3. `gh pr list --state open` → empty
4. **Lint branch**: `lint/2026-06-23`

## Recommended Fixes

### Required (7 entity-page creations past 2-surface threshold)

1. **Create `people/0xcodez.md`** with `[[lev-deviatkin]]` canonical-identity-attribution — 3-substantive-surface canonical-voice-tier
2. **Create `people/anatoli-kopadze.md`** — 2-substantive-surface practitioner-content-register
3. **Create `people/francois-fleuret.md`** — 2-substantive-surface Meta FAIR canonical-voice
4. **Create `people/thibault-sottiaux.md`** — 3-ref 2-substantive-surface OpenAI Codex eng-lead
5. **Create `companies/reflection-ai.md`** — STRUCTURALLY MAJOR canonical-SpaceX-anchor-customer
6. **Create `tools/colossus-2.md`** — canonical-SpaceX-substrate-anchor + canonical-multi-tenant canonical-positioning
7. **Create `companies/allenai.md`** — multi-lint 3-cycle carry-over pattern-watch (Nathan Lambert + Finbarr Timbers canonical-voices)

### Optional

- Create `tools/openai-deployment-simulation.md` OR fold into `companies/openai.md` section (4-lint carry-over)
- Refresh 5 stale tool pages (crewai + llama-index + mem0 + obsidian-dataview + obsidian) — defer per conservative policy

## Overall Posture

**MAJOR cleanup needed this lint**: 7 entity-page candidates past 2-surface threshold (5 new from Jun 21-23 sequence + 2 multi-lint carry-overs) — largest single-lint actionable-entity-page-creation queue since [[meta/lint-report-2026-06-14|Jun 14 lint]]'s 4-entity-page creation. **Slug-discipline holding**: 0 wrong-slug regressions across the 6-ingest sequence (Jun 19-pt2 + Jun 20 + Jun 20-pt2 + Jun 21 + Jun 21-pt2 + Jun 21-pt3 + Jun 22 + Jun 23).

**Major narrative tracking now established**:
- **STRUCTURALLY MAJOR Anthropic Claude Tag** (Jun 23) — canonical-2-vendor 6-day Slack-native firm-tier canonical-AI-PR-automation cluster + canonical-eat-your-own-dog-food canonical-validation at frontier-vendor-tier
- **STRUCTURALLY MAJOR SpaceX-Reflection AI** (Jun 22) — canonical-4-tier canonical-SpaceX-AI-vertical-integration canonical-cluster with NEW canonical-anchor-customer-tier
- **STRUCTURALLY MAJOR Nobel-laureate Jumper canonical-cross-vendor-migration event** (Jun 20)
- **3-day 2-event Google-AI-talent-attrition canonical-cluster** (Shazeer + Jumper) — canonical-strongest-signal-yet of Google-AI-talent-retention canonical-issue
- **4-vendor 3-week vendor-side AI-control + AI-safety-and-transparency canonical-discipline cluster** extended to **5-tier** with NEW canonical-AI-security-firm tier (Gray Swan)
- **First wiki-captured canonical-2-tier Artifacts canonical-articulation** (vanilla Claude + Claude Code Artifacts Jun 18)
- **First wiki-captured canonical-AI-PR-automation 2-vendor canonical-validation** (Block Builderbot 15% production code + Anthropic Claude Tag 65% internal PRs)
- **4-tier canonical-AI-vendor-tier cluster** (AI-coding-product + AI-agent + AI-employee + AI-builds-companies-meta-AI)

**Tracking for next lint**:
- Pattern-watch escalations per above
- Continued slug-discipline holding
- 5 stale tool pages refresh-as-needed
