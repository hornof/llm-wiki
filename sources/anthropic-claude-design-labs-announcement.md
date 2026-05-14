---
title: "Introducing Claude Design by Anthropic Labs"
type: source
medium: article
url: https://www.anthropic.com/news/claude-design-anthropic-labs
ingested: 2026-05-14
---

## Summary

Anthropic's official announcement of Claude Design, published April 17, 2026. Claude Design is an Anthropic Labs research preview available at claude.ai/design — a two-panel workspace (chat left, canvas right) powered by Claude Opus 4.7 that lets users create prototypes, slides, one-pagers, and visual collateral through conversation. Available to Claude Pro, Max, Team, and Enterprise subscribers. This source resolves the product-surface ambiguity flagged in the [[nateherk-claude-design-masterclass]] stub: Claude Design is a distinct Anthropic product, not an artifact flow inside Claude.ai proper.

Note on provenance: the Anthropic blog post URL returned HTTP 403 in this session. Content is reconstructed from search-API snippets reproducing Anthropic-originated language and the official @claudeai X post (https://x.com/claudeai/status/2045156267690213649), corroborated by TechCrunch, VentureBeat, MacRumors, and Fast Company coverage all dated 2026-04-17. Claims appearing verbatim across multiple independent snippets are treated as Anthropic-originated copy. Raw drop: `_raw/anthropic-claude-design-labs-announcement.md`.

## Key Claims / Takeaways

- Claude Design is an Anthropic Labs product in research preview — distinct surface at claude.ai/design, not a flow inside the main Claude.ai chat UI
- Powered by Claude Opus 4.7 ("our most capable vision model" — @claudeai launch post)
- Two-panel interface: chat on left, canvas on right; describe → generate → refine loop
- Refinement methods: conversation, inline comments (click on canvas element for targeted change), direct edits, custom sliders (Claude auto-generates per-design sliders for micro-adjustments: spacing, radius, color temperature, etc.)
- Design system integration: during onboarding, Claude reads your codebase and design files to extract colors, typography, and components; applied to every project automatically
- Three target personas: Designers (static-to-interactive prototype without code review), Product Managers (feature flow → Claude Code handoff), Founders/AEs (rough outline → on-brand deck in minutes)
- Export options: internal URL, folder, Canva, PDF, PPTX, standalone HTML
- Claude Code handoff: export generates a "handoff bundle" — machine-readable spec containing component structure, design tokens, layout hierarchy, referenced assets, and a README with a Claude Code prompt — passed with "a single instruction"
- Mike Krieger (Anthropic) reportedly left Figma's board ahead of the launch (per @TheRundownAI; single source, not confirmed by Anthropic directly)
- Available April 17, 2026; Pro, Max, Team, Enterprise plans

## Pages Updated

- [[claude-design]] — replaced [!gap] callouts in "How to Use It" and "Key Concepts"; product surface confirmed as distinct Anthropic product; last_updated bumped to 2026-05-14
