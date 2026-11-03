---
name: Lint report 2026-11-03
type: lint-report
last_updated: 2026-11-03
---

# Lint report — 2026-11-03

**Corpus**: 1,112 markdown files. Entity pages: 43 tools, 18 models, 51 concepts, 113 people, 64 companies, 6 topics, 2 tutorials. Also 727 sources and 79 meta.
**Delta**: six days since the 2026-10-28 lint, covering #333–#342, all merged. This pass ran on `main` at `cb361e2`.

## Summary

**Structure is clean. Two things need doing: `log.md` is overdue for its September rollover, and Anthropic's model table omits two releases.**

- **`log.md` holds three months** (September, October, November) at 390 KB. The retention rule says two. September should move to `meta/log-archive/2026-09.md`.
- **`companies/anthropic` model table** ("as of 2026-10-16") leaves out **Sonnet 5.5** (2026-09-28) and **Fable 5.1** (2026-09-01). Both came out before the table was written. Sonnet 5.5 appears further down the page; Fable 5.1 isn't on the company page at all.
- **Two stale pages aren't marked dormant**: `concepts/rag` (61 days) and `tools/mem0` (64 days). Neither appears in a source from the last 45 days, and neither gained a new link since 10-20.
- The 34 path-form links from 10-28 are gone (#335). The `canonical-` count fell from 1,635 to 1,404.

| Check | Result |
|---|---|
| 1. Orphan entity pages | **0** |
| Linked from one page besides `index` | **3**: `a16z`, `charlie-hills`, `orewadeveloper` |
| Entity pages missing from index | **0** |
| Dangling links on entity pages | **0** (code spans stripped) |
| Path-form wikilinks on entity pages | **0** (34 on 10-28) |
| Source pages linked from nowhere | **7**: daily roundups for 10-25, 10-26, 10-27, 10-28, 11-02 and 11-03, plus `raw-batch-roundup-2026-10-31` |
| 2. Stale >60d: behind | **0** |
| Stale >60d: dormant but not yet marked | **2**: `rag`, `mem0` |
| Marked dormant but resurfaced | **4 hits, 0 real** (below) |
| 2a. Tracked open-question items | **62** across 23 pages (61 on 10-28) |
| 2b. Superseded models without a successor pointer | **0** |
| Lab product lists out of date | **1**: `anthropic` (Sonnet 5.5, Fable 5.1) |
| 3. Sources listing no entity page under Pages Updated | **51 counted, 0 actionable** (below) |
| 3a. URL-medium sources with neither `url:` nor `local_source:` | **0** |
| 4. Tools with empty Traction Signals | **0** |
| 5. Contradictions | **0**. `world-labs` heading fixed |
| 6. Unprocessed `_raw` drops | **0** of 522. No deletable duplicates |
| 7. `canonical-` filler (entity + index + log) | **1,404 on 62 pages** (1,635 on 65) |
| `log.md` | **390 KB, three months, one entry out of order** |

---

## 1. Link integrity

0 orphans, 0 dangling links, 0 entity pages missing from the index, 0 path-form links.

**Single-link pages.** `a16z`, `charlie-hills` and `orewadeveloper` are each linked from one source page and from `index`. The 10-28 pass counted `index` as a link, which is why it reported 0. None of the three needs work. They're small pages that haven't come up again.

**Sources linked from nowhere.** Six recent daily roundups and `raw-batch-roundup-2026-10-31` have no inbound links, not even from `index`. This is timing, as on 10-28. Linking each roundup from the next day's roundup would fix it and keep the chain readable.

## 2. Staleness

44 tool, model, concept and topic pages are over 60 days old. 42 already carry `dormant_since`.

**Not yet marked:**
- **`concepts/rag`** (61 days). Its recent citers (`end-of-finetuning`, `llm-wiki-pattern`, `mcp`) link it from old Related sections, and no source since 2026-09-19 mentions RAG. Dormant.
- **`tools/mem0`** (64 days). No mention in any recent source. Dormant.

**Resurfacing hits, none real:**
- `river`: the 10-01 masterclass mention again.
- `goose`: two new links since 10-20, both naming Goose as a project already in the Agentic AI Foundation. Nothing about Goose itself.
- `muse-glimmer`: the same 10-21 Latent Space line as last time.
- `dac`: the 09-20 roundup, which is the source it was marked dormant from.

## 2a. Open-question backlog: 62 items, 23 pages

Up one from 10-28. Same heaviest pages: `claude-fable-5` and `ai-vulnerability-discovery` (5 each), then `herdr`, `instinct`, `claude-sonnet-5`, `ai-labor-market-impacts`, `loop-engineering`, `metr` and `etched` (4 each). No triage is needed at this size.

## 2b. Successor pointers and lab product lists

**Model pages are clean.** The 10-28 findings are fixed: `companies/openai` lists GPT-6.1 Terra and `companies/google` names Gemini 4 Argon and Carbon and links `models/gemini`. `mistral-ai` has Le Chonk, `deepseek` has V4.1-Flash, `moonshot-ai` has Kimi K3.1.

**`companies/anthropic` is behind.** Its Products table ("as of 2026-10-16") goes Opus 5.5, Opus 5, Sonnet 5, Fable 5, Mythos, Opus 4.8, Opus 4.7. Missing:
- **Sonnet 5.5** (2026-09-28). It has its own section on `models/claude-sonnet-5` and a Traction Signals bullet lower on the company page.
- **Fable 5.1** (2026-09-01). It has a section on `models/claude-fable-5` and is cited on `claude-opus-5-5` as the comparison model on Terminal-Bench. The company page never names it.

This is rule 2b's pattern a third time. The table was correct for what its author checked, and two point releases that lived only on model pages were missed.

## 3. Sources without an entity page in Pages Updated: 0 actionable

This pass counted 51, against 29 on 10-28. The difference is the method: this count includes the 30 roundups, which are exempt. The other 21 are the same set as 10-28: June-era pages that list only `[[index]]` but are cited by entity pages, plus the documented exemptions (`cerebras-60b-ipo`, `fastcompany-amazon-workers`, `tanstack-npm-supply-chain`, `linkedin-luke-hornof-2026`). None is newer than 2026-07-01.

## 5. Contradictions: none

`world-labs` now reads "AMD to acquire for $8.2B (announced 2026-09-28)". Two concepts use maturity values outside the schema: `rag` (`mainstream`) and `loop-engineering` (`gaining-mainstream-recognition`). Both are accurate descriptions; the schema just has no value for a concept everyone uses. Not worth changing.

## 6. `_raw`: 0 unprocessed

522 files, down from 542 after the 10-30 dedup. Matching by filename, URL, status ID and title leaves 156 unmatched. The newest X post among them is from 2026-10-07, and the 10-28 lint traced everything older than that to log entries. I spot-checked the three newest Reddit clips (opusplan, shapeshifting software, architecture review); all three are in the 10-14 and 10-15 roundups, with truncated filenames my matcher missed. The duplicate check finds 0 deletable copies and the same 5 pairs kept because their replies differ.

## 7. `canonical-` filler: 1,404 on 62 pages

Down 231 after #335's rewrites. Top by impact (instances × inbound): `eric-topol` (94 × 6), `0xmovez` (89 × 6), `gray-swan` (66 × 8), `general-intuition` (110 × 4), `charity-majors` (30 × 13). `wiki-captured` appears 462 times.

## Log

`log.md` is 390 KB with September (34 entries), October (44) and November (3). On 10-28 this report said September would roll on 11-01. It hasn't yet. Rolling it now brings the file back to two months. The header note still says "entries before 2026-08 live in `meta/log-archive/`" and should say 2026-10 after the move. One entry is out of order: a 10-21 line follows a 10-22 line (lines 123–124).

## Proposed fixes

1. Roll September out of `log.md` into `meta/log-archive/2026-09.md`, check the line multiset is unchanged, fix the header note and the one misordered entry.
2. Add Sonnet 5.5 and Fable 5.1 to the `companies/anthropic` model table, and update its "as of" date.
3. Mark `concepts/rag` and `tools/mem0` dormant.
4. Link each uncited roundup from the next day's roundup.
5. Next `canonical-` batch: `eric-topol`, `0xmovez`, `gray-swan`.
