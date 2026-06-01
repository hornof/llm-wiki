---
name: Lint Report 2026-06-01
type: meta
last_updated: 2026-06-01
---

# Lint Report — 2026-06-01

**Last lint**: 2026-05-29 (3 days ago, ~14 ingest sessions ago).
**Pages scanned**: 392 (sources 229 + tools 22 + models 4 + concepts 29 + people 49 + companies 31 + topics 5 + tutorials 2 + owner 2 + meta 15 + root 4).
**Net delta vs last lint**: **+34 pages in 3 days** (sources +25; meta +2; tools +1; people +3; companies +3).
**Raw files scanned**: 177 (was 161 at last lint; +16).

> [!note] First-run miss
> Initial run of this lint scanned 388 pages (pre-PR-64). PR #64 had merged on origin/main but my local main was stale because my prior `git pull` returned "Already up to date" against an unrefreshed origin tip; I trusted it without `git fetch` first. Re-ran with `git fetch origin && git pull` to pick up PR #64's 3 new sources + entity updates. **Pre-lint workflow updated** (see [§5 Pre-lint discipline](#5-pre-lint-discipline)).

## Summary

The wiki is in **strong overall health** and **discipline is improving over time**:

| Check | Result | vs last lint |
|---|---|---|
| Pages with stale `last_updated` (>60 days) | **0** | unchanged ✓ |
| Pages with missing `last_updated` frontmatter | **0** | unchanged ✓ |
| Sources missing `## Pages Updated` section | **0** | unchanged ✓ |
| Sources with empty Pages Updated section | **7** (all explicit "no entity changes" — intentional) | unchanged |
| Tools missing/thin Traction Signals | **0** | unchanged ✓ |
| Duplicate slugs across the vault | **0** | unchanged ✓ |
| Orphan pages outside `meta/` | **0** | unchanged ✓ |
| Real dead-link unique targets (active content) | **22** | was 14 (4 fixed; ~12 added by recent ingests; older ones carried) |

The discipline-side of the wiki is bulletproof. The dead-link surface drifts up with each ingest wave; mostly fixable in a single mechanical pass.

---

## 1. Real Dead Links (post-regex-fix)

