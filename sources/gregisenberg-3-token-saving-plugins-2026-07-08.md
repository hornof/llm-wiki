---
title: "Greg Isenberg — 3 Claude Code plugins to save tokens (+ token-economy discourse)"
type: source
medium: twitter-thread
url: https://x.com/gregisenberg/status/2074843642997485676
ingested: 2026-07-08
---

## Summary

[[greg-isenberg|Greg Isenberg]] (2026-07-08) shares **3 [[claude-code|Claude Code]] plugins for saving tokens** — named in-thread as **caveman**, **morph**, and **codeburn**. More interesting than the listicle is the reply-thread discourse it triggered: a genuine practitioner debate on the **token economy of long-running Claude Code sessions** and whether token-minimization trades off against output quality.

## Key Claims / Takeaways

- **3 token-saving plugins**: `caveman`, `morph`, `codeburn` (plugin specifics are from the reply thread; the main post's images/steps were not fetched — verification-pending).
- **Why it matters (Jan Stevens)**: *"Saving tokens in Claude Code sounds minor until you have it running all day and realize how much context gets burned on repeat work."* Real reported savings: PostRoutine cites *~25% token savings* on content generation with strategic plugin use.
- **The tradeoff counter-thread** (the substantive part):
  - *"saved tokens but the output felt… flatter? wondering if token efficiency trades off with response quality"* (Sanket Datta).
  - *"token-saving plugins can mask output degradation. The silent cost."* (MaatWork).
  - *"most claude code plugins net-add tokens once you factor in the tool schema loading on every request"* (Gregor) — a sharp structural point: a plugin's own tool-schema is re-sent every request, which can exceed the tokens it saves.
  - **"value per output vs cost per token"** (NetWorth Explained): *"People frantically minimizing tokens are self-sabotaging… token counters optimize cost-per-token, while top players optimize value-per-output."*
- **Adjacent tool**: `CCAUDIT` (open-source, github.com/fabio-dee/ccaudit) — audits where a Claude Code setup wastes tokens (agents/commands/MCPs loaded but never used) so you can prune them.

## Why it matters

A concrete practitioner cluster on **context/token efficiency as an operational discipline** — the cost-side companion to [[loop-engineering]]'s token-discipline checklist. The load-bearing insight is the skeptics': plugin-based token-minimization can (a) net-add tokens via per-request schema loading and (b) silently degrade output — so the right target is *value per output*, not *cost per token*. Candidate for a `context-efficiency` / token-economy concept page if a second substantive surface appears.

## Pages Updated

- [[greg-isenberg]] — added the token-saving-plugins + token-economy-discourse surface
