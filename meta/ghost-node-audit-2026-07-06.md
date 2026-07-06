---
type: meta
title: "Ghost-Node Audit 2026-07-06"
created: 2026-07-06
updated: 2026-07-06
tags: [meta, lint, ghost-nodes]
status: applied
---

# Ghost-Node Audit: 2026-07-06

First full vault-wide audit of **ghost nodes** — `[[wikilinks]]` that point to a page that does not exist. The per-cycle lint reports "0 orphans / 0 wrong-slug" because it measures *self-introduced* regressions each cycle; it never surfaced the accumulated tail. This audit separates the tail into: wrong-slug regressions (broken links to pages that DO exist), genuine missing-page candidates, and acceptable ghosts.

## Method

- Scanned every `[[link]]` in content dirs (`tools/ models/ concepts/ people/ companies/ topics/ sources/ owner/`) + `index.md` + `log.md`. Excluded `CLAUDE.md`/`README.md`/`meta/` (they quote link *examples*, not live links).
- Normalized: stripped aliases (`|`), anchors (`#`), path prefixes, escaped table-pipes (`\|`), and `.md`/`.canvas` extensions.
- Resolved each target against 701 existing page/canvas basenames.

## Results

- **14,751** wikilink occurrences scanned
- **394** distinct ghost targets — of which **203** are referenced ≥2× and **191** referenced once
- Roughly a third of the raw 394 are **extraction artifacts** (see bottom), not real issues.

---

## A. Wrong-slug regressions — FIXED this cycle (5)

Broken links whose intended page already exists under the canonical slug. All fixed in content dirs + `index.md`; historical `meta/` reports and append-only `log.md` left as-written.

| Ghost (broken) | Canonical page (exists) | Refs | Fix |
|---|---|---|---|
| `anthropic-xai-colossus-2026-05` | `willison-anthropic-xai-colossus-2026-05` | 4 | missing `willison-` prefix restored |
| `fei-fei-li-world-models-functional-taxonomy-2026-06-03` | `feifei-li-world-models-functional-taxonomy-2026-06-03` | 2 | `fei-fei` → `feifei` |
| `deepmind` | `google-deepmind` | 9 | retargeted, display `DeepMind` preserved |
| `mistral` | `mistral-ai` | 6 | retargeted, aliases preserved |
| `minchoi` | `min-choi` | 1 | retargeted, display `Min Choi` |

## B. Missing-source (recommended, NOT auto-fixed — needs judgment)

- `anthropic-bun-zig-rust-port-2026-05` (1 ref, in `samueljmcd-loop-engineering-verifier-bottleneck-2026-06-15`) — no source under that slug. The Bun Zig→Rust port content lives in `anthropic-dynamic-workflows-primary-2026-05-28` (and the `bun` tool page). **Recommend** re-pointing that link; left alone here because the intended target is inferred, not certain.

## C. Dual-slug people (defer; normalize when/if the page is created)

Same person linked under ≥2 slugs, none of which has a page yet. Not fixable until a page exists; when created, pick one slug and normalize:

- `0xMovez` / `0xmovez` / `movez`
- `rahulgs` / `rahul-gs`
- `samueljmcd` / `samuel-mcdonald`
- `hanakoxbt` / `hanako`

## D. Missing-page candidates, ranked by inbound references

Recommended for creation but **deferred** per the wiki's conservative entity-creation policy. Ordered by how many distinct pages reference them (signal strength):

**Concepts / tutorials**
- `writing-claude-code-skills` — **19 refs** (by far the strongest missing-page signal in the vault; clearly wants a concept/tutorial page)
- `personal-ai-agent-claude-desktop-mcp` — 10 refs (tutorial-shaped)
- `openai-deployment-simulation` — 5 refs
- `skill-md` — 3 refs

**Models / labs** (the open-weights ecosystem the [[ai-margin-collapse]] ingest just made newly relevant)
- `deepseek` — 9 refs
- `qwen` — 7 refs
- `moonshot-ai` — 5 refs (maker of Kimi; also `kimi-k2` / `kimi-k2-6` ghosts)
- `gemma` — 3 refs
- also single/low-ref: `minimax`, `vibe-thinker`, `llama` (→ note: `llama-index`/`ollama` exist but `llama` the model family does not)

**People** (practitioner voices, 2–3 refs each)
- `sydney-runkle`, `teknium`, `noam-shazeer`, `addy-osmani`, `eric-siu`, `xlr8harder`, `pierre-carl-langlais`, `andreas-kirsch`, `tomas-reimers`, `tibo-sottiaux`, `theker`, `lev-deviatkin`, `will-brown`, `yejin-choi`, `zico-kolter`, `weijia-shi`, `jeremy-howard`, `nabeel-qureshi`, `sebastian-raschka` …

**Companies / orgs** (2–3 refs each)
- `vercel` (3 — already a multi-cycle pattern-watch), `meta-fair`, `tsinghua-university`, `stanford-hai`, `trail-of-bits`, `epoch-ai`, `bytedance`, `amazon`, `apple`, `qualcomm`, `broadcom`, `asml`, `coinbase`, `ramp` …

## E. Acceptable ghosts (defer, no action)

The 191 single-reference targets are mostly one-off mentions of people/orgs/products that don't (yet) warrant a page. Standard wiki hygiene — leave as ghosts until a second independent signal appears.

## F. Extraction artifacts (excluded — not real issues)

Flagged by a naive sweep but not defects: escaped table-pipes (`[[claude-code\|Claude Code]]` → `claude-code\`), `.md`/`.canvas` embed refs (`[[index.md]]`, `[[agi-debate.canvas]]`), and doc/example placeholders in CLAUDE.md and the lint skill (`Page Name`, `slug`, `wikilink`, `concept`).

## Recommended next actions

1. **Create the top signal-strength pages** when ready: `writing-claude-code-skills` (19), `deepseek` (9), `qwen` (7), `moonshot-ai` (5), `personal-ai-agent-claude-desktop-mcp` (10). These are the highest-value gaps.
2. **Re-point** the `anthropic-bun-zig-rust-port-2026-05` link (item B) once the intended target is confirmed.
3. Consider adding a ghost-node sweep to the recurring lint so this tail doesn't re-accumulate silently.