**Regex fix**: my prior dead-link detection over-counted by ~13 false positives — markdown-table wikilinks with escaped pipes (`[[slug\|display]]`) caused the regex to capture the trailing `\` as part of the slug. The fixed regex (excluding `\` from the slug character class + stripping trailing escape) cleaned up the noise.

### 1a. Authored this week (post-2026-05-29-lint ingests)

| Broken link | From | Suggested fix |
|---|---|---|
| `[[zodchii-4-agent-pipeline-2026-05-31]]` | `nateherk-dynamic-workflows-2026-05-30` | **Slug typo** — actual page is `zodchii-4-agent-pipeline-2026-05-30` |
| `[[autoresearch]]` | `nateherk-dynamic-workflows-2026-05-30`, `log` | Page doesn't exist; reference was speculative. Either create concept page or remove wikilink |
| `[[eng-khairallah]]` | `nate-herk`, `dailybrief-roundup-2026-05-31` | Entity page deferred; either create stub or reference `[[eng-khairallah-multi-agent-team-course-2026-05-15]]` source-page slug directly |
| `[[matt-pocock]]` | `dailybrief-roundup-2026-05-31` | 2nd Pocock surface noted; still deferred (reactive friction). Either create stub or strip wikilink |
| `[[swyx]]` | `latentspace-walden-yan-async-agents-2026-05-29` | No entity page; either create stub or reference source pages directly |
| `[[ai-native-service-companies]]` | `latentspace-walden-yan-async-agents-2026-05-29` | Concept page doesn't exist; would link 5+ existing wiki entries if created. Either create concept page or reference `[[gustaf-alstromer]]` who carries the framing |

### 1b. Authored in the just-merged PR #64 (2026-06-01 ingest)

| Broken link | From | Suggested fix |
|---|---|---|
| `[[david-manheim-opus-4-8-subagent-token-critique-via-dailybrief-supplemental-2026-05-31]]` | `dailybrief-roundup-2026-06-01` | I invented this absurdly-long speculative slug for a page that doesn't exist. **Replace with** `[[dailybrief-supplemental-2026-05-31]]` (the real page where Manheim is captured) |
| `[[opencode]]` | `dailybrief-roundup-2026-06-01` | PewDiePie's odysseus mentions opencode; no opencode page exists. Either create stub or strip |
| `[[gerard-sans]]` | `dailybrief-roundup-2026-06-01` | Entity page deferred multiple times despite recurring mentions; either create stub or reference his prior wiki surfacing in `[[zephyr-karpathy-10-year-agent-window-2026-05-14]]` (Ríos-García citation) |

### 1c. Carried over from last lint (not yet addressed)

| Broken link | From | Notes |
|---|---|---|
| `[[claude]]` (bare) | `log` (May 11 reference) | Likely intended `[[claude-mythos]]` or `[[claude-code]]` |
| `[[meta]]` (bare) | `lecun-after-llms-unsupervised-learning-2026-05-15` | Should be `[[meta-platforms]]` if created |
| `[[stainless]]` | `anthropic` | Single mention; either remove or stub |
| `[[google-search]]` | `google-io-2026-flash-omni-spark-antigravity` | Either tool/google-search stub or strip |
| `[[agent-memory]]`, `[[claude-managed-agent-memory]]` | `milesdeutscher-claude-personal-cfo-2026-05-14` | Speculative concept-page names; should reference `[[mem0]]` / `[[company-brain]]` |
| `[[in-the-weeds]]` | `stahlberg-team-os-aakash-2026-05` | Stulberg's newsletter; either stub or strip |
| `[[clickup-mass-layoff-via-roundup]]` | `dailybrief-roundup-2026-05-26` | Should be `[[dailybrief-roundup-2026-05-26]]` self-reference removed, or `[[clickup]]` stub |
| `[[claude-code-did-my-taxes]]` | `klmn-claude-code-taxes-2026-01-07` | Self-reference; remove |
| `[[shipper takeaway 2 "automation is a lie"]]` | `dailybrief-roundup-2026-05-26` | Quoted-string with-spaces wikilink — malformed; strip or convert to plain text |
| `[[people/]]` (empty path) | `willison-boris-mann-11-agents-2026-05-13` | Typo — slug fragment, not a real link |
| `[[agi-debate]]` | `index` | Canvas reference; should be `[[agi-debate.canvas]]` or restructured |
| `[[claude-opus-4-6]]` | `log` (May 8 entry) | Historical reference; either stub or leave |

### 1d. Documentation false positives (do not fix)

Intentional examples in CLAUDE.md and old `meta/lint-report-*` files (`[[Page Name]]`, `[[wikilink]]`, `[[slug]]`, etc.). Excluded from the count.

---

## 2. `_raw/` Hygiene

177 raw files on disk; 77 in manifest. **+16 raw files since last lint**.

### 2a. Tiny files (likely placeholders or thin-content drops)

| Size | File | Notes |
|---|---|---|
| 420b | `AI Ascent 2026.md` | Old conference reference |
| 546b | `Post by @_arohan_ on X.md` | Already processed in pt3; numeric-variant `... 1.md` at 1941b has fuller content |
| 548b | `Hannah Stulberg  Substack.md` | Kept from prior lint (has Mother's Day content); intentional |
| 553b | `Post by @PeterDiamandis on X.md` | Generic platitude, processed-and-skipped 2026-05-29 |
| 574b | `Post by @mattpocockuk on X.md` | Reactive friction post, processed-and-skipped 2026-05-29 |

**Recommendation**: keep all 5 — they're processed-and-documented (Stulberg, Pocock, Diamandis, _arohan_, AI Ascent 2026) rather than empty placeholders.

### 2b. Duplicate filename variants (Web Clipper double-captures)

**16 groups** of numeric-variant duplicates. Sizes differ for all of them — they're different snapshots of the same X URL captured on different dates, not byte-identical duplicates.

**0 byte-identical pairs** verified by `cmp` (the two that were identical at the May 29 lint were deleted then).

**Recommendation**: leave them. The diff-size suggests Web Clipper is correctly capturing different points-in-time.

### 2c. Truly unprocessed (heuristic — name not mentioned in any source/log/CLAUDE)

**69 files** flagged as "truly unprocessed" by the name-mention heuristic (was 54 at last lint). **Caveat**: this is an upper bound — many ARE processed but the source page doesn't quote the raw filename verbatim (the manifest under-reports by ~50%).

Worth a future pass: drill into the 16 *new* unprocessed entries from the last 3 days to ensure none are genuinely-skipped high-value drops.

---

## 3. Orphans

**14 orphan pages** — all in `meta/`. Same pattern as last lint: lint-report files (`meta/lint-report-*.md`) including this one. They don't need inbound links; they're date-indexed log entries, not content nodes.

**No real-content orphans.** The wiki's cross-reference discipline continues to hold.

---

## 4. Manifest Hygiene (still unresolved)

`_raw/.manifest.json` still tracks **77 of 177 files** (~43%). The manifest is unreliable for lint purposes — the wiki uses log.md-based dedup per CLAUDE.md, not the skill-spec manifest.

**Same recommendation as last lint**: either retire the manifest (favor the log.md-based dedup workflow per CLAUDE.md), or commit to populating it post-ingest. The current half-state produces unreliable lint signals.

---

## 5. Pre-lint discipline

This lint's first run got the wrong page count (388 instead of 392) because my local main was stale. `git pull` returned "Already up to date" against an unrefreshed origin tip. Updated pre-lint checklist for future runs:

1. **`git fetch origin`** — force-refresh, don't trust the cached origin ref
2. **`git log main..origin/main`** — explicitly inspect any incoming commits
3. **`git pull`** if anything's there
4. **`gh pr list --state open`** — confirm zero open PRs touching the wiki
5. **`gh pr list --state merged --search "merged:>2 hours ago"`** — sanity check for very recent merges
6. **`brctl download "Daily Briefs/" "_raw/"`** — force-fetch any iCloud-offloaded files (caught the 2026-06-01 brief mid-ingest yesterday)
7. Run lint

The cost of these checks is ~5 seconds; the cost of skipping them is a stale lint that has to be rewritten.

---

## Other state worth cleanup (not lint-blocking)

- **18 stale local branches** (`ingest/2026-05-06` through `ingest/2026-05-15`, plus several `chore/*`). All merged into main via PRs but never deleted locally. Owner cleanup: `git branch -d` each one, or `git branch --merged main | grep -v main | xargs git branch -d`.
- **`meta/lint-report-2026-06-01.md` is uncommitted** on main right now (just sitting in the working tree). Same pattern as prior lint reports — gets committed when fix-batch lands.

---

## What I Want to Auto-Fix vs Defer

I will not auto-apply anything without sign-off. The fixes I'd recommend, batched by risk:

**Safe + high-leverage (recommend doing)**:
- Fix the `[[zodchii-4-agent-pipeline-2026-05-31]]` → `-2026-05-30` slug typo (1 mechanical fix)
- Fix `[[david-manheim-opus-4-8-subagent-token-critique-via-dailybrief-supplemental-2026-05-31]]` → `[[dailybrief-supplemental-2026-05-31]]` (real page that already covers Manheim; speculative slug I invented should be retired)
- Strip the `[[eng-khairallah]]`, `[[matt-pocock]]`, `[[swyx]]`, `[[gerard-sans]]`, `[[opencode]]` wikilink-forms where they're referenced (5 deferred entities) OR create stubs
- Fix the `[[shipper takeaway 2 "automation is a lie"]]` malformed wikilink and `[[people/]]` empty-path typo
- Cross-reference `[[agent-memory]]` / `[[claude-managed-agent-memory]]` to `[[mem0]]` / `[[company-brain]]`

**Mid-leverage stubs (worth a "yes" or "no" each)**:
- Create stubs for `people/eng-khairallah`, `people/matt-pocock`, `people/swyx`, `people/gerard-sans`, `concepts/ai-native-service-companies`. Each has 1-2 inbound; useful but discretionary.

**Defer**:
- `_raw/` triage for the 16 new "potentially unprocessed" drops — needs per-file verification
- Manifest hygiene (decision: retire or maintain)
- Older single-ref dead links (`[[stainless]]`, `[[google-search]]`, `[[in-the-weeds]]`, etc. — owner judgment call on each)
- Stale local branch pruning (housekeeping; not lint-blocking)
