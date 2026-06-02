---
name: Lint Report 2026-06-02
type: meta
last_updated: 2026-06-02
---

# Lint Report — 2026-06-02

**Last lint**: 2026-06-01 (1 day ago; 4 ingest sessions + 2 lint-fix PRs since: PR #65 + PR #66).
**Pages scanned**: 404 (sources 233 + tools 22 + models 4 + concepts 31 + people 53 + companies 31 + topics 5 + tutorials 2 + owner 2 + meta 15 + root 6).
**Net delta vs last lint**: +12 pages (sources +4 from PR #67; concepts +1 from autoresearch stub PR #66; root +2 from local-only `Untitled.md` files not in git).
**Pre-lint checklist**: clean — `git fetch origin` + sync confirmed; PR #67 (today's ingest) merged at 17:11 UTC and is reflected in the scan.

## Summary

The wiki continues its strong-discipline trajectory. **Real dead-link count is at an all-time low (4)**, with 2 of the 4 introduced by today's PR #67 (mechanical to fix).

| Check | Result | vs last lint |
|---|---|---|
| Stale dates | **0** | unchanged ✓ |
| Missing `last_updated` frontmatter | **0** | unchanged ✓ |
| Sources missing `## Pages Updated` section | **0** | unchanged ✓ |
| Sources with empty Pages Updated section | **7** (all explicit "no entity changes") | unchanged |
| Tools missing/thin Traction Signals | **0** | unchanged ✓ |
| Duplicate slugs across the vault | **0** | unchanged ✓ |
| Real-content orphans | **0** | unchanged ✓ |
| Real dead-link unique targets | **4** | was 3 (+1 from PR #67's net new — see §1) |

### Trajectory
- 2026-05-29 lint: 14 real dead-link targets
- 2026-06-01 initial (pre-PR-65 + PR #67 layered): 22
- Post-PR-65: 11
- Post-PR-66: 3
- **Post-PR-67 (today): 4** (+1 net from today's 4 new sources)

The +1 net dead-link drift is the lowest ingest-driven drift captured to date — ~0.25 dead links per new source page. Prior wave averaged ~1 dead link per new source. **The lint discipline is compounding favorably.**

---

## 1. Real Dead Links (4 unique targets)

### 1a. Introduced by today's PR #67 (mechanical fixes available)

| Broken link | From | Suggested fix |
|---|---|---|
| `[[sam-altman]]` | `altman-three-observations-2025-02` | Either **create `people/sam-altman.md` stub** (warranted — Altman is referenced across multiple wiki pages but has no entity page; comparable significance to [[dario-amodei]] which has a stub) or change reference to `[[openai\|Sam Altman (OpenAI CEO)]]` |
| `[[claude-obsidian:save]]` | `trq-suzanne-learn-quiz-2026-06-01` + `log` | This is a **Claude Code skill reference** (`claude-obsidian:save`), not a wiki-page slug — wikilink form is wrong. Either change to backtick code-style `` `claude-obsidian:save` `` or strip wikilink form |

### 1b. Intentionally preserved (per 2026-06-01 lint owner-judgment)

| Broken link | From | Status |
|---|---|---|
| `[[claude]]` (bare) | `log` (May 11 entry) | Append-only history; ambiguous original intent (mythos? code? cowork?) — preserved per 2026-06-01 lint decision |
| `[[claude-opus-4-6]]` | `log` (May 8 entry) | Historical reference; append-only — preserved per 2026-06-01 lint decision |

**Both append-only-log entries are stable across lints**; no action.

---

## 2. `_raw/` Hygiene

177 raw files on disk (no change from 2026-06-01 lint). +7 net-new drops during the 2026-06-02 ingest, but most have already been processed today via PR #67 (Anthropic S-1, Altman essay, Ng FDE, Thariq learn-quiz, Amy Pretzel ×2 + Tarlon SF-events skipped, low-signal-noted).

Tiny / duplicate-variant analysis unchanged from prior lint (intentional file-system state per the 2026-06-01 lint's analysis).

---

## 3. Orphans

**14 orphan pages — all in `meta/`** (same pattern as prior lints; date-indexed log entries, not content nodes). **Zero real-content orphans.**

This lint report (`meta/lint-report-2026-06-02.md`) will become the 15th orphan once committed — expected per the pattern.

---

## 4. Manifest Hygiene

Unchanged from prior lint — `_raw/.manifest.json` tracks ~43% of raw files (77 of 177). Same recommendation: retire or commit to maintaining.

---

## 5. PR #67 retrospective: low drift, fast lint-cleanup-ability

PR #67 added 4 new sources + updated 6 entity pages. Only 2 new dead links were introduced — and both are mechanical (1 missing stub; 1 wrong-wikilink-form-for-a-skill-reference). **Cleanest ingest-wave-to-lint-drift ratio captured to date.**

Pattern hypothesis: as the wiki's entity-page coverage densifies (now 53 people + 31 companies + 31 concepts + 22 tools + 5 topics + 4 models + 2 tutorials + 2 owner = 150 entity pages), new sources increasingly reference *existing* pages rather than speculative ones, which drives the drift rate down.

---

## What I Want to Auto-Fix vs Defer

I will not auto-apply anything without sign-off.

**Recommend doing (very small batch — 2 fixes)**:
- Create **`people/sam-altman.md` stub** — high-leverage; Altman is wiki-relevant across many pages (Three Observations, OpenAI references, RSI cluster, "compute budget for everyone" framing) and the absence is a structural gap given [[dario-amodei]] already has a stub for symmetry
- Fix `[[claude-obsidian:save]]` → backtick `` `claude-obsidian:save` `` in `trq-suzanne-learn-quiz-2026-06-01` (skill-reference, not wiki-page-reference; same fix in `log` if accessible)

**Defer**:
- The 2 intentionally-preserved log entries (`[[claude]]` bare, `[[claude-opus-4-6]]`) — same owner judgment as 2026-06-01 lint
- `_raw/` triage + manifest hygiene — same status as prior lint
- **Local-only `Untitled.md` files** at vault root — Obsidian-state artifacts; per CLAUDE.md ingest workflow they're excluded from commits. Owner cleanup whenever convenient.
