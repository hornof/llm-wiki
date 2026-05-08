---
title: "Live blog: Code w/ Claude 2026"
type: source
medium: article
url: https://simonwillison.net/2026/May/6/code-w-claude-2026/
ingested: 2026-05-07
---

## Summary

[[simon-willison]]'s live blog of [[anthropic]]'s **Code w/ Claude 2026** event (May 6 2026). Twelve named product/feature announcements anchored around three product lines: **Claude Code** (developer CLI/agent surface), **Claude Managed Agents** (production runtime for vertical agents — first introduced in [[claude-financial-services]]), and **Claude Agent SDK** (the developer SDK powering IDE and Desktop hosts). Major model news: **Claude Opus 4.7** ships with the [[claude-design]] visual capability built in. Headline metric: **17× year-over-year API volume**.

## Key Claims / Takeaways

### Models
- **Claude Opus 4.7** — first event surface for the model name; ships with [[claude-design]] visual capability built in.
- **Claude Mythos** — preview, surfaces separately around the Mozilla/Firefox post — see [[claude-mythos]] and [[willison-firefox-claude-mythos-2026-05]].

### Claude Code (developer surface)
- **Doubled rate limits** for Pro/Max/Enterprise tiers (5-hour limit). Enabled by SpaceX Colossus partnership — see [[willison-anthropic-xai-colossus-2026-05]].
- **Code Review** — automated cross-team code review.
- **Remote Agents** — control laptop sessions from a phone.
- **CI Auto-fix** — automatic fixes against pull requests.
- **Security Reviews** — automated security review primitive inside Claude Code.
- **Claude Code Routines** — higher-order prompts for async automations and PR generation.
- **Claude Code Desktop App** — full-screen GUI with preview and rich outputs (distinct from [[claude-desktop]], which is the chat/MCP host).

### Claude Managed Agents (production runtime)
- **Multi-agent Orchestration** (public beta) — spin up agent fleets for complex tasks.
- **Outcomes** (public beta) — agents iterate toward defined success criteria.
- **Dreaming** (research preview) — agents inspect previous sessions and self-improve. *Naming/concept worth tracking — overlaps with self-improvement / continual-learning research patterns.*

### SDK
- **Claude Agent SDK** — formal SDK powering both IDE and Desktop hosts; consolidates the developer surface previously split across product-specific harnesses.

### Quotes
- **Ami Vora** (CPO, Anthropic): "Today is about how we are making our products work better for you."
- **Cat Wu** (Head of Product, Claude Code): "Thank you for trusting Claude Code on your production databases."
- **Boris Cherny** (Claude Code Creator): "Everything we are seeing today still feels magical to me."

### Metrics
- **17× year-over-year API volume**.
- **Mercado Libre** stated goal: 90% autonomous coding by Q3 2026. Bookend customer-side stake — first public customer commitment to a specific autonomy threshold the wiki has tracked.

## Pages Updated

- [[anthropic]] — Opus 4.7, Mythos preview, Multi-agent Orchestration, Outcomes, Dreaming, Code Review, Remote Agents, CI Auto-fix, Security Reviews, Routines, Agent SDK, Desktop App; Mercado Libre + 17× API growth as traction signals
- [[claude-code]] — five new feature surfaces; rate-limit doubling
- [[claude-design]] — confirmed shipping with Opus 4.7 GA
- [[claude-mythos]] — new model page
- [[claude-opus-4-7]] — new model page
- [[claude-agent-sdk]] — new tool page
- [[ami-vora]] — new person page (Anthropic CPO)
- [[cat-wu]] — new person page (Head of Product, Claude Code)
- [[boris-cherny]] — additional quote captured
- [[simon-willison]] — additional source added
