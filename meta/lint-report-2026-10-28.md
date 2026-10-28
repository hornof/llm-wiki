---
name: Lint report 2026-10-28
type: lint-report
last_updated: 2026-10-28
---

# Lint report — 2026-10-28

**Corpus**: 1,066 markdown files. Entity pages: 43 tools, 17 models, 51 concepts, 112 people, 64 companies, 6 topics, 2 tutorials. Also 684 sources and 78 meta.
**Delta**: seven days since the 2026-10-21 lint, covering #321–#332 merged and #333 open. This pass ran on `main`, so the new `models/gemini` page from #333 isn't counted.

## Summary

**Structure is clean again. What's left is two lab pages that don't list current models, one concept going stale, and a convention slip.**

- **`companies/openai` doesn't list GPT-6.1 Terra**, and **`companies/google` doesn't mention the Gemini 4 line at all.** Rule 2b's company-page check.
- **`concepts/mcp` is behind**: 63 days old with 12 recently updated citers. #333 adds one line; the page needs more than that.
- **34 path-form wikilinks** (`[[concepts/x]]`) on 25 entity pages break the slug-only convention. They resolve in Obsidian, so earlier lints never counted them.
- The open-question backlog is **61**, up from 55 after the 10-21 cut.

| Check | Result |
|---|---|
| 1. Orphan entity pages | **0** |
| Weakly integrated (1 inbound) | **0** |
| Entity pages missing from index | **0** |
| Dangling links on entity pages | **0** (code spans stripped; path-form and `\|` table links normalized) |
| Path-form wikilinks on entity pages (convention) | **34 on 25 pages** (new check) |
| Source pages with 0 inbound | **4**: the four newest roundups |
| 2. Stale >60d: behind | **2**: `mcp` (12 citers), `simulation-scaling` (2 citers, both old links) |
| Stale >60d: dormant but not yet marked | **0** |
| Marked dormant but resurfaced | **5 hits, 0 real** (below) |
| 2a. Tracked open-question items | **61** across 22 pages (55 after #324) |
| 2b. Superseded models without a successor pointer | **0** |
| Lab product lists out of date | **2**: `openai` (GPT-6.1 Terra), `google` (Gemini 4) |
| 3. Sources listing no entity page under Pages Updated | **29, of which 0 need action** |
| 3a. URL-medium sources with neither `url:` nor `local_source:` | **0** (3 on 10-21) |
| 4. Tools with empty Traction Signals | **0** (2 on 10-21) |
| 5. Contradictions | **1 minor** (`world-labs` heading vs status) |
| 6. Unprocessed `_raw` drops | **0** of 542: all 33 hard cases traced to log entries |
| 7. `canonical-` filler (entity + index + log) | **1,635 on 65 pages**, unchanged |
| `log.md` size | **376 KB** (retention wins; see below) |

---

## 1. Link integrity

0 orphans, 0 weak pages, 0 dangling links on entity pages, 0 entity pages missing from the index. `[[agi-debate.canvas]]` in `index.md` resolves to `canvases/agi-debate.canvas`.

**Path-form links (new check).** The schema says to use slugs, with `owner/` as the only exception. 25 entity pages use `[[concepts/…]]`, `[[people/…]]` and similar forms 34 times. The worst are `nando-de-freitas`, `junyang-lin` and `shane-legg` (3 each), then `andy-jassy` and `dan-jeffries` (2 each). They all resolve, so nothing is broken. It's a mechanical fix: strip the directory prefix.

**Zero-inbound sources:** `dailybrief-roundup-2026-10-25`, `-10-26`, `-10-27` and `raw-batch-roundup-2026-10-28`. This is timing. The raw-batch roundup can be linked from the 10-27 daily roundup.

**Source pages (not checked by rule):** 235 distinct link targets from source pages don't exist. Most are deliberate create-candidates (`hermes-agent`, `noam-shazeer`, `vercel`, `gemma`), and none sits on an entity page. They aren't counted as defects.

## 2. Staleness

### Behind

- **`concepts/mcp`** (63d). 12 pages updated in the last 14 days cite it, including `anthropic`, `agentic-engineering`, `ai-native-organizations` and `code-mode`. Its last substantive entry is from May, and its Current State predates the Agent Skills move to AAIF (10-22) and Google's Connected Apps Platform (10-28). #333 adds the Google line. A proper refresh would cover AAIF governance, the 10-22 Skills donation, and how MCP now relates to Skills.
- **`concepts/simulation-scaling`** (66d). Both recent citers, `world-models` and `jack-clark`, link it from old entries. By the 10-21 precedent that's dormancy, so add `dormant_since`.

### Marked dormant, resurfacing hits: none real

- `river`: the 10-01 masterclass mention, the same passing example as on 10-21.
- `goose`: named in the Agent Skills → AAIF source as a project already in the foundation. Nothing new about Goose.
- `muse-glimmer`: one line in a 10-21 Latent Space source.
- `vibe-physics`, `jailbreak-severity-framework`: marked dormant on 10-21 (#323) because their citers were old Related links. That still holds.

All five stay dormant.

## 2a. Open-question backlog: 61 items, 22 pages

#324 cut it to 55 on 10-21, and it's up 6 since. The heaviest pages are `claude-fable-5` and `ai-vulnerability-discovery` (5 each), then `herdr`, `instinct`, `claude-sonnet-5`, `ai-labor-market-impacts`, `loop-engineering`, `metr` and `etched` (4 each). No triage is needed at this size. Ingest step 5a is now closing items each week; the S-1 closed seven on 10-26.

## 2b. Successor pointers and lab product lists

**Model pages are clean.** `kimi-k3` points to K3.1 Pro, `gpt-6-astra` carries the GPT-6.1 Sol and Terra callouts, `gpt-5-6` points to Terra and the GPT-6 line, `glm-5-2` points to 5.3, `claude-sonnet-5` covers 5.5, and the Opus pages point to 5.5.

**Two company pages are behind:**
- **`companies/openai` Key Products** ("as of 2026-10-16") lists Astra, Sol, Luna and 6.1 Sol, but not **GPT-6.1 Terra** (2026-10-26), which has its own source page and callouts on two model pages. This is the gap rule 2b describes: model pages get updated, and the company list doesn't.
- **`companies/google`** has no product or model list. It never names Gemini 4 Argon (GA 10-13) or Carbon (10-28). Once #333 merges and `models/gemini` exists, the page needs a line pointing to it.

## 3. Sources without an entity page in Pages Updated: 29, none actionable

- **20** list only `[[index]]` or another source page. All of these are June-era, and all are cited by entity pages anyway, so it's a recording gap.
- **8** record why they updated nothing: four research roundups, `dailybrief-mixed-2026-05-16-to-18`, `cerebras-60b-ipo`, `fastcompany-amazon-workers` (paywall) and `tanstack-npm-supply-chain`. Exempt under rule 3.
- **1** is `linkedin-luke-hornof-2026` → `owner/profile`. Owner pages are exempt.

None is newer than 2026-07-01. The three uncited pages flagged on 10-21 are fixed. *(The 10-21 count of 22 likely excluded the documented ones. This pass lists them so the count can be reproduced.)*

## 5. Contradictions: 1 minor

`companies/world-labs` has the heading **"Acquired by AMD for $8.2B (2026-09-28)"**, while `status: acquisition-announced-close-unconfirmed` and the body says close date and structure aren't captured. The status is right and the heading overstates it. Suggested heading: "AMD to acquire for $8.2B (announced 2026-09-28)". `xai`, flagged on 10-21, is fixed (`acquired (SpaceX, 2025)`).

## 6. `_raw`: 0 unprocessed

542 files. 186 fail exact matching by filename, status ID or URL, and title words narrow that to 33. **All 33 trace to entries in `log.md` or `meta/log-archive/`**, mostly June-era drops processed into roundups that didn't record the handle (`@gradypb`, `@jianw851`, `@nurijanian`, `@kunalstwt`, `@amypretzel` and others). The automatic count overstates the backlog, as on 10-15 and 10-21.

## 7. `canonical-` filler: 1,635 on 65 pages, unchanged

No filler work this week. The top of the impact ranking (instances × inbound) is unchanged: `allenai` (71 × 11), `alibaba` (78 × 10), `khairallah` (84 × 7), `eric-topol` (94 × 6), `0xmovez` (89 × 6). `wiki-captured` appears 474 times (467 on 10-21).

## Log size

376 KB, holding September and October. Under the 10-21 owner decision, retention wins over size. On 2026-11-01 September rolls to `meta/log-archive/2026-09.md` and the file shrinks a lot. October's new one-line entries average well under 1 KB.

## Proposed fixes

1. Add GPT-6.1 Terra to `companies/openai` Key Products.
2. Once #333 merges, add a Gemini line to `companies/google` pointing to `models/gemini`.
3. Refresh `concepts/mcp`: AAIF governance, Skills alongside MCP, Google Connected Apps.
4. Mark `concepts/simulation-scaling` dormant.
5. Convert the 34 path-form wikilinks to slugs.
6. Soften the `world-labs` heading.
7. Link `raw-batch-roundup-2026-10-28` from `dailybrief-roundup-2026-10-27`.
8. Next `canonical-` batch: `allenai`, `alibaba`, `khairallah`.
