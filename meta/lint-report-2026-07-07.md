---
type: meta
title: "Lint Report 2026-07-07"
created: 2026-07-07
updated: 2026-07-07
tags: [meta, lint]
status: applied
---

# Lint Report: 2026-07-07

Fresh full-vault cycle after the pt2 ingest (PR #166) and ghost-node audit (PR #167) both merged to `main`.

## Summary

- **Wrong-slug fixes from PR #167**: all 5 confirmed resolved on `main` (0 residual in content dirs) ✅
- **Orphans**: **2 found → 2 fixed** (`people/anton-leicht`, `companies/intel`)
- **Frontmatter gaps**: 0 ✅
- **Stale `last_updated` (tools/models >60d)**: **1** — `tools/claude-agent-sdk.md` (2026-05-07, 61d), newly crossed; below batch threshold, deferred
- **NEW systemic finding**: **397 path-form wikilinks** (`[[concepts/x]]`, `[[topics/x]]`, …) violating the vault's slug convention — reported, not mass-fixed (needs a decision)

## Orphans — fixed (2)

Both were caused by their **only inbound link being a path-form link**, which slug-space resolution (and Obsidian's graph, by convention) treats as not pointing at the bare-slug page:

| Orphan | Root cause | Fix |
|---|---|---|
| `people/anton-leicht` | sole inbound was `[[people/anton-leicht]]` in its source page | → `[[anton-leicht]]` |
| `companies/intel` | sole inbound was `[[companies/intel]]` in `google-intel-3m-tpus-2028-2026-06-08` | → `[[intel]]` (also fixed `[[companies/google]]` → `[[google]]` in the same list) |

Both fixes double as slug-convention corrections. Full re-scan after: **0 orphans**.

## Stale `last_updated` (1)

- `tools/claude-agent-sdk.md` — 2026-05-07 (61 days). Newly crossed the 60-day line; below the ~10-page batch-refresh threshold, so deferred per standing discipline. Only stale tool/model page in the vault.

## NEW systemic finding: path-form wikilinks (397 occurrences)

CLAUDE.md is explicit: *"Always use the slug filename … never the path-form. **Exception**: `owner/` namespace pages use path-form."* A scan of content dirs found **397 non-`owner/` path-form links** across ~50 distinct targets. They **resolve fine in Obsidian** (so not broken), but they:

1. Violate the stated convention, and
2. Can **mask orphans** — if a page's only inbound is path-form, slug-space checks (and the "compounding graph" value) miss it. That's exactly what produced today's 2 orphans.

Most-affected targets (path-form occurrence count):

| Target | Path-form refs |
|---|---|
| `concepts/loop-engineering` | 56 |
| `concepts/recursive-self-improvement` | 48 |
| `topics/ai-roi-gap` | 38 |
| `concepts/verifiability-and-jagged-intelligence` | 35 |
| `concepts/company-brain` | 25 |
| `concepts/ai-labor-market-impacts` | 22 |
| `concepts/agentic-engineering` | 20 |
| … ~43 more targets | remainder |

**Recommendation**: normalize all non-`owner/` path-form links to bare slug vault-wide (`[[concepts/loop-engineering]]` → `[[loop-engineering]]`). It's a large but zero-risk sweep (both forms resolve identically), it enforces the convention, and it closes the orphan-masking gap. **Deferred pending owner sign-off** because it's ~397 edits across many historical pages and worth a conscious yes.

## Cross-cutting health

- 0 orphans (after fix), 0 frontmatter gaps, 5/5 prior wrong-slug fixes holding.
- 1 stale date (deferred), 1 systemic path-form issue (awaiting decision).
