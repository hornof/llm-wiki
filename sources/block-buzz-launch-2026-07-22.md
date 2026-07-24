---
title: "Jack Dorsey — 'why we're buzzing': Block open-sources Buzz, a Nostr-based workspace where agents are equal, cryptographically-identified team members (2026-07-22)"
type: source
medium: twitter-thread
url: https://x.com/jack/status/2080056638820450400
ingested: 2026-07-23
---

## Summary

[[jack-dorsey|Jack Dorsey]] announces [[block|Block]]'s **[[buzz|Buzz]]** (2026-07-22) — an **open-source (Apache-2.0), Nostr-based, self-hosted team workspace** that *"puts people, agents, conversations, and code on the same level, behind one cryptographic identity system,"* built to **reduce Block's dependency on Slack + GitHub**. The thesis: *"the biggest problem it solves is context… every seam loses information… and agents feel it the most. they can't help with what they can't see."* Extends Block's AI-native rebuild ([[goose|Goose]]) with a collaboration/identity layer.

## Key Claims / Takeaways

- **What it is**: open-source workspace on **Nostr**; everything is a **signed event on a self-hosted relay** — *"every message, patch, review, workflow step, and approval. one record, one search."*
- **Agent-as-equal-member**: people and agents get the *same* identity — *"their own keys, channels, and an audit trail. an agent on buzz is an equal member of the team"* — able to search history, open repos, send patches, review code, run workflows, edit canvases; *"everything it does is signed and attributable, which builds trust and accountability."*
- **Three principles**: (1) **self-sovereign** — run your own relay, own your domain/data/keys; (2) **open** — Apache-2.0, built on Nostr, model-agnostic, harnesses for **[[goose|Goose]] / [[codex|Codex]] / [[claude-code|Claude Code]]**, *"no lock-in, including to us"*; (3) **one context** — *"a feature branch becomes a channel"*; patches, CI, review, and the merge decision live in the same thread as the conversation — *"code review becomes a conversation with a permanent record."*
- **Block context**: *"block is rebuilding itself to be an intelligence. goose… works across the company every day, and the deeper we go the more the seams between tools become the limit."*
- **Status**: early — channels/threads/DMs/canvases/media/search/audit-log/workflows/desktop work today; git hosting being wired; mobile/push/approval-gates partial; **federation between relays** = the path to full decentralization.
- **Next**: tighter agent scoping (private-within-workspace), a hosted option, token efficiency, an ecosystem of workflows/agents — and *"agents that can transact feels like a natural place… next."*

## Why it matters

- **The open, cryptographic answer to agent-governance-by-transparency**: where [[river|Shopify's River]] gates agents by *audience* (public Slack channels), Buzz gates by **signed attribution + audit trail** — every agent action is keyed and accountable. Two instantiations of the [[ai-native-organizations|AI-native-org]] transparency substrate.
- **"One context" = context engineering at the org layer**: attacks the seam-loses-information problem directly — the [[context-engineering]] / [[company-brain]] thesis applied to the whole collaboration stack, with agents as first-class citizens.
- **Block's 2nd open-source agent-infra bet**: Goose (substrate) + Buzz (workspace/identity) — a coherent open stack for the [[ai-native-organizations|AI-native org]].

## Pages Updated
- [[buzz]] (new), [[block]], [[jack-dorsey]]
