---
name: Lint report 2026-10-15
type: lint-report
last_updated: 2026-10-15
---

# Lint report — 2026-10-15

**Corpus**: 987 markdown files — 42 tools, 17 models, 51 concepts, 112 people, 65 companies, 6 topics, 2 tutorials, 607 sources, 71 meta, 2 owner.
**Delta**: 14 ingests since the 2026-09-21 lint.

## Summary

**The structural state is clean and the content state is not.** Every link-integrity and integration check returns zero. **The two largest defects were both things no existing lint rule detected** — `canonical-` filler (**~2,781 instances across 73 pages**, 5× worse than the first pass measured) and 43 roundup sources whose exemption wasn't machine-visible. **Both are now addressed: rule 7 added, all 89 URL-less sources annotated, and the 8 worst-corrupted pages rewritten.**

| Check | Result |
|---|---|
| 1. Orphan entity pages | **0** |
| Weakly integrated (1 inbound) | **0** |
| Source pages with 0 inbound | **0** |
| Dangling links on entity pages | **0** *(see checker bug)* |
| 2. Stale >60d, genuinely **behind** | **2 confirmed, 1 arguable** |
| Dormant, not yet marked | **5** |
| 2a. Tracked open-question items | **153** across 27 pages |
| 3. Sources with no Pages Updated | **0** |
| 3a. Missing URL, real defects | **0** — but **43 pages need `local_source:`** |
| 4. Tools missing Traction Signals | **2** |
| 5. Contradictions | **1 real, 1 missing status** |
| 6. Unprocessed `_raw` drops | **≈0** (21 heuristic misses, spot-checked clean) |
| **`canonical-` filler** | **~2,781 instances, 73 pages** — *see correction* |

---

## 1. Link integrity — clean, and the checker had a bug

**0 orphans, 0 weakly-integrated entity pages, 0 source pages without inbound links.**

**Dangling links on entity pages: 0.** The first pass reported 3; all were false positives, and finding out why **fixed a defect in the lint tooling itself**:

| Reported | Actually |
|---|---|
| `tools/obsidian.md` → `[[wikilink]]` | inside a backtick code span — **documentation of the syntax** |
| `tools/obsidian.md` → `[[Page Name]]` | same |
| `companies/anysphere.md` → `[[cursor]]` | inside the merge note explaining *"inbound `[[cursor]]` links now point here"* |

**The checker must strip fenced blocks and inline code spans before extracting links.** Every prior lint that counted dangling links without doing this over-reported. **This also explains the "4 dangling targets on entity pages" figure reported on 2026-10-03 — it was 3 of these plus one since resolved, and none was ever real.**

**Long-tail, unchanged and still out of scope**: 281 dangling targets across `sources/` (233 distinct), overwhelmingly one-off `[[handle]]` ghosts from May–July ingests; 403 in `meta/` (lint reports and log archives referencing things by display name).

**Two of those long-tail targets are worth promoting, because they are entities rather than handles**: `hermes-agent` (×2) and `vercel` (×2).

## 2. Staleness — the dormant/behind split

**35 tool/model pages exceed 60 days.** Applying the 45-day resurfacing test with word boundaries:

### Genuinely behind — 2 confirmed

- **`tools/alphafold.md`** (2026-07-28, 79d) — **the consequential one.** Two real surfaces: [[topos-bio-redefining-druggable-space-2026-09-30]] argues AlphaFold's formulation doesn't cover intrinsically disordered proteins, and the **2026-10-09 brief carried *"Why AlphaFold didn't solve protein folding"*** — which the ingest flagged as *"would materially revise that page."* **`dormant_since` not set, correctly.**
- **`models/kimi-k3.md`** (2026-07-28, 79d) — Treasury Secretary **Bessent alleging *"Kimi says it is Claude"*** (2026-10-03). A claim about the model's provenance from a cabinet secretary is new information about the entity.

### Arguable — 1

- **`tools/claude-agent-sdk.md`** (2026-07-08, 99d, marked dormant 09-20) — three name surfaces, zero wikilinks: it is **Moyai's default harness** and the platform for the agent-teams course, where *"the default is unlimited"* on `max_budget_usd` was documented. **Named repeatedly as infrastructure rather than discussed as a subject.** Borderline; the spend-cap default is genuinely page-worthy.

