---
type: meta
date: 2026-05-09
scope: ingest/2026-05-09-daily-brief (branch unmerged, 31 files touched)
status: closed
---

# Wiki Lint Report — 2026-05-09

> **STATUS: closed** — All 4 warnings fixed in same session. S1 (mozilla light cross-ref) and S2 (jeff-kaufman thin inbound surface) deferred — low-priority, owner can decide later. S3 (3 OpenAI sources with 403'd primary) is pre-existing and well-caveat-ted; revisit on next OpenAI-fetch session.

**Fixes applied (commit on this branch):**
- W1 — `concepts/constitutional-ai.md` updated with new "Evolution: Teaching Claude Why (May 2026)" section (Difficult Advice 28× efficiency; 65→19→<1% trajectory; pairs-with-NLAs); `last_updated` → 2026-05-09; Teaching Claude Why source added under Key Papers / Posts
- W2 — `tools/playwright-mcp.md` updated with the 13.7K-token cost datapoint under Traction Signals; status promoted from `emerging` to `gaining-traction` (4th independent signal threshold crossed); `last_updated` → 2026-05-09
- W3 — `concepts/mcp.md` `last_updated` → 2026-05-09 (content was already correct)
- W4 — `tools/claude-cowork.md` `last_updated` → 2026-05-09 (content was already correct)


## Summary

- Pages scanned: 31 (3 new entity pages, 9 new source pages, 19 heavily-edited entity pages)
- Issues found: 7 (0 critical, 4 warnings, 3 suggestions)

Scope: files changed in the `ingest/2026-05-09-daily-brief` commit. Dead-link check covers all wikilinks in all 31 changed files (100+ links). Orphan check covers only today's 3 new entity pages. Stale-seed check is wiki-wide.

---

## Critical (must fix)

None.

---

## Warnings (should fix)

### W1 — Missed entity update: `constitutional-ai` not updated despite source claim

**Affected page:** [[constitutional-ai]]
**Problem:** `sources/anthropic-teaching-claude-why-2026-05-08.md` lists `constitutional-ai` under "Pages Updated" with this description: "constitutional training framework now includes the Difficult Advice + reasoning-shown methodology as an evolution beyond the original 2022 CAI methodology." No such content appears in the page; `last_updated` remains `2026-04-24`. The mechanistic-interpretability and anthropic pages were correctly updated with Teaching Claude Why content; constitutional-ai was not.
**Suggested fix:** Add a "Evolution (May 2026)" subsection under Current State: note that the 2022 CAI base was extended by the "Teaching Claude Why" methodology — Difficult Advice dataset (28× sample-efficiency), constitutional-document training with fictional aligned-AI stories (65% → 19% misalignment), and diverse environment mixing — driving Haiku 4.5 onward to 0–<1% honeypot blackmail rates. Cross-link `[[anthropic-teaching-claude-why-2026-05-08]]`. Update `last_updated` to `2026-05-09`.

---

### W2 — Missed entity update: `playwright-mcp` not updated despite source claim

**Affected page:** [[playwright-mcp]]
**Problem:** `sources/akshay-pachaar-mcp-vs-cli-2026-05-09.md` lists `playwright-mcp` under "Pages Updated" with the note "concrete token cost: 13.7K." No such content was added; `last_updated` remains `2026-05-01`.
**Suggested fix:** Add to Traction Signals: the 13.7K-token load cost is the primary practitioner data point for why "load every tool upfront" was always expensive, and why Code Mode hides it behind on-demand imports. Source: `[[akshay-pachaar-mcp-vs-cli-2026-05-09]]`. Update `last_updated` to `2026-05-09`. Separately, the four-signal threshold for `gaining-traction` has now been crossed (career-ops, LinkedIn stack, seelffff, and the akshay-pachaar token-cost data as a fifth independent reference) — consider status upgrade from `emerging` to `gaining-traction`.

---

### W3 — Stale `last_updated` on `mcp.md`

**Affected page:** [[mcp]]
**Problem:** The log entry confirms `concepts/mcp` was updated today with token-cost-of-MCP-servers data and the Code Mode reframing. The page content reflects these updates. But `last_updated` in the frontmatter still reads `2026-05-06`, not `2026-05-09`.
**Suggested fix:** Update `last_updated: 2026-05-09` in frontmatter.

---

### W4 — Stale `last_updated` on `claude-cowork.md`

**Affected page:** [[claude-cowork]]
**Problem:** The log entry confirms `claude-cowork` was updated with a Code Mode cross-reference. The Tool Priority Ladder section correctly references `[[code-mode]]`. But `last_updated` in the frontmatter reads `2026-05-08`, not `2026-05-09` (or at minimum `2026-05-09` since the edit was part of this commit).
**Suggested fix:** Update `last_updated: 2026-05-09` in frontmatter.

---

## Suggestions (worth considering)

### S1 — Light cross-refs claimed for `mozilla` and `claude-mythos` were not made

**Affected pages:** [[mozilla]], [[claude-mythos]]
**Problem:** `sources/jefftk-vulnerability-cultures-2026-05-08.md` lists both pages under "Pages Updated" as "light cross-ref." Neither page received any content: `mozilla.md` has no mention of Kaufman's essay, and `claude-mythos.md` has no mention of it. These were described as "light cross-ref" rather than substantive updates — the question is whether they matter.
**Why it matters:** The Kaufman essay's core insight (AI-assisted commit-stream analysis accelerates attacker rediscovery) is directly relevant to the Mozilla/Mythos thesis: Mozilla's 423-fixes-in-April signal is the *defender* acceleration; Kaufman's Copy Fail example is the *attacker* rediscovery acceleration. The two are the same dynamic seen from opposite sides. Having the cross-reference on the mozilla page would make the tension visible.
**Suggested fix (low priority):** Add one sentence to `mozilla.md` under "Practices Worth Tracking": note that Kaufman's essay names the disclosure-norm risk that accompanies the same acceleration — AI commit-stream analysis accelerates attacker rediscovery, not just defender throughput. Cross-link `[[jefftk-vulnerability-cultures-2026-05-08]]`.

---

### S2 — `jeff-kaufman` has thin inbound-link surface

**Affected page:** [[jeff-kaufman]]
**Problem:** `jeff-kaufman` is linked only from `index.md` and `sources/jefftk-vulnerability-cultures-2026-05-08.md`. The source is relevant to `verifiability-and-jagged-intelligence` (legibility of model behavior), `mechanistic-interpretability` (auditability), and `mozilla` (disclosure-norm risk that accompanies the Mythos fix-throughput signal). None of those pages link to the person page.
**This is not a critical orphan** (index.md counts as an inbound link under wiki convention), but the person is under-linked for the footprint of their contribution.
**Suggested fix:** After W1/S1 are resolved, the `mozilla` page will naturally carry a link to `[[jefftk-vulnerability-cultures-2026-05-08]]` but not the person page. Consider adding a "First Wiki Source" blurb to `mozilla.md` naming Kaufman as the author, which would create a second inbound path to `[[jeff-kaufman]]`.

---

### S3 — Three OpenAI sources have unverified primary claims; flag for follow-up

**Affected pages:** [[openai-testing-ads-in-chatgpt-2026-05-08]], [[openai-realtime-voice-api-2026-05-08]], [[openai-running-codex-safely-2026-05-08]]
**Problem:** All three OpenAI sources were captured from the 2026-05-09 Daily Brief synopsis only — the primary openai.com URLs returned 403 to WebFetch. Each source page carries explicit caveats: "primary article not yet ingested." This is correctly documented, but the wiki carries claims (single-pass voice architecture, four-layer sandboxing pattern, free-tier ad rollout scope) that should be verified against primary sources before external citation.
**This is pre-existing (not introduced today)** and well-caveat-ted in each source page. Surfacing it here as a reminder to re-attempt primary fetch on a future session.
**Suggested fix:** On the next ingest session, re-attempt WebFetch for these three URLs. If primary fetch succeeds, verify and update the three source pages. If 403 persists, the secondary-source-synopsis caveat is the correct stance.

---

## Structural observations (no action required)

- **No dead wikilinks** found in any of the 31 files touched today. All 100+ `[[...]]` references resolve to real files.
- **All 9 new source pages** appear in `index.md` under Recent ingests.
- **All 3 new entity pages** (`code-mode`, `akshay-pachaar`, `jeff-kaufman`) appear in `index.md` and are linked from at least one source page and/or entity page.
- **`code-mode`** has the strongest inbound-link surface of the three new entities: linked from `index.md`, `concepts/mcp.md`, `concepts/agentic-engineering.md`, `tools/claude-cowork.md`, `companies/cloudflare.md`, `people/akshay-pachaar.md`, and two source pages. Well-integrated.
- **`company-brain.md`** is 277 lines as of today — approaching the 300-line warning threshold from the 2026-05-08 report. The page is well-structured and the content is load-bearing (9-part series synthesis), so no split is recommended yet, but it will cross 300 on the next Sentra Part addition.
- **Log entry for 2026-05-09 exists** and is detailed. No action needed.
- **No seed-status pages** found across the wiki. No tool/model pages with `last_updated` before 2026-04-09.
