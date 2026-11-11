---
name: Lint report 2026-11-10
type: lint-report
last_updated: 2026-11-10
---

# Lint report — 2026-11-10

**Corpus**: 1,075 markdown files outside `_raw`, `Daily Briefs` and `meta`. Entity pages: 43 tools, 18 models, 52 concepts, 114 people, 66 companies, 6 topics, 2 tutorials. Also 765 sources.
**Delta**: one week since the 2026-11-03 lint, covering the ingests #343–#352, all merged. This pass ran on `main` at `1e0438f`.

## Summary

**Structure is clean. One real defect: Anthropic's model table stops at Sonnet 5.5 and leaves out Fable 5.2 and Mythos 5.2, shipped 2026-11-09.** The 11-10 ingest added them to the model pages and to Traction Signals but not to the table. That is rule 2b's pattern a fourth time, and this time the ingest that missed it was the one that had just read the launch page.

All five fixes proposed on 11-03 are done: September rolled to the archive, the table gained Sonnet 5.5 and Fable 5.1, `rag` and `mem0` were marked dormant, and every roundup now has an inbound link.

| Check | Result |
|---|---|
| 1. Orphan entity pages | **0** |
| Linked from one page besides `index` | **14** (3 on 11-03); see below |
| Entity pages missing from index | **0** |
| Dangling links on entity pages | **0** (code spans stripped; `\|` in tables handled) |
| Path-form wikilinks on entity pages | **0** |
| Source pages linked from nowhere | **0** (7 on 11-03) |
| 2. Stale >60d: behind | **0** |
| Stale >60d: dormant but not yet marked | **1**: `graph-engineering` |
| Marked dormant but resurfaced | **5 hits, 0 real** |
| 2a. Tracked open-question items | **48** across 20 pages (62 on 11-03) |
| 2b. Superseded models without a successor pointer | **0** |
| Lab product lists out of date | **1**: `anthropic` (Fable 5.2, Mythos 5.2; no Haiku row at all) |
| 3. Sources listing no entity page under Pages Updated | **47 counted, 0 actionable** |
| 3a. URL-medium sources with neither `url:` nor `local_source:` | **0** |
| 4. Tools with empty Traction Signals | **0** |
| 5. Contradictions | **0**. One status value off-convention (`ona`) |
| 6. Unprocessed `_raw` drops | **0** of 530 |
| 7. `canonical-` filler (entity + index + log) | **1,157 on 59 pages** (1,404 on 62) |
| `log.md` | **184 KB, two months, in order** |

---

## 1. Link integrity

0 orphans, 0 dangling links, 0 path-form links, and every source page has at least one inbound link.

**Single-link pages rose from 3 to 14.** Three are new this week and are linked only from the source that created them: `mercor`, `fal` and `data-constrained-scaling`. The other eleven (`mojo`, `anton-korinek`, `charlie-hills`, `ruben-hassid`, `yacine`, `anton-leicht`, `0x-rody`, `aravind-srinivas`, `jelani-nelson`, `orewadeveloper`, `a16z`) are older pages. The 11-03 count found only three of them, so it probably used a stricter rule for what counts as a link; the difference wasn't traced. None needs work. New pages pick up links as their subjects come up again.

*Method note:* a first run reported 20 dangling links, all of the form `[[slug\|alias]]` inside tables, where the backslash escapes the pipe. Obsidian resolves those. The checker now strips the trailing backslash.

## 2. Staleness

**One to mark dormant: `concepts/graph-engineering`** (63 days). Four pages updated this week link to it (`jev`, `greg-isenberg`, `company-brain`, `factory-ai`), but all four links predate 11-03; no page gained a new link to it this week and no source in 45 days mentions it. Same reading as `rag` on 11-03.

**Concepts already dormant with recent citers.** `vibe-physics` (3), `jailbreak-severity-framework` (2), `rag` (2), `interaction-models` (1), `simulation-scaling` (1) and `topics/ai-50-2026-snapshot` (1) are cited by pages updated this week. Only `simulation-scaling` gained a new link since 11-03, from `data-constrained-scaling`, as a related concept. That isn't new information about it. All stay dormant.

