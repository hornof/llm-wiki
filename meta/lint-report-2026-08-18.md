---
type: meta
title: "Lint Report 2026-08-18"
created: 2026-08-18
updated: 2026-08-18
tags: [meta, lint]
status: applied
---

# Lint Report: 2026-08-18

Full health-check covering the three ingests since the 08-13 lint — **#246** (08-16: multi-agent failure-modes / Grok CSAM / Willison local-inference / watermark), **#247** (08-17: Anthropic $65B / Stripe-OpenRouter / Amazon rare-books / Copilot-Autofix), **#248** (08-18: OpenAI 14 policy projects / DumpsterCluster). **3 link fixes + 2 tool web-refreshes + 2 freshness-bumps applied.**

## Results

| Check | Result |
|---|---|
| Orphan entity pages | **0** |
| Stale tool/model pages (>60d) | **4 → 0** (2 web-refreshed, 2 bumped) |
| Tools missing a Traction Signals section | **0** |
| `sources/` missing a `Pages Updated` section | **7** (all May; left by owner decision) |
| New ghost links from delta ingest pages (#246–248) | **0** |
| Pre-existing broken links (genuine slug-typos) | **3 fixed** |
| Dangling refs total (non-meta) | **313 — ~210 flagged "entity-page candidate," ~5 backtick examples, rest one-off mentions; left by design** |

Corpus: 275 entity pages / 506 sources / 67 meta.

## Fixes applied

**Link fixes (3 genuine slug-typos, all pre-existing):**
1. `sources/0xcodez-14-step-loop-engineering-roadmap-2026-06-20` — `[[0xcodez-fault-5-…]]` → `[[0xcodez-fable-5-…]]` (2×; "fault" was a typo for "fable"; target page exists).
2. `sources/dailybrief-roundup-2026-06-17` — `[[bezos-prometheus-physical-age-2026-06-11]]` → `[[prometheus-12b-41b-bezos-physical-age-2026-06-11]]` (slug drift; target exists, same event).
3. `sources/dailybrief-roundup-2026-06-20` — `[[cognition-ai]]` → `[[cognition]]` (2×; the entity has a page, was flagged a "candidate" in error).

**Tool web-refreshes (stale active products, per convention #240 → refresh-active-from-web):**
4. `tools/openclaw` — refreshed from web. **Status gaining-traction → mainstream.** Added: ~347K GitHub stars (most-starred repo in history, Apr 2026); Steinberger joined OpenAI (Feb 16) while OpenClaw transitions to an independent OpenAI-backed foundation (stays open); production-grade security for Fortune 500 (ClawKeeper / threat-model arXiv papers); personal-agents-via-iMessage/WhatsApp positioning. Date → 2026-08-18.
5. `tools/codex` — refreshed from web. **Status gaining-traction → mainstream**, category ide-extension → cli. Added: default → gpt-5.6-sol (post GPT-5.6 GA 2026-07-09; 88.8% Terminal-Bench 2.1 / 64.6% SWE-Bench Pro); Linux desktop preview; `/import` from Claude Code + Cursor (switching-cost attack); plugin support; `--approve-for-me` flag. Date → 2026-08-18.

**Freshness bumps (date-only, per owner decision):**
6. `tools/goose` — last_updated → 2026-08-18 (content current).
7. `tools/ona` — last_updated → 2026-08-18 (content current).

## Left by design / deferred

- **7 `sources/` missing `Pages Updated`** (all May 2026: cerebras-60b-ipo, dailybrief-mixed-2026-05-16-to-18, 3× research-roundups, fastcompany-amazon-workers-ai-task-faking, tanstack-npm-supply-chain) — **owner chose to defer**; historical pages, low value to reconstruct now.
- **~310 dangling wikilinks** — overwhelmingly intentional: `- [[x]] — entity-page candidate` deferral markers (~210), backtick/example refs, and one-off entity mentions in old roundups (poll-participant names, passing company mentions). `[[log]]` refs point to the real root `log.md` (checker false-positive). Not fixed — creating ~200 stub pages would be noise, and the candidate-marker pattern is the wiki's deliberate deferral mechanism.
- **`[[russell-kaplan]]`** (paired with the cognition-ai fix) — left as an intentional single-source-defer candidate.

## Create-candidates worth promoting (ingest-side, surfaced again this cycle)

- **`hermes-agent`** — recurs across `openclaw` + Isenberg's "pick a side" poll (now cross-source); the strongest standing candidate.
- **`opik`** — Comet's eval/observability tool (2× in the Akshay Pachaar self-repairing-harness source).
- Carry-over from recent ingests: `openrouter` (post Stripe $7B acquisition), `training-data-provenance` (Amazon rare-books), `groq` (neocloud pivot).
