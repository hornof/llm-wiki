---
name: Lint report 2026-11-20
type: lint-report
last_updated: 2026-11-20
---

# Lint report — 2026-11-20

**Corpus**: 1,115 markdown files outside `_raw`, `Daily Briefs` and `meta` on `main` (1,127 with open PR #376). Entity pages: 43 tools, 19 models, 52 concepts, 114 people, 67 companies, 6 topics, 2 tutorials. Also 805 sources on `main`, 817 with #376.
**Delta**: eight days since the 2026-11-12 lint, covering #358–#375, all merged. This pass ran on `main` at `9bd4fc3` and again on #376's head (`98b877d`); the two differ only where noted.

## Summary

**Structure is clean. The defects are small and come from this week's ingests:**
- `tools/langchain` was refreshed on 11-14 (Series C) without clearing `dormant_since`.
- Four pages crossed 60 days with nothing new and should be marked dormant.
- One roundup on `main` and two source pages in #376 have no inbound link.
- **#376 adds Gemini 4 Neon to `models/gemini` but not to `companies/google`.** That's rule 2b's lab-product-list pattern again.

The 11-12 fixes all hold: `obsidian` and `claude-desktop` no longer carry `dormant_since`, the 11-11 roundup is linked, Gemini Decision 1 is on `companies/google`, the Haiku row is in the Anthropic table (via #369), and the `colossus-2`/`langchain`/`perplexity` filler batch landed in #363.

| Check | Result |
|---|---|
| 1. Orphan entity pages | **0** |
| Entity pages missing from index | **0** |
| Dangling links on entity pages + index | **0** (code spans stripped; `.canvas` link excluded) |
| Path-form wikilinks on entity pages | **0** |
| Source pages linked from nowhere | **1** on `main` (`dailybrief-roundup-2026-11-15`); **+2** in #376 (`dailybrief-roundup-2026-11-19`, `livesfo-3d-airport-2026-11-15`) |
| 2. Stale >60d: behind | **0** |
| Stale >60d: dormant but not yet marked | **4**: `glm-5-2`, `control-flow-agents`, `saas-disruption-thesis`, `agentic-ai` |
| Marked dormant but refreshed since | **1 real**: `langchain` |
| Marked dormant, resurfacing hits | **5 hits, 1 real** (`langchain`, above) |
| 2a. Tracked open-question items | **59 on 24 pages, unchanged since 11-12** (see the method note) |
| 2b. Superseded models without a successor pointer | **0** |
| Lab product lists out of date | **0** on `main`; **1** in #376 (`google`: Neon) |
| 3. Sources listing no entity page under Pages Updated | **76 counted, 0 actionable** |
| 3a. URL-medium sources with neither `url:` nor `local_source:` | **0** |
| 4. Tools with empty Traction Signals | **0** |
| 5. Contradictions / off-convention status values | **0** (`ona` uses the documented `acquisition-announced-close-unconfirmed`) |
| 6. Unprocessed `_raw` drops | **0** new of 563; newest unmatched clip is still 2026-10-15 |
| 7. `canonical-` filler (entity + index + log) | **745 on 56 pages** (1,039 on 59 on 11-12) |
| `log.md` | **188 KB, October and November, in order** |

---

## 1. Link integrity

**`dailybrief-roundup-2026-11-15` has no inbound link.** It folds five items into source pages, but none of them links back to it, and the 11-16 roundup doesn't mention it. The natural place is `depue-checkpoint-forensics-blackwell-2026-11-12`, the primary the roundup brought in.

**In #376:**
- `dailybrief-roundup-2026-11-19` has no inbound link. The same fix works: link it from `anthropic-ipo-priced-nasdaq-debut-2026-11-19`, the brief's lead item.
- `livesfo-3d-airport-2026-11-15` is linked from nowhere. Its page says it was "clipped as a build idea", so it belongs in `owner/project-ideas` item 2, beside the other build posts.

## 2. Staleness

**One page refreshed without clearing `dormant_since`: `tools/langchain`.** The 11-14 ingest added the $300M Series C from AINews. That's new information, so the rule says to clear it.

**Three more pages have `last_updated` after `dormant_since`, but they aren't refreshes:** `claude-financial-services` (filler rewrite, #305), `claude-opus-4-7` and `claude-opus-4-8` (successor pointers, #309). Those were maintenance edits, with no new information about the entity, so the dormancy stands.

**Four to mark dormant:**
- `models/glm-5-2` (68 days). No source in 45 days mentions it, and the page already points at GLM 5.3.
- `concepts/control-flow-agents` (61 days). One recent citer, no new links since 11-12.
- `topics/saas-disruption-thesis` (65 days). Four recent citers, all with links older than 11-12.
- `topics/agentic-ai` (61 days). Three recent citers, none new. The source hits are the Agentic AI Foundation's name and one 11-06 source that cites the page for an unsettled Harvey claim without adding anything.

The concept test is the same one used on `graph-engineering` on 11-10: a concept is live when pages gain new links to it, not when old links sit on pages edited for other reasons.

**Other resurfacing hits aren't real.** `ollama` appears in Willison's "LM Studio or Ollama or llama.cpp" list, a passing mention. `goose` and `muse-glimmer` are the same hits as 11-12.

## 2a. Open-question backlog: 59 items, 24 pages

**No change since 11-12.** Running this pass's counter on the 11-12 tree (`286b1c8`) gives the same 59 items, item for item. The 11-12 report said 51 on 22; the difference is the counter, not the wiki. This counter counts every bullet in a `## Verification-pending` or `## Open Questions` section with no "Resolved" in it, sub-bullets included. Heaviest pages: `jelani-nelson` (5), then `herdr`, `instinct`, `claude-sonnet-5`, `ai-labor-market-impacts` and `etched` (4 each). No triage needed.

## 2b. Successor pointers and lab product lists

**`main` is current.** The Anthropic table (dated 2026-11-12) now has a Haiku 5.5 row. `companies/google` lists Argon, Carbon, Hydrogen and Gemini Decision 1.

**#376 adds Gemini 4 Neon (2026-11-18) to `models/gemini` but not to `companies/google`.** The company page's "Current frontier models" line stops at Hydrogen. Fix it on the #376 branch before merge.

Only Anthropic and Google were checked against their model pages this pass, because they're the two labs with new models since 11-12.

## 3. Sources without an entity page in Pages Updated: 0 actionable

76 counted, all roundups or pages that say why they updated nothing. New since 11-12: the 11-12 to 11-19 roundups and `livesfo-3d-airport`, which explains itself.

## 6. `_raw`: 0 unprocessed

563 files. The newest unmatched clip is from 2026-10-15, as on 11-10 and 11-12. The ~200 older uncovered clips are the long-standing backlog.

## 7. `canonical-` filler: 745 on 56 pages

Down 294, from the rewrites in #363 (`perplexity`, `langchain`, `colossus-2`) and #370 (`general-intuition`, `reflection-ai`, `anthropic-public-record`). `index` has 0. `log` has 12, all in lint entries that report the count.

Top by instances × inbound links:

| Page | Instances | Inbound | Impact |
|---|---|---|---|
| `concepts/company-brain` | 4 | 74 | 296 |
| `companies/anthropic` | 1 | 284 | 284 |
| `tools/obsidian` | 31 | 9 | 279 |
| `tools/microgpt` | 39 | 7 | 273 |
| `people/hanako` | 28 | 9 | 252 |
| `people/anatoli-kopadze` | 60 | 4 | 240 |
| `tools/openclaw` | 15 | 16 | 240 |
| `companies/cloudflare` | 23 | 10 | 230 |

**The top two are five sentences between them**, on two of the most-read pages. They're the cheapest high-impact fix this rule has produced.

## Log

188 KB, October and November only, sorted. No action. November rolls to the archive once December starts and October is two months back.

## Proposed fixes

On a lint branch from `main`:
1. Clear `dormant_since` on `tools/langchain`.
2. Mark `glm-5-2`, `control-flow-agents`, `saas-disruption-thesis` and `agentic-ai` dormant.
3. Link `dailybrief-roundup-2026-11-15` from `depue-checkpoint-forensics-blackwell-2026-11-12`.
4. Rewrite the five filler sentences on `company-brain` and `anthropic`.

On #376 before merge:
5. Add Gemini 4 Neon to `companies/google`'s frontier-model line.
6. Link `dailybrief-roundup-2026-11-19` from the Anthropic IPO source, and `livesfo-3d-airport-2026-11-15` from `owner/project-ideas`.

Next filler batch after that: `obsidian`, `microgpt`, `openclaw`.

## Fixes applied (2026-11-20, owner chose all six)

Fixes 1–4 are on this branch; 5 and 6 are on #376.

- `langchain`'s `dormant_since` cleared; the four pages marked `dormant_since: 2026-11-20`.
- `dailybrief-roundup-2026-11-15` linked from the DePue source.
- `company-brain`'s Single Brain section and `anthropic`'s 2026-06-03 bullet rewritten in plain prose, with quotes and numbers checked against the `_raw` clips. Filler: 745 → 740, not counting the count this lint wrote into `log.md`.
- **Found while rewriting:** `company-brain` credited *"The moat is the system"* to Sentra. The quote is Greg Isenberg's ([[gregisenberg-theo-tabah-ai-native-masterclass-2026-06-08]]). Corrected on the page with a note.