### False positive — 1, and it is the documented failure mode recurring

- **`tools/river.md`** — one hit, and it is a **passing comparison** (*"is [[river|Shopify's River]] (agents in public Slack channels)"*) used to illustrate a convergence in the FDE fold. **Exactly the class CLAUDE.md warns about**: *"the one surviving match for `River` was a passing category listing, not new information about the entity."* **Still correctly dormant.**

### Dormant but unmarked — 5

`tools/bun.md` (64d), `tools/marble.md` (72d), `tools/qm.md` (76d), `models/flux-3.md` (82d), `models/muse-glimmer.md` (64d). **26 of 31 dormant pages already carry `dormant_since`; these five are the gap.**

## 2a. Open-question backlog — 153 items

**153 tracked items inside dedicated `Verification-pending` / `Open Questions` sections, across 27 pages.** Separately, **~124 inline provenance caveats**, which are **the sourcing discipline working and are not debt** — not counted, not to be "resolved" by deletion.

**Against 2026-09-21's ~163 items across ~83 pages**: the **item** count is down ~6%, but **the page count fell from ~83 to 27**, which is the more meaningful change — the backlog has consolidated onto the pages that actively cite figures rather than being smeared across the corpus. **Comparison caveat: the 09-21 figure came from a differently-shaped regex, so treat the item delta as indicative, not measured.**

**Highest-value items, by the "does the wiki cite this?" test:**

1. **Anthropic's prospectus** — six economics items on `companies/anthropic` (gross margin, inference cost, burn rate, customer concentration, revenue basis, the Series G date inconsistency) are **jointly answerable by one public document**. Eighteen days after filing, the wiki has executive compensation and a growth rate.
2. **Anthropic's Opus 5.5 prompting guide** — the source of *every* number on `models/claude-opus-5-5`, including the Terminal-Bench comparison against the larger Fable 5.1.
3. **The CMU full PDF** (arXiv:2609.26550) — per-benchmark breakdowns and the comparator's identity, behind the Jev calibration argument.
4. **Jev's RLCD calibration evidence** — the single load-bearing claim behind a $7.5B valuation, unevidenced for a month.

## 3a. Missing URLs — 0 real defects, 43 pages of invisible exemption

**0 genuine missing-URL defects.** But the raw rule flags **68**, and after a content-based roundup exemption, **43 remain flagged** — *all of them* `dailybrief-roundup-*` or `raw-batch-roundup-*` from **2026-05 through 2026-09**.

**These are correctly authored and incorrectly annotated.** CLAUDE.md rule 3a says: *"leave `url:` empty and record `local_source: '_raw/<file>'`."* Recent roundups do. **The 43 older ones predate that habit, so the exemption exists only in my judgement at ingest time and nowhere on the page** — which means **every future lint re-flags them, forever.**

**This is the cheapest real fix available**: add `local_source: "Daily Briefs/YYYY-MM-DD.md"` to 43 files, derived from each filename.

## 4. Tools missing Traction Signals — 2

