---
name: Lint report 2026-10-21
type: lint-report
last_updated: 2026-10-21
---

# Lint report — 2026-10-21

**Corpus**: 1,024 markdown files. Entity pages: 43 tools, 17 models, 51 concepts, 112 people, 64 companies, 6 topics, 2 tutorials. Also 643 sources, 77 meta and 2 owner.
**Delta**: six days and seven ingest/cleanup PRs since the 2026-10-15 lint (#311–#320; #321 still open).

## Summary

**Link structure is clean; what remains is staleness, filler and log size.** Every link and integration check comes back zero. The findings worth acting on:

- **Seven concept pages are being cited by recently updated pages but haven't been updated themselves in months.** Under the 10-15 rule, that makes them behind, not dormant.
- **`claude-agent-sdk` is marked dormant but has resurfaced.**
- **`xai`'s status contradicts how the wiki treats `anysphere`.**
- **`log.md` is 2.5× its size limit**, and the rollover rule can't fix it without breaking the retention rule.

| Check | Result |
|---|---|
| 1. Orphan entity pages | **0** |
| Weakly integrated (1 inbound) | **0** |
| Entity pages missing from index | **0** |
| Dangling links on entity pages | **0** (code spans stripped) |
| Source pages with 0 inbound | **3**: the three newest roundups, which nothing has linked yet |
| 2. Stale >60d: behind | **7 concepts by the citation test; 2 tools/concepts by the source test** |
| Stale >60d: dormant but not yet marked | **13** |
| Marked dormant but resurfaced | **1** (`claude-agent-sdk`) |
| 2a. Tracked open-question items | **156** across 28 pages (153 / 27 on 10-15) |
| 2b. Superseded models without a successor pointer | **0** |
| Lab product lists out of date | **0** (Anthropic: Opus 5.5 "current flagship"; OpenAI: GPT-6 line) |
| 3. Sources listing no entity page under Pages Updated | **22**, of which **3 are cited by no entity page** |
| 3a. URL-medium sources with neither `url:` nor `local_source:` | **3** |
| 4. Tools with empty Traction Signals | **2** (`google-agents-cli`, `gstack`; same as 10-15) |
| 5. Contradictions | **1** (`xai` status) |
| 6. Unprocessed `_raw` drops | **≈0**: 125 files fail automatic matching; 10 of 10 spot-checked were processed |
| 7. `canonical-` filler (entity + index + log) | **1,635 instances on 65 pages**; index.md 0 |
| `log.md` size | **379 KB** against a ~150 KB limit |

---

## 1. Link integrity: clean

0 orphans, 0 weak pages, 0 dangling links on entity pages, 0 entity pages missing from `index.md`.

**Three source pages have no inbound links:** `dailybrief-roundup-2026-10-21`, `raw-batch-roundup-2026-10-18` and `raw-batch-roundup-2026-10-20`. Roundups get linked when later pages cite them, and these are the newest, so this is mostly timing. The two raw-batch roundups could be linked from their same-day daily roundups.

## 2. Staleness

### Behind: concepts that are cited but not updated (citation test, rule 2)

Each of these has a `last_updated` older than 60 days and is linked from pages updated in the last 14 days. A concept that current pages rely on is live, so these count as behind:

| Page | Age | Recent citers |
|---|---|---|
| `reverse-information-paradox` | 83d | **6**: ai-margin-collapse, ai-native-organizations, frontier-ai-governance, kimi-k3, loop-engineering, satya-nadella |
| `software-3-0` | 168d | **5**: agentic-engineering, andrej-karpathy, model-rendered-ui, verifiability-and-jagged-intelligence, vibe-coding |
| `vibe-physics` | 168d | 3 |
| `jailbreak-severity-framework` | 107d | 3 |
| `agi` | 175d | 2, plus DeepMind's AGI-impact institute (2026-09-16 roundup), which the page doesn't record |
| `context-engineering` | 84d | 2 |
| `engineering-leadership-ai-era` | 69d | 2 |

**`reverse-information-paradox` is the clear first pick.** Six pages updated this week rely on a page last touched in July.

### Behind: tools (source test)

- **`claude-agent-sdk`** is marked `dormant_since: 2026-09-20` but appears in two sources from the last 45 days: an 11-step agent-teams course built on it (2026-10-07), and Moyai, which uses it as its default harness (2026-10-07). Per rule 2, the dormant flag should come off and the page should be refreshed.
- **`claude-design`** (62d): one commenter (2026-10-17 raw roundup) says the legacy Claude Design tool is retiring. That's unconfirmed but worth one line on the page.

### Dormant but not yet marked: 13

Older than 60 days, no source mentions in 45 days, and no tool or model resurfacing. Each needs a `dormant_since` added:

`autoresearch`, `claude-certified-architect`, `doing-great-work`, `global-workspace`, `interaction-models`, `llmorphism`, `openai-deployment-simulation`, `science-as-training-data-frontier`, `spatial-intelligence`, `ai-50-2026-snapshot` (a dated snapshot, so dormant by design), `goose`, `mojo`, `ona`.

`claude-certified-architect` has two recent citers, but both are passing mentions in product lists. Marking it dormant is a judgment call.

### Dormant and correct

28 tool and model pages already carry `dormant_since`. The only resurfacing hits were `river` (a passing example in a 10-01 masterclass) and `muse-glimmer` (one line in today's AINews, nothing new). Both stay dormant.

## 2a. Open-question backlog: 156 items, 28 pages

Up 3 from 10-15. The heaviest pages are `junyang-lin` (10), `intel` (9), `nando-de-freitas`, `satya-nadella`, `david-sacks` and `google` (8 each), then `claude-fable-5` and `elon-musk` (7 each). Most are bio and handle questions on people pages. Rule 2a says to delete those rather than research them.

**Closed this week:** the White House Accord (#321), the DHS order date (#321), the Alibaba/Qwen vendor question (#319), the Anthropic customer-concentration and comparison-quarter items (#317).

## 2b. Successor pointers: clean

Every superseded model page names its successor:
- `claude-opus-4-7`, `claude-opus-4-8` and `claude-opus-5` all point to Opus 5.5.
- `claude-sonnet-5` points to Sonnet 5.5.
- `gpt-5-6` points to the GPT-6 line.
- `glm-5-2` points to GLM-5.3.
- `claude-fable-5` points to Fable 5.1.

Lab product lists are current.

## 3. Sources without an entity page in Pages Updated: 22

**19 of the 22 are cited by an entity page anyway.** Their Pages Updated sections list other source pages (the June cluster pages), `index` or `owner/profile` instead. That's a recording gap, not lost content. **Three are cited by no entity page at all:**

- `alex-finn-fable-5-operating-systems-audit-2026-07-02`
- `paul-meade-apple-vision-pro-to-openai-hardware-2026-06-27`
- `open-tag-vs-claude-tag-vendor-vs-open-source-cluster-2026-06-26`

Each needs either a fold into an entity page or a line recording why it has none.

*This count differs from 10-15's "0" because this pass applied rule 3 literally (an entity page must be listed). The earlier pass accepted any linked page.*

## 3a. Missing URL: 3

`raw-batch-roundup-2026-09-02` and `raw-batch-roundup-2026-09-03` (roundups with an empty `url:`) need `local_source:`. `aakashgupta-doordash-company-brain-2026-05-10` has `url: ""` and needs either the X status URL or a `local_source:`.

## 4. Tools without Traction Signals: 2

`google-agents-cli` and `gstack`, the same two as on 10-15.

## 5. Contradictions: 1

**`companies/xai` reads `status: active` while its body says "Acquired by SpaceX in 2025".** `companies/anysphere`, acquired by the same buyer, reads `status: acquired (SpaceX, closed 2026-08-14)`. Two pages handle the same situation two different ways. Suggested fix: `status: acquired (SpaceX, 2025)`, with the note the Status Fields section asks for.

## 6. `_raw` drops: ≈0 unprocessed

534 files. 125 can't be matched to a source page by filename, status ID, URL or title words. **A spot-check of 10 (HamelHusain, dhh, JeffDean, thdxr, typesafeai, DX Core 4, dylan522p, The Untrainable, gregisenberg #14, satyanadella) found all 10 processed** under different slugs, as on 10-15. The matching misses come from June-era source pages that didn't record status URLs.

## 7. `canonical-` filler: 1,635 instances on 65 entity pages

`index.md` and `log.md` are clean. Ranked by instances × inbound links, the worst offenders are:

| Page | Instances | Inbound |
|---|---|---|
| `companies/allenai` | 71 | 11 |
| `companies/alibaba` | 78 | 8 |
| `people/khairallah` | 84 | 7 |
| `people/eric-topol` | 94 | 6 |
| `people/0xmovez` | 89 | 6 |
| `companies/gray-swan` | 66 | 8 |
| `companies/general-intuition` | 110 | 4 |
| `people/charity-majors` | 30 | 13 |
| `tools/colossus-2` | 43 | 9 |
| `tools/mem0` | 21 | 18 |

**The pages most readers hit are already clean.** The most-linked affected page has 18 inbound links, against 405 for `loop-engineering` when the work began. The remaining work is real but low-traffic.

The milder template phrases: `wiki-captured` 467 times (278 as "First wiki-captured"), `STRUCTURALLY MAJOR` 26, `canonical-anchor-tier` 4.

Source pages carry 14,757 more instances across 128 pages. They are out of scope under rule 7 but noted here.

## Log size: 379 KB, and the rules conflict

`log.md` holds September (210 KB, 34 entries) and October (168 KB, 27 entries). **The rollover rule triggers on size above ~150 KB, but retention says to keep the current and prior month**, and the file already holds only those two. Rolling September out would meet the size limit and break the retention rule.

**The cause is entry length, not entry count.** October averages over 6 KB per entry, against the "facts a future dedup needs" standard. Options for the owner:
- (a) roll September now and accept one month in `log.md`
- (b) leave it and keep new entries short
- (c) change the size threshold

## Not flagged

- Three empty `Untitled*.md` files at the vault root (70 bytes each, 2026-10-01) are excluded from every PR by convention. They can be deleted.
