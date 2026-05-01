---
type: meta
title: "Lint Report 2026-04-30b"
created: 2026-04-30
updated: 2026-04-30
tags: [meta, lint]
---

# Lint Report: 2026-04-30b

Second lint pass of 2026-04-30, run after the batch ingest of three X posts (@heygurisingh / career-ops, @AlfieJCarter / LinkedIn stack, @Aina_Ai2 / 8 senior prompts) and creation of `tools/career-ops.md` + `tools/playwright-mcp.md`.

The morning's lint report (`lint-report-2026-04-30.md`) closed three issues (B-01 obsidian placeholders, M-01 missing claude-design page, L-01 stray cross-reference). This pass verifies they stayed closed and checks the new pages.

## Summary

- Pages scanned: 124 entity/source/topic/tutorial pages + index, log, README, CLAUDE → 128 wiki-tracked markdown files (excludes `_raw/`, `meta/`, `.obsidian/`)
- Total wikilink mentions: **850** across all pages (up from ~720 a week ago)
- Issues found: **1** (1 low/suggestion, 0 medium, 0 high, 0 blocker)
- Apr 29 subpath-wikilink fix: HELD — zero subpath wikilinks across the vault
- Apr 30 morning fixes (B-01, M-01, L-01): HELD — all three remain resolved

---

## Blockers (must fix)

_No blockers found._

---

## High (should fix)

_No high-severity issues found._

---

## Medium

_No medium-severity issues found._

---

## Low / Suggestions

### L-01 — `sources/how-to-learn-claude-infographic.md` is referenced only from `index.md` and `log.md`

- **Page**: `[[how-to-learn-claude-infographic]]`
- **Problem**: Inbound-link audit shows this source page is reached only from `index.md` (under Sources & References) and `log.md` (the ingest entry). No entity page links to it, despite the manifest declaring `tools/claude-code.md` was updated to reference it during the original 2026-04-24 ingest. Either the link was lost during a later rewrite, or it never landed.

  The page itself is a useful **April 2026 community-built map** of Claude's 9 interaction modes (Chat, Reasoning, Developer/API, Build/Artifacts, Automation/Cowork, Browser/Chrome, Coding/Claude Code, Integrations, Skills) — useful orientation material for anyone new to the surface area. Worth keeping linked from `tools/claude-code.md`.

- **Fix**: Add `[[how-to-learn-claude-infographic]]` to the Resources section of `tools/claude-code.md`. One-line restoration; no content change.

---

## Checks Completed — Clean

The following checks passed with zero findings:

| Check | Result |
|-------|--------|
| Subpath wikilinks (`[[X#Section]]`) | 0 across all 128 pages — Apr 29 fix held |
| Dead wikilinks | 0 — all 125 unique link targets resolve |
| Orphan entity pages (no inbound from anywhere) | 0 |
| Frontmatter gaps (required fields missing per schema) | 0 across tools/models/concepts/people/companies/tutorials/topics/sources/owner |
| Stale `last_updated` on tool/model pages (before 2026-03-01) | 0 |
| Stale seed pages (status:seed, not updated in 30 days) | n/a — no seed-status pages |
| Sources missing or empty Pages Updated | 0 |
| Tools missing or empty Traction Signals | 0 |
| Index drift (dead links in `index.md`) | 0 — all entries resolve |
| Empty sections (`## Heading` with no body) | 0 |
| TODO/TBD/FIXME markers in wiki pages | 0 (excluding CLAUDE.md and README.md) |
| Obsidian placeholder wikilinks (B-01 from morning) | 0 — fix held |
| Tools schema completeness — career-ops, playwright-mcp | All 6 required sections present (What It Is, Traction Signals, How to Use It, Key Concepts, Compared To, Resources) |
| New source schema completeness — 3 new sources | All 3 have Summary, Key Claims/Takeaways, Pages Updated, Resources |
| Inbound coverage — 5 new pages | All 5 have ≥3 inbound links from non-index/non-log pages |

---

## Inbound Coverage on This Batch's New Pages

| New page | Real inbound (excluding self, index, log) |
|----------|-------------------------------------------|
| `tools/career-ops.md` | claude-code, agentic-engineering, writing-claude-code-skills, heygurisingh-career-ops |
| `tools/playwright-mcp.md` | career-ops, claude-code, agentic-engineering, alfiejcarter-linkedin-claude-stack, heygurisingh-career-ops, writing-claude-code-skills |
| `sources/aina-ai2-eight-senior-prompts.md` | claude-code, alfiejcarter-linkedin-claude-stack, heygurisingh-career-ops, writing-claude-code-skills |
| `sources/alfiejcarter-linkedin-claude-stack.md` | playwright-mcp, claude-code, career-ops, writing-claude-code-skills, heygurisingh-career-ops |
| `sources/heygurisingh-career-ops.md` | career-ops, claude-code, playwright-mcp, agentic-engineering, alfiejcarter-linkedin-claude-stack, writing-claude-code-skills, aina-ai2-eight-senior-prompts |

All five pages are well-anchored in the graph. None are orphan-prone.

---

## Style Spot-Checks (no issues found)

- `tools/career-ops.md` cites the **8.2k GitHub stars** claim consistently as "at announcement, April 30 2026" / "per the post" — provenance preserved, not asserted as static fact.
- `tools/playwright-mcp.md` correctly distinguishes status `emerging` from `gaining-traction`, with explicit promotion criteria documented ("after wiki-owner builds a workflow OR third independent traction signal arrives") — guards against premature status upgrade.
- `sources/heygurisingh-career-ops.md` does **not** create a person page for `santifer` despite repeated mentions — appropriately defers, since the handle has only one mention. Matches the wiki's existing convention (cf. single-handle promo accounts not getting person pages in earlier ingests).
- `sources/aina-ai2-eight-senior-prompts.md` correctly notes the source's **Pattern #7 (multi-agent persona-prompting)** is *prompt-time* persona simulation, not Claude Code's actual sub-agent feature. Caveat callout is appropriate; cross-references the real-feature usage in `[[career-ops]]`'s `batch` mode.
- `sources/alfiejcarter-linkedin-claude-stack.md` captures the first-reply pushback from `@Prithvi_Jadwani` as a fair critique of the `profile.md`/`hooks.md` voice-scaffolding pattern, rather than uncritically promoting it. Same critique echoed in `tutorials/writing-claude-code-skills.md` Voice-Scaffolded Skills section.

---

## Recommended Fix Order

1. **L-01** (1 min) — Add `[[how-to-learn-claude-infographic]]` to the Resources section of `tools/claude-code.md`. One-line restoration.

That is the entire fix list. Wiki is in excellent health going into May 2026.

---

## Notes for Next Lint

- 124 entity/source pages and growing. Consider whether any **topic pages** would help consolidate emerging clusters:
  - "Claude Code skill stacks in production" — 4+ source pages (career-ops, alfiejcarter, julian-goldie, zodchiii) plus 1 tool page (career-ops) plus 1 tutorial (writing-claude-code-skills) all converging on the same theme. A `topics/claude-code-skill-stacks.md` page might help readers navigate the cluster.
  - "Claude Code MCP integrations" — playwright-mcp is the first MCP-server-specific tool page. If a second one lands (Slack MCP, GitHub MCP, etc.), a topic page or sub-index would help.
- The Apr 30 morning `tools/claude-design.md` stub (created to close M-01) is currently the thinnest tool page in the wiki — keep an eye on whether it deserves promotion or absorption into a broader `claude-creative-suite` page once the Claude Design surface is better characterized.
