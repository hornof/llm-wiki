---
title: Learning on the Shop floor (Tobi Lütke on River)
type: source
medium: article
url: https://simonwillison.net/2026/May/11/learning-on-the-shop-floor/
ingested: 2026-05-11
---

## Summary

[[simon-willison]] post (May 11 2026) surfacing [[tobi-lutke]]'s ([[shopify]] CEO) public description of **[[river]]**, Shopify's internal AI coding agent. The defining design choice: River **refuses direct messages** and forces all work into **public Slack channels** by default. Lütke frames this as governance-by-transparency rather than governance-by-permission — every agent interaction becomes auditable and learnable for the rest of the company.

## Key Claims / Takeaways

- **Default-public, not default-private**: River will not engage in DMs. The constraint is a workflow primitive, not a policy bolt-on. Lütke's framing is that you cannot have agent-mediated work scale without organization-wide visibility into what the agents are doing and why.
- **Auditability as a primary product axis (not a compliance afterthought)**: River's transparency posture mirrors the [[verifiability-and-jagged-intelligence]] auditability discussion — once agents are doing real work, *knowing what they did and why* becomes more load-bearing than the work itself.
- **Implicit critique of the agent-IDE/chat-window paradigm**: most agent-coding tooling ([[claude-code]], Cursor, Codex) is per-developer, per-shell, per-DM. River is the first widely-discussed internal-agent example that inverts this — agent-as-shared-room-participant rather than agent-as-personal-tool.
- **Pattern naming**: Willison's title "Learning on the Shop floor" is a direct echo of [[ai-native-organizations]] arguments (cf. [[block]], [[ai-native-organizations]]) — the agent is a co-worker on a *shared* shop floor, not a tool in an individual's hand.
- **Pedagogical side effect**: forcing work to be public means every interaction with River is also a transcript that newer employees (and the rest of the org) can learn from. Lütke frames documentation/onboarding as a byproduct of the transparency constraint.

## Why This Matters for the Wiki

First wiki appearance of [[river]] as a named internal agent tool, [[shopify]] as a tracked company, and [[tobi-lutke]] as a tracked voice. River is the cleanest publicly-described existence proof to date of **agents-as-shared-channel-participants** as a deployment topology, distinct from the per-developer harness pattern. Adjacent to the [[company-brain]] thesis (every agent action becomes organizational memory by default) and the [[ai-native-organizations]] reorganization pattern.

## Pages Updated

- [[shopify]] — new company page
- [[river]] — new tool page
- [[tobi-lutke]] — new person page
- [[simon-willison]] — additional notable take added (River as agent-governance pattern)
