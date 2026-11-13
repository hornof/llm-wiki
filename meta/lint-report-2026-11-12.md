---
name: Lint report 2026-11-12
type: lint-report
last_updated: 2026-11-12
---

# Lint report — 2026-11-12

**Corpus**: 1,092 markdown files outside `_raw`, `Daily Briefs` and `meta`. Entity pages: 43 tools, 18 models, 52 concepts, 114 people, 66 companies, 6 topics, 2 tutorials. Also 782 sources (765 on 11-10).
**Delta**: two days since the 2026-11-10 lint, covering #354–#357, all merged. This pass ran on `main` at `286b1c8`.

## Summary

**Structure is clean. There are two small defects, both left by ingests this week:**
- Two pages refreshed on 11-09 still carry `dormant_since`.
- The 11-11 roundup has no inbound link.

All three fixes from 11-10 that were applied in #354 still hold: the Anthropic table carries Fable 5.2 and Mythos 5.2, `graph-engineering` is dormant, and `ona` uses the conventional status. The Haiku row is still missing, as expected; it needs a primary source.

| Check | Result |
|---|---|
| 1. Orphan entity pages | **0** |
| Linked from one page besides `index` | **14** (same 14 as 11-10) |
| Entity pages missing from index | **0** |
| Dangling links on entity pages | **0** (same-page `[[#heading]]` anchors and the `.canvas` link in `index` excluded) |
| Path-form wikilinks on entity pages | **0** |
| Source pages linked from nowhere | **1**: `dailybrief-roundup-2026-11-11` |
| 2. Stale >60d: behind | **0** |
| Stale >60d: dormant but not yet marked | **0** |
| Marked dormant but resurfaced | **6 hits, 2 real**: `obsidian`, `claude-desktop` |
| 2a. Tracked open-question items | **51** across 22 pages (48 on 20 on 11-10) |
| 2b. Superseded models without a successor pointer | **0** |
| Lab product lists out of date | **0** required; 1 optional (`google`) |
| 3. Sources listing no entity page under Pages Updated | **46 counted, 0 actionable** |
| 3a. URL-medium sources with neither `url:` nor `local_source:` | **0** |
| 4. Tools with empty Traction Signals | **0** |
| 5. Contradictions / off-convention status values | **0** |
| 6. Unprocessed `_raw` drops | **0** new; newest unmatched clip is still 2026-10-15 |
| 7. `canonical-` filler (entity + index + log) | **1,039 on 59 pages** (1,157 on 11-10) |
| `log.md` | **183 KB, two months, in order** |

---

## 1. Link integrity

**`dailybrief-roundup-2026-11-11` has no inbound link.** The 11-10 and 11-12 roundups are linked (from `notion-fireworks-ai-incident-2026-11` and `ai-margin-collapse`). The 11-12 roundup already says its items repeat "the 11-10 and 11-11 ingests". Turning those words into links fixes it honestly.

The 14 single-link pages are the same 14 as on 11-10. None needs work.

*Method note:* the checker first reported 34 empty-slug "dangling" links. All are same-page anchors such as `[[#The agent-swarm thread…|…]]`, which Obsidian resolves. `[[agi-debate.canvas]]` in `index` points to `canvases/agi-debate.canvas`, which exists.

## 2. Staleness

**Nothing is behind and nothing new needs marking dormant.**

**Two pages were refreshed without clearing `dormant_since`.** The rule says to clear it when the page is refreshed:
- `tools/obsidian`: refreshed 2026-11-09 by #350 (the Claude + Obsidian second-brain guide). Two recent sources mention it.
- `tools/claude-desktop`: refreshed 2026-11-09 by #350 (Desktop scheduled tasks). Cited by `anthropic`, `claude-code`, `claude-cowork` and `mcp`, all updated this week.

**The other four resurfacing hits aren't real.** `ollama`, `river` and `muse-glimmer` are the same passing mentions as on 11-10. `goose` appears in the AAIF source's list of foundation projects, which is a listing, not news about Goose.

## 2a. Open-question backlog: 51 items, 22 pages

Up 3 from 48. This count treats an item as closed when a "Resolved" note sits under it, and keeps "Partly answered" items open. The 11-12 ingests added partly-answered notes to `jev` and `skill-md`, which stay in the count. The rest of the difference wasn't traced item by item. Heaviest pages: `herdr`, `instinct`, `claude-sonnet-5`, `ai-labor-market-impacts` and `etched` (4 each), then `claude-fable-5` (3). No triage needed.

## 2b. Successor pointers and lab product lists

**Model pages and the Anthropic table are current.** The table is dated 2026-11-10 and has Fable 5.2 and Mythos 5.2, and the Opus 5.5 row now carries Anthropic's "strongest daily driver" framing. **There's still no Haiku row**, for the reason given on 11-10.

**Optional: `companies/google`.** Its "Current frontier models (2026-10-28)" line lists Gemini 4 Argon and Carbon. Gemini Decision 1 (2026-11-11) is on `gemini` but not on the company page. It's a decision model, not a frontier LLM, so the line isn't wrong. A separate sentence would keep the product list complete.

## 3. Sources without an entity page in Pages Updated: 0 actionable

46 counted, all roundups or pages reviewed on earlier lints. None is from this week.

## 6. `_raw`: 0 unprocessed

535 files. The newest unmatched clip is from 2026-10-15, the same as on 11-10. The five `.txt` files added on 11-12 are the fetched texts behind the skills ingest, named by their source slugs.

**Not a `_raw` item, but carried twice now:** "Anthropic launches Claude Meetings" was in TechCrunch's sidebar on 11-11 and hasn't appeared in a brief or been fetched.

## 7. `canonical-` filler: 1,039 on 59 pages

Down 118. `mem0`, `latent-space` and `charity-majors` are no longer in the top ranks. Top by instances × inbound links: `colossus-2` (43 × 8), `langchain` (34 × 10), `general-intuition` (110 × 3), `anthropic-public-record` (22 × 15), `reflection-ai` (19 × 15), `perplexity` (70 × 4). `index` has 0. `log` has 17, all in lint entries that report the count.

**`perplexity` was edited on 11-12 without touching its filler.** The skills ingest added a plain bullet and left the old ones as they were. That follows the rule (rewrite against sources, as a scoped job), but the page now mixes the two styles.

## Log

183 KB, October and November only, sorted. No action.

## Proposed fixes

1. Clear `dormant_since` on `tools/obsidian` and `tools/claude-desktop`.
2. Link `dailybrief-roundup-2026-11-11` from the 11-12 roundup's "repeat the 11-10 and 11-11 ingests" sentence.
3. Optional: add Gemini Decision 1 to `companies/google`'s product line.
4. Next `canonical-` batch: `colossus-2`, `langchain`, `perplexity` (the last since it was just touched).
5. Optional: fetch the Claude Meetings announcement.
