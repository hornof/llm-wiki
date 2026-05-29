---
name: Lint Report 2026-05-29
type: meta
last_updated: 2026-05-29
---

# Lint Report — 2026-05-29

**Last lint**: 2026-05-15 (14 days ago, 4 ingest sessions ago).
**Pages scanned**: 358 (sources 204 + tools 21 + models 4 + concepts 29 + people 46 + companies 28 + topics 5 + tutorials 2 + owner 2 + meta 13 + root 4).
**Raw files scanned**: 161.

## Summary

The wiki is in **strong overall health**. All discipline checks pass cleanly:

| Check | Result |
|---|---|
| Pages with stale `last_updated` (>60 days) on tool/model/concept/person/company/topic | **0** |
| Pages with missing `last_updated` frontmatter | **0** |
| Sources missing `## Pages Updated` section | **0** |
| Sources with empty Pages Updated section | **7** (all intentional — explicit "no entity changes" / candidate-flagged) |
| Tools missing/empty Traction Signals | **0** |
| Duplicate slugs across the vault | **0** |
| Orphan pages outside `meta/` | **0** |

Active findings cluster into three buckets: (1) **broken wikilinks from this week's ingests** (deferred-entity stubs that should resolve), (2) **slug normalization gaps** (case mismatches, missing path prefixes, drifted date suffixes), and (3) **`_raw/` hygiene** (~54 unreferenced drops, 3 tiny placeholders, 14 duplicate-filename groups from Obsidian Web Clipper).

---

## 1. Dead Links — Real (active content only)

97 total dead-link instances detected; 36 of those are documentation examples in old `meta/lint-report-*` files and `meta/obsidian.md` (`[[Page Name]]`, `[[wikilink]]`, `[[slug]]`, `[[topics/y]]`, etc. — literal documentation, not real links). The remaining ~30 instances are real.

### 1a. Broken links created by this week's ingests (highest priority)

These were authored in 2026-05-27 and 2026-05-28 ingest sessions. Fix path: either create a thin stub page or remove the wikilink form.

| Broken link | From | Notes |
|---|---|---|
| `[[box]]` | `aaron-levie`, `levie-ceo-ai-psychosis-2026-05-23` | Box is the company Levie founded. **Stub-worthy** — 2 inbound refs from active entities. |
| `[[doordash]]` | `hannah-stulberg`, `stahlberg-team-os-aakash-2026-05` | Stulberg is a DoorDash PM. **Stub-worthy** — 2 inbound refs. |
| `[[heeki-park]]` | `heeki-spec-driven-development-2026-02-28` | Source page explicitly defers entity creation but leaves wikilinks. Either create thin stub or remove `[[…]]` form. |
| `[[felixaix-anthropic-founders-playbook-2026-05-27]]` | `anthropic-founders-playbook-2026-05` | Source page explicitly notes "subsumed into this page — no separate page created" but leaves dead wikilink. **Remove the wikilink form.** |
| `[[bun]]` | `anthropic-dynamic-workflows-primary-2026-05-28` | The Bun port is the launch case study; 1 inbound but high-signal context. **Stub-worthy.** |
| `[[dan-shipper]]` | `claude-opus-4-8-dynamic-workflows-2026-05-28` | Single source today; per pattern, defer entity page. **Remove the wikilink form** or create stub. |
| `[[devin]]` | `cognition-26b-valuation-492m-arr-2026-05-27` | Devin is Cognition's product. **Stub-worthy** if Cognition stays in news. |
| `[[capone]]` | `sqlite-agents-md-2026-05-27` | Should be `[[luca-capone]]` — slug typo. |
| `[[zephyr]]` | `sqlite-agents-md-2026-05-27` | No entity page exists. The references in concept pages use `zephyr-7-claude-setups-2026-05-15` (source slug). **Slug typo** — should reference the source page directly. |

### 1b. Slug typos / case mismatches

| Broken link | From | Should be |
|---|---|---|
| `[[LLM Wiki Pattern]]` | `CLAUDE.md` (live; the other 6 refs are in old lint reports — documentation) | `[[llm-wiki-pattern]]` per slug convention |
| `[[mistral]]` | `lecun-after-llms-unsupervised-learning-2026-05-15` | `[[mistral-ai]]` |
| `[[anthropic-claude-partner-network-2026-03]]` | `anthropic-founders-playbook-2026-05` | `[[anthropic-claude-partner-network]]` (no -2026-03 suffix; page exists without it) |
| `[[willison-andon-cafe-stockholm-2026-05-07]]` | `willison-anthropic-openai-pmf-2026-05-27` | Verify slug — likely `[[willison-andon-cafe-stockholm-2026-05]]` (no `-07` day suffix) |
| `[[willison-anthropic-xai-colossus-2026-05-07]]` | `willison-anthropic-openai-pmf-2026-05-27` | Same — `[[willison-anthropic-xai-colossus-2026-05]]` exists |

### 1c. Single-ref dead links worth deciding on

