---
type: meta
title: "Lint Report 2026-07-11"
created: 2026-07-11
updated: 2026-07-11
tags: [meta, lint]
status: clean
---

# Lint Report: 2026-07-11

Light delta cycle following the comprehensive [[lint-report-2026-07-10]]. **Clean — no fixes required.** Scope: verify the reliable direct-content checks still pass and confirm the 2026-07-11 ingest (#180) introduced no regressions.

## Results

| Check | Result |
|---|---|
| Stale tool/model pages (>60d) | **0** — the 2026-07-10 refreshes of `playwright-mcp` (62d) and `claude-opus-4-7` (61d) cleared the only two; nothing new crossed the threshold |
| Tools missing a Traction Signals section | **0** |
| `sources/` missing a `Pages Updated` section | **0** — the 2026-07-10 fix of the five June roundups held; new `dailybrief-roundup-2026-07-11` + `apple-openai-trade-secret-lawsuit-2026-07-10` are compliant |
| New ghost / broken wikilinks in pages touched by ingests #177–#180 | **0** — every wikilink in the newly-created pages resolves (authoritative per-target existence check, not `glob`) |
| Stray root files tracked | **0** — `Untitled.md` already removed in `1e40364`; no other stray root `.md` tracked |

## Ghost-node tail — unchanged

The residual tail (`tomas-reimers`, `origin`, `samueljmcd`, `rahulgs`, `sydney-runkle`, `vercel`, `amazon`, `meta-fair`, and the June-roundup people/orgs) is identical to the standing [[ghost-node-audit-2026-07-06]] and remains deferred/acceptable per the conservative entity-creation policy. The four ingests since that audit (Slate/Lieberman #177, Reflect #178, Apple/GPT-5.6 #180) introduced **no new ghost nodes** — new person mentions were left as plain text where a page was deferred (e.g. `mira-murati` in the 07-11 roundup).

Note: `[[agi-debate.canvas]]` (index.md) and `[[Daily Briefs/2026-06-0X.md]]` (June roundups) are embed / file-path references to files that exist outside the scanned page dirs — extraction artifacts per the audit's category F, not broken links.

## Caveat carried forward

iCloud `glob` unreliability (see [[lint-report-2026-07-10]]) persists — automated graph counts can falsely flag existing pages as ghosts. All findings here were verified with per-target file-existence checks / `grep`, not raw `glob`.

## Actions

None. No fix branch opened beyond this report.