- **`tools/google-agents-cli.md`** — the section is absent entirely. **Also one of the `canonical-`-corrupted pages** (see below), so a rewrite would fix both.
- **`tools/gstack.md`** — **owner-authored, 2026-10-01.** It has a *"Who's Using It"* section serving the same purpose (Tan's daily use, star count as proxy, no independent receipts). **Schema deviation, not a content gap** — either rename the section or record the exemption.

## 5. Contradictions — 1 real, 1 gap

**`companies/hugging-face.md` contradicts itself on the NVIDIA acquisition:**

- Frontmatter: `status: acquisition-announced-close-unconfirmed`
- Body: *"**DEAL-CONFIRMED-AT-$12.9B** — Nvidia **confirms** it will buy Hugging Face for $12.9 billion"* (2026-09-03, TechCrunch)

**A confirmed *deal* and an unconfirmed *close* are compatible — but the page never says so**, and the body's language reads as flatly contradicting the field.

**The sharpest part: line 18 of that page is a note about this exact defect class.** It records that the status field read `gaining-traction` until 2026-09-14 while the body described a confirmed acquisition, and calls it *"the same defect class as the `claude-mythos` naming contradiction: the body was kept current, the frontmatter was not."* **The page documents the failure mode and has it again, in a subtler form.** This is also the [[anysphere]] lesson — *"close unconfirmed" for five weeks after the deal closed* — and the wiki **cannot verify the close without web access.**

**`companies/zhipu-ai.md` has no `status:` field** — the only entity page in the corpus missing one. (Frontmatter is otherwise complete across all 222 entity pages: **0 gaps**.)

**Status-vocabulary drift, noted not flagged**: 4 pages use free-text descriptive values (`acquired (SpaceX, closed 2026-08-14)`, `incumbent + foundry-tier vendor`, `incumbent + frontier-lab parent`, `established`). CLAUDE.md's Status Fields section permits this where annotated; all 4 are.

## 6. `_raw` — effectively clean

**526 files. 21 fail a token-match coverage heuristic; spot-checking three found zero real backlog:**

- `@typesafeai` (2026-09-15) — *"we are officially out of stealth!"* → covered by [[jev-typesafe-system-one-model-2026-09-18]]
- `@rambuilds_` — *"15 AI related accounts you should follow"* → a follow list
- `@EnoReyes` — a CTO's thoughts on burnout → not AI-engineering content

**The heuristic is the problem, not the backlog.** It matches on a handle or first long word, which fails whenever a drop was folded under a source slug rather than its filename — **the documented `_raw` dedup blind spot, reappearing as a lint false positive instead of an ingest one.**

## The finding no rule catches: `canonical-` filler

> [!warning] Measurement corrected after the first pass
> **The initial count in this report was wrong by roughly 5×, and the ranking was wrong too.** I used `grep -c`, **which counts matching *lines*, not occurrences** — so a line with eight instances counted as one. Re-measured with code spans stripped and occurrences counted:
>
> | | First pass (`grep -c`) | Corrected |
> |---|---|---|
> | Instances | *not measured* | **~2,781** |
> | Pages affected | 74 | **73** |
> | Worst page | `concepts/okf.md` (46) | **`people/min-choi.md` (147)** |
>
> **This is the same class of error CLAUDE.md rule 2a documents for the open-question backlog** — *"mis-measured in four consecutive lint passes"* — and it happened here for the same reason: a convenient grep flag that answers a slightly different question than the one asked. **Rule 7 and the tooling notes now say to count occurrences with code spans stripped.**

**~2,781 instances of `canonical-` prefix filler across 73 entity pages**, from an automated pass. Worst offenders by the corrected metric:

| Page | Instances |
|---|---|
| `people/min-choi.md` | **147** |
| `companies/metr.md` | 132 |
| `companies/microsoft.md` | 127 |
| `companies/general-intuition.md` | 110 |
| `people/eric-topol.md` | 94 |
| `companies/hugging-face.md` | 93 |
| `people/0xmovez.md` | 89 |
| `people/jelani-nelson.md` | 85 |

**876 distinct filler forms**, uniformly `canonical-` plus a word that would be valid prose without it — *"canonical-vendor-neutral canonical-open-specification"*, *"canonical-Google canonical-coding-agent canonical-CLI-tier-cohort"*.

**The owner found and fixed one instance** (`tools/antigravity.md`, 2026-10-02), leaving the note: *"the 2026-06-29 version was corrupted with 'canonical-' filler from an automated pass."*

**This is the largest quality defect in the corpus and every structural rule misses it.** It is not a broken link, a stale date, a frontmatter gap or an empty section. **It is prose that reads as machine output**, and it leaves every check green.

**It cannot be fixed by find-and-replace**, which is why rule 7 says so explicitly. The filler is woven into sentences, and there is a second layer underneath it: hyphens joining words that should be spaces. *"canonical-coding-agent"* → *"coding agent"* is a judgement, not a substitution.

### Fixed this pass — 8 pages, ~558 instances

| Page | Was | Now | Also fixed |
|---|---|---|---|
| `people/min-choi.md` | 147 | **0** | — |
| `companies/metr.md` | 132 | **0** | 2 path-form links; evaluator-independence comparison added |
| `concepts/okf.md` | 46 | **0** | 2 path-form links |
| `models/claude-sonnet-5.md` | 28 | **0** | 1 path-form link |
| `companies/stripe.md` | 28 | **0** | `focus:` frontmatter; 4 missing 2026-10 surfaces added |
| `companies/etched.md` | 28 | **0** | `focus:` frontmatter; 2 path-form links |
| `models/gpt-5-6.md` | 26 | **0** | 2 path-form links |
| `companies/arena.md` | 24 | **0** | `focus:` frontmatter; Series B + Alignment Index added |

**Each rewrite preserved the content and the recent clean sections verbatim**, and carries a dated page-history note. **Three of the eight were also four months stale on material facts** — Arena had raised at 31× since its page was written, Stripe had acquired OpenRouter and appeared in the agent-spending-safeguards story, and METR's independence question had become live. **The filler was hiding staleness**, because a page nobody can read is a page nobody re-reads.

### Remaining: ~2,223 instances across 65 pages

**Worst remaining**: `companies/microsoft.md` (127), `companies/general-intuition.md` (110), `people/eric-topol.md` (94), `companies/hugging-face.md` (93), `people/0xmovez.md` (89).

**At roughly 4,000 tokens per page this is a 60-page project, not an ingest side-effect.** The honest scoping: **rule 7 now detects it, 8 of the worst are done, and the remaining 65 need a dedicated pass or several.**

## Watch-items

- **`hermes-agent` is the wiki's most-referenced unpaged entity — 21 files** and now a dangling link target ×2. Carried as a create-candidate since the 2026-08-02 lint. **Still blocked on the same thing: no primary describing what Hermes is.**
- **`gemini`** — flagged 2026-10-03 as the highest-value create-candidate. The wiki has a page for every frontier and near-frontier model line **except** Gemini, which has 12+ mentions on `companies/google-deepmind`. A plugin adding Gemini 4 Argon support (2026-10-14) is not a substitute.
- **`vercel`**, **`typesafe-ai`** (two surfaces plus an $870M round), **`amd`** ($8.2B acquisition, one surface) — create-candidates with specific triggers.
- **`companies/hugging-face`** — the NVIDIA close needs confirming; the anysphere precedent says this class of field goes stale silently for weeks.

---

## Actions taken this pass (all five items the owner approved)

| # | Item | Status |
|---|---|---|
| 1 | `local_source:` on URL-less roundups | **done** — 68 annotated, **50 paths corrected** to `Daily Briefs/archive/YYYY-MM/`, rule 3a now returns **0** |
| 2 | Staleness | **done** — `alphafold` and `kimi-k3` refreshed; 5 pages marked `dormant_since` |
| 3 | Contradictions | **done** — `hugging-face` status disambiguated with the anysphere precedent attached; `zhipu-ai` given the missing `status:` |
| 4 | `canonical-` cleanup | **8 worst pages rewritten (~558 instances); ~2,223 across 65 pages remain** |
| 5 | Rule 7 in `CLAUDE.md` | **done** — plus a *Lint tooling notes* section |

**A fix beyond the five, found while doing item 1**: the 50 `local_source` paths I first wrote pointed at `Daily Briefs/<date>.md`, **which does not exist for any brief older than ~two weeks** — they roll off to `Daily Briefs/archive/YYYY-MM/`. **Writing a path that dangles the moment the brief rolls off would have recreated the same invisible-exemption problem one layer down.** All 50 corrected and verified on disk; **0 `local_source` paths now dangle.**

### Two tooling fixes recorded in CLAUDE.md

1. **Strip code spans before extracting wikilinks.** Every prior lint over-reported dangling links, including the "4 on entity pages" from 2026-10-03, which was never real.
2. **Count occurrences, not lines.** `grep -c` understated the filler by ~5× and mis-ranked every offender.

**Both were errors in the measuring instrument rather than the corpus**, which is the recurring theme of this report: **the wiki's structural health is genuinely good, and three of the four numbers this lint started with were wrong.**