| Broken link | From | Suggested action |
|---|---|---|
| `[[claude-opus-4-6]]` | `log`, `lint-report-2026-05-08` | Stub for predecessor-model continuity? Cheap. |
| `[[dario-amodei]]` | `log`, `lint-report-2026-05-08` | Stub for Anthropic co-founder? Currently no people page despite Anthropic being the most-discussed company. |
| `[[stainless]]` | `anthropic` | Single mention; remove wikilink form. |
| `[[claude]]` (bare) | `log`, `lint-report-2026-05-11` | Likely intended `[[claude-mythos]]` or `[[claude-code]]` — disambiguate. |
| `[[meta]]` (bare) | `lecun-after-llms-unsupervised-learning-2026-05-15` | Likely intended `[[meta-platforms]]` — page doesn't exist; create stub or remove. |
| `[[agi-debate]]` (4 refs) | `index`, lint reports | The canvas is `agi-debate.canvas`; `[[agi-debate]]` may need `.canvas` extension or rename. Obsidian-version-specific behavior. |
| `[[google-search]]`, `[[agent-memory]]`, `[[claude-managed-agent-memory]]`, `[[in-the-weeds]]`, `[[clickup-mass-layoff-via-roundup]]`, `[[claude-code-did-my-taxes]]`, `[[learn-agentic-ai]]` | various single-source pages | Each 1 ref — either create stub or remove wikilink form. |

### 1d. False positives — do not fix

These are documentation examples in old lint reports, the obsidian skill page, and CLAUDE.md examples. The wikilink syntax is shown literally as documentation. Leave as-is or move out-of-vault if Obsidian still flags them in dataview:
- `[[Page Name]]` (9 refs), `[[wikilink]]` (9), `[[slug]]` (2), `[[concept]]` (2), `[[X]]` (2), `[[topics/y]]`, `[[topics/baz]]`, `[[concepts/x]]`, `[[concepts/z]]`, `[[people/y]]`, `[[people/z]]`, `[[tools/y]]`, `[[sources/foo]]`, `[[companies/bar]]`, `[[companies/x]]`, `[[Note Name]]`, `[[Page A]]`, `[[Page B]]`, `[[Page C]]`, `[[Daily Briefs/2026-05-10-personal.md]]` (in CLAUDE.md as a documented filename example).

---

## 2. Missing-Entity Stub Candidates (sorted by net value)

If we want to clear the active-content dead links AND give the wiki a discoverable home for entities mentioned in 2+ ingests, the highest-leverage stubs are:

1. **`companies/box.md`** — Box; 2 inbound from `aaron-levie` + `levie-ceo-ai-psychosis-2026-05-23`. Worth a 30-line stub.
2. **`companies/doordash.md`** — DoorDash; 2 inbound from `hannah-stulberg` + `stahlberg-team-os-aakash-2026-05`.
3. **`people/heeki-park.md`** — AWS solutions architect; 7th+ CLAUDE.md surface (added today). Single-source, but the pattern of explicit-defer-then-leave-wikilinks suggests stubs are worth more than the wikilink-stripping cost.
4. **`tools/bun.md`** — JavaScript runtime / build tool; the Anthropic Dynamic Workflows launch case study lives here. Becomes higher-leverage if Jarred Sumner's primary write-up surfaces.
5. **`tools/devin.md`** OR **`companies/cognition.md`** — Cognition with $492M ARR ([[cognition-26b-valuation-492m-arr-2026-05-27]]) is past the "single-source defer" threshold; multiple ingests reference Devin/Cognition.
6. **`people/dario-amodei.md`** — surprising gap; Anthropic is the most-referenced company on the wiki and the co-founder/CEO has no entity page.

Lower-leverage (1 inbound, single-source):
- `people/dan-shipper.md`, `people/felix-aix.md`, `companies/mistral-ai.md` (page exists; just slug-fix), `models/claude-opus-4-6.md`, `tools/codex.md` (mention is in old lint report only — false positive).

---

## 3. `_raw/` Hygiene

