---
title: Our AI started a cafe in Stockholm
type: source
medium: article
url: https://simonwillison.net/2026/May/5/our-ai-started-a-cafe-in-stockholm/
ingested: 2026-05-07
---

## Summary

[[simon-willison]] post (May 5 2026) on [[andon-labs]]' second autonomous-business experiment: an AI named **Mona** runs a Stockholm cafe — inventory, ordering, supplier emails, even permit applications. The first iteration of the pattern was their AI-run retail store in San Francisco (the "Anthropic Project Vend" reference point from earlier 2026 community discussion). This post is mostly a catalog of failures, and Willison closes with a sharp consent-ethics critique: experiments become unethical when they impose burdens on third parties (police, suppliers, regulators) who never consented to participate.

## Key Claims / Takeaways

- **Failure catalog**: ordered 120 eggs despite the cafe having no stove; ordered 22.5 kg of canned tomatoes for fresh sandwiches; submitted a hallucinated street sketch to authorities for a location the agent had never seen (model generated the image itself); sent multiple "EMERGENCY" emails to suppliers about its own ordering errors.
- **Iteration on the same pattern**: Stockholm cafe is Andon Labs' v2 of "AI runs an entire commercial operation." First iteration was the SF retail store. Pattern continuing despite the obvious failure modes is the signal — they're collecting data, not running a viable business.
- **Willison's ethics critique** — the most substantive contribution: the externalities (wasted time of police, suppliers, regulators) make these experiments unethical, not just amusing. He frames this as a generalizable principle: "human oversight on every outbound action with external impact" should be a hard requirement for autonomous-business agents. Adjacent to but distinct from the standard "agent safety" framing.
- **Model used**: not specified.

## Why This Matters for the Wiki

First wiki appearance of [[andon-labs]]. Establishes the autonomous-business experimental class as a recurring pattern (not a one-off). Most useful for the wiki long-term is Willison's consent-ethics framing — distinct from the safety/alignment framing, focused on third-party-impact rather than model-internal behavior. Worth tracking as the autonomous-agent-as-economic-actor pattern matures (cf. [[cloudflare-stripe-projects-agents-2026-05]] for the protocol-side complement).

## Pages Updated

- [[andon-labs]] — new company page
- [[simon-willison]] — additional source added
