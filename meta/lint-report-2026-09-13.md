---
name: Lint Report 2026-09-13
type: meta
last_updated: 2026-09-13
---

# Wiki Lint — 2026-09-13 (deep contradiction sweep)

Run on `main` at `c16ba4b` (post-#272). The structural checks are unchanged from yesterday and all pass, so this pass ran the thing that had been deferred twice: **the semantic contradiction sweep** (lint workflow step 5).

## Structural re-scan: clean

0 orphan entity pages · 0 weakly-integrated pages · 0 source pages with zero inbound · 0 dangling from entity pages · 0 frontmatter gaps · 0 pages missing from index · 0 broken index links · 0 duplicate slugs.

Remaining flagged: the 4 known rule-#3 false positives and 27 stale tool/model pages (both scoped out by the owner on 2026-09-12).

---

## F1 — Cursor and Anysphere are the same company on two pages, and they contradict each other **[material]**

The most consequential finding in three lint passes, and one that neither the slug-similarity check nor the numeric check could catch.

`companies/anysphere.md` and `companies/cursor.md` are both `type: company` for a single legal entity (Anysphere is the company, Cursor the product). They disagree about the central fact:

| Page | `last_updated` | `status:` | What it says about the SpaceX deal |
|---|---|---|---|
| `companies/anysphere` | 2026-06-16 | `acquisition-target` | **Stated as fact** — "the acquisition target of a SpaceX **$60 billion all-stock merger** projected to close in Q3 2026" |
| `companies/cursor` | **2026-07-01** | `gaining-traction` | **Stated as rumor** — "(VERIFICATION-CRITICAL)… Linas Beliūnas casual X comment-thread aside" |
| `companies/spacex` | — | — | Rumor only (2026-06-07 entry) |
| `tools/codex` | — | — | Comparison table asserts **"Acquired by SpaceX"** — past tense |

The direction matters and is the opposite of what it looks like. The **later-updated** pages are the stale ones: the 2026-06-16 Daily Brief reported the merger as an announcement and the wiki folded it into `anysphere` — but `cursor` was edited **two weeks afterwards** and still presents the deal as an unverified rumor, never mentioning the confirmation. A reader landing on `companies/cursor` learns the opposite of what the wiki knows.

`tools/codex` then overstates in the other direction: "Acquired by SpaceX," past tense, for a deal that was *projected to close*, not closed.

**Live tracking gap:** the projected close was **Q3 2026, which is now**. Nothing in the wiki records whether it closed, slipped, or collapsed.

**Possible factual error, flagged not fixed:** `anysphere.md` says *"Founded by Tomas Reimers"* — but Reimers appears on that same page launching **Origin**, a separate product, and `cursor.md` has **Michael Truell** as the Cursor principal. This looks like two same-day brief items getting conflated into one sentence. Needs a source check; I have not silently corrected it.

**Suggested fix:** merge to one canonical page (recommend `companies/anysphere` as the company, since `cursor` is the product), repoint inbound links, reconcile the deal to a single dated progression (Jun 7 rumor → Jun 16 announcement → Q3 close *unverified*), fix the `codex` table to "acquisition announced, close unconfirmed," and open a tracking note on the close.

## F2 — `hugging-face` status says `gaining-traction` for a company under a confirmed acquisition

`companies/hugging-face.md` carries `status: gaining-traction` while its own **first Traction Signal** reads *"2026-09-03: DEAL-CONFIRMED-AT-$12.9B — Nvidia confirms it will buy Hugging Face."*

`last_updated` is 2026-09-12 — I edited this page during the 09-13 ingest and walked straight past the frontmatter. Same class of defect as the `claude-mythos` naming contradiction found yesterday: **the body gets updated, the status field does not.**

Note the schema has no clean value here either (`acquired` is not in the allowed set) — same gap flagged for `claude-mythos`. Recommend a value plus a one-line note, or a schema amendment.

## F3 — The numeric sweep came back **clean**, which is a real result

Ran cross-page extraction of every money figure tied to a tracked company and metric (valuation / raise / run-rate / acquisition), grouped by entity, and looked for disagreement.

**No genuine numeric contradictions found.** Specifically checked:

- **Anthropic run-rate**, the wiki's most-repeated and most-forked number, appears across 8+ pages and forms a coherent dated progression: $14B → $44B (2026-05-09) → $47B (2026-05-29) → $65B (2026-08-17). No page asserts a figure out of sequence.
- **`topics/ai-50-2026-snapshot`** carries April figures ($380B Anthropic valuation, $30B run-rate) that are far behind current numbers — but the page is titled *Snapshot*, dated `2026-04-29`, and opens by naming its source and date. **Correctly framed, not a contradiction.**
- **Hugging Face $13B → $12.9B** is handled exactly as the contradiction policy requires: both figures kept, both dated, progression explained.

The dated-progression discipline is holding. That is worth recording, because it was the main thing this sweep existed to test.

## F4 — 111 entity pages carry open-question markers, and nothing retires them

Pages holding `verification-pending` / `open question` / `remains unclear` / `unconfirmed`: **111**. Oldest sits at 135 days.

Most are legitimately open (primary sources never fetched). The problem is not the count, it is that **there is no mechanism that closes one when the answer arrives**. Yesterday's `claude-mythos` case is the proof: the naming question was resolved on 2026-06-09 and the page still said *"insufficient public detail to call this yet"* three months later. F1 is the same failure at company scale.

**Suggested fix:** not a bulk sweep — add a step to the ingest workflow that greps the touched entity pages for open-question markers and closes any the new source answers.

## F5 — Carry-over, unchanged

27 stale tool/model pages >60 days (owner scope: refresh only on resurfacing). Lint rule #3 remains too strict for image-only and cross-reference-roundup sources — 4 of the flagged 8 are rule artifacts; recommend relaxing the rule rather than editing the pages.

---

## Ingest note (not a lint item)

`_raw/Post by @saranormous on X.md` (2026-09-13) is unprocessed — Sarah Guo asking *"best multi agent harness outside of the labs?"*, replies naming AmpCode, Cognition, Devin, openscout, Herdr. **`people/sarah-guo` already exists** (last_updated 2026-06-14), and the post is a direct market-read on the [[domain-specific-harness]] thread. Worth taking on the next ingest.

## Suggested order

1. **F1** — the only material correctness defect; a reader currently gets the wrong answer.
2. **F2** — one-line fix, same class, trivial.
3. **F4** — process change, prevents both from recurring.
4. **F5** — relax lint rule #3 (tooling, not content).