161 raw files on disk; 76 in manifest as processed; **~54 likely unprocessed** by name-mention heuristic (manifest under-reports — caveat: this is an upper bound; some of these are processed but the source page doesn't mention the raw filename verbatim).

### 3a. Tiny placeholder files (likely safe to delete)

| Size | File |
|---|---|
| 493b | `1776157497718 1,280×1,600 pixels.md` (image-clipper artifact) |
| 548b | `Hannah Stulberg  Substack.md` |
| 548b | `Hannah Stulberg  Substack 2.md` |

### 3b. Duplicate filename variants (Obsidian Web Clipper double-captures)

14 groups; the diff sizes suggest different snapshots of the same URL captured on different dates. Consolidation or deletion of the smaller / older snapshot:

| Group | Variants (size) |
|---|---|
| `Post by @Av1dlive on X` | 765b / 2088b / 2107b |
| `Post by @benln on X` | 2638b / 2748b / 2823b |
| `Post by @elora_khatun on X` | 3497b / 4383b |
| `Hannah Stulberg Substack` | 548b / 548b / 1176b |
| `Post by @milesdeutscher on X` | 2048b / 3537b |
| `Post by @aakashgupta on X` | 2584b / 3378b / 4471b |
| `Post by @chamath on X` | 3712b / 5245b |
| `Post by @svpino on X` | 2435b / 4864b |
| `Post by @Zephyr_hg on X` | 2892b / 4112b |
| `How to Build a Team of AI Agents... (Full Course)` | 14546b / 14546b (identical size — likely exact duplicate) |
| `Post by @realBigBrainAI on X` | 1910b / 4263b |
| `Post by @lennysan on X` | 1174b / 7981b |
| `Vladimir Klimontovich` | 2527b / 13009b |
| `Using Claude Code The Unreasonable Effectiveness of HTML` | 14298b / 14298b (identical — likely exact duplicate) |

**Safe-to-delete candidates**: the two 14298b/14298b identical-size pairs (`How to Build a Team...` and `Using Claude Code... HTML`) are almost certainly byte-identical duplicates.

### 3c. Large unprocessed drops worth attention (>10KB)

These have not been ingested AND are not referenced by name. Some may be already-processed (the source page just doesn't quote the raw filename). Worth scanning for genuinely-skipped high-value content:

| Size | Date | File | Likely status |
|---|---|---|---|
| 116KB | 2026-05-25 | `The Playbook for a $100M AI Agency.md` | Likely already covered by `herk-kearns-100m-ai-agency-playbook-2026-05-25` — verify and delete from _raw if so |
| 80KB | 2026-05-17 | `How this PM Used Claude Code to Support 20 People.md` | Likely Stulberg-adjacent; check vs `hannah-stulberg` / `stahlberg-team-os-aakash-2026-05` |
| 21KB | 2026-05-16 | `I Turned Claude Into My Personal CFO (step-by-step guide).md` | Already covered by `milesdeutscher-claude-personal-cfo-2026-05-14` |
| 18KB | 2026-05-25 | `You can't beat AI..md` | Already covered by `hassid-cant-beat-ai-cost-collapse-2026-05-18` |
| 17KB | 2026-05-16 | `How to Build a Team of AI Agents That Run Your Business While You Sleep — The Complete Playbook.md` | Genuinely unprocessed — Nate Herk / Custom AI Studio content adjacent to `herk-kearns-100m-ai-agency-playbook-2026-05-25` |
| 15KB | 2026-05-09 | `How to Build Your First AI Agent That Companies Will Pay $10K+ For (Full Course).md` | Genuinely unprocessed — practitioner-content register |
| 14KB | 2026-05-11 | `Using Claude Code The Unreasonable Effectiveness of HTML.md` | Already covered by `karpathy-html-output-taxonomy-2026-05-08` + `willison-html-effectiveness-2026-05` |
| 14KB | 2026-05-08 | `Claude Managed Agents Point to the Next AI Infra Layer Company Brain.md` | May connect to `company-brain` concept page |
| 13KB | 2026-05-17 | `The AI Career Opportunity Nobody is Talking About in 2026.md` | Genuinely unprocessed |
| 12KB | 2026-05-09 | `From Systems of Record to the Company Brain Why AI Needs Shared State, Not Just Smarter Tools.md` | Likely already covered by `company-brain` concept page |

**Net**: ~3-5 of these are genuinely-unprocessed high-value drops worth a focused triage pass. The rest are processed under a slug that doesn't match the raw filename.

---

## 4. Manifest Hygiene

`_raw/.manifest.json` tracks 77 sources; on-disk raw files = 161. **Manifest under-counts processed files by ~50%.** Causes: (a) skill-based delta tracking was not used by the project-specific ingest workflow in CLAUDE.md; (b) skill convention `_raw/articles/<slug>-<date>.md` does not match this wiki's flat `_raw/<original-filename>.md` structure.

**Recommendation**: either retire the manifest (favor the log.md-based dedup workflow per CLAUDE.md, which is what the wiki actually uses), or commit to populating it post-ingest. The current half-state produces unreliable lint signals.

---

## What I Want to Auto-Fix vs Defer

I will not auto-apply anything without your sign-off. The fixes I'd recommend, batched by risk:

**Safe + high-leverage (recommend doing)**:
- Fix the 5 slug-normalization typos in §1b (low risk, mechanical).
- Remove the wikilink form on the 2 self-deferred entities (§1a): `[[felixaix-anthropic-founders-playbook-2026-05-27]]` and the one-off `[[heeki-park]]` references (or create stubs — your call).
- Delete the 3 tiny placeholder files in §3a.
- Delete the 2 byte-identical duplicate `_raw/` pairs in §3b.

**Mid-leverage stubs (worth a "yes" or "no" each)**:
- Create stubs for `companies/box`, `companies/doordash`, `tools/bun`, `companies/cognition` (or `tools/devin`), `people/dario-amodei`. ~10-min each.

**Defer**:
- The "may-already-be-processed" `_raw/` large drops (§3c) — needs per-file verification; not a quick batch.
- Manifest hygiene — needs a decision on whether to retire it.