**Resurfacing hits, none real:** `ollama` (Kimi K3.1 Pro "hosted on Ollama Cloud", a hosting mention), plus `river`, `goose` and `muse-glimmer`, which are the same hits as 11-03.

## 2a. Open-question backlog: 48 items, 20 pages

Down 14 from 62. Most of the drop is the 11-10 ingest closing two items on `claude-fable-5` and one on `claude-mythos`. Some is method: this count treats an item as closed when a `Resolved` note sits under the bullet, which the 11-03 count did not. Heaviest pages: `herdr`, `instinct`, `claude-sonnet-5`, `ai-labor-market-impacts` and `etched` (4 each). No triage needed.

## 2b. Successor pointers and lab product lists

**Model pages are clean.** `claude-fable-5` has a Fable 5.2 section, `claude-mythos` a Mythos 5.2 section, and `claude-opus-5-5` points to Fable 5.2.

**`companies/anthropic` is behind again.** The Products table ("as of 2026-11-03") tops out at Sonnet 5.5. Missing:
- **Fable 5.2** and **Mythos 5.2** (2026-11-09), which Anthropic now says are one model behind two access gates.
- **No Haiku row at all.** Claude Haiku 5.5 exists: it appears in METR's 11-05 assessment and in Willison's 10-28 game post. The wiki has no Haiku 5.x model page and no launch date for it. The table can't add a row without a date. The fix is a primary fetch, not a guess.

The `Opus 5.5 — current flagship` label is still defensible: Anthropic calls Opus 5.5 its *"strongest daily driver"* and positions Fable above it for the hardest work. The row could say that.

Other labs are current against this week's sources: Gemini 4 Carbon on `google`/`google-deepmind`, Kimi K3.1 Pro on `moonshot-ai`.

## 3. Sources without an entity page in Pages Updated: 0 actionable

47 counted: 24 roundups (exempt) and 22 June-era pages already reviewed on 11-03. One new page is in the list: `notion-fireworks-ai-incident-2026-11`. It explains on the page why it updated nothing (no Notion or Fireworks page for a single incident), which the rule exempts.

## 5. Contradictions: none

**`tools/ona` uses `status: acquisition-target`.** The Status Fields convention says acquisitions use `acquisition-announced-close-unconfirmed`, with a note on the page. Ona has neither the conventional value nor a note. The deal was announced 2026-06-16, and whether it has closed isn't on the page. A small fix: change the value and add the note. A primary check on closing would be better.

## 6. `_raw`: 0 unprocessed

530 files. Matching by filename, URL, status ID and title leaves 163 unmatched. The newest is from 2026-10-15, and all of the newest three were already traced to the 10-14 and 10-15 roundups on 11-03. Every clip since then is matched.

## 7. `canonical-` filler: 1,157 on 59 pages

Down 247 after the 11-03 batch (`eric-topol`, `0xmovez` and `gray-swan` are now at 0). Top by instances × inbound links: `mem0` (21 × 18), `latent-space` (72 × 5), `charity-majors` (30 × 12), `colossus-2` (43 × 8), `langchain` (34 × 10), `general-intuition` (110 × 3). `wiki-captured` appears 466 times.

## Log

184 KB, October and November only, sorted. Under the size trigger. No action.

## Proposed fixes

1. Add Fable 5.2 and Mythos 5.2 to the `companies/anthropic` model table, update its "as of" date, and qualify the Opus 5.5 row as Anthropic's recommended default.
2. Mark `concepts/graph-engineering` dormant.
3. `tools/ona`: change the status to `acquisition-announced-close-unconfirmed` and add the note the convention asks for.
4. Next `canonical-` batch: `mem0`, `latent-space`, `charity-majors`.
5. Optional: fetch a primary for Claude Haiku 5.5 so the table can carry a Haiku row.
