---
name: Buzz
type: tool
category: platform
status: emerging
last_updated: 2026-07-23
---

## What It Is

**Buzz** (by **[[block|Block]]**, announced by [[jack-dorsey|Jack Dorsey]] 2026-07-22) is an **open-source (Apache-2.0) team workspace** that puts *"people, agents, conversations, and code on the same level, behind one cryptographic identity system."* Built on **Nostr**, model-agnostic, and **self-hosted** (you run your own relay), it's Block's attempt to **reduce dependency on Slack + GitHub** by collapsing chat, code, CI, review, and agent tools into one signed, searchable event log. Block's 2nd major open-source agent-infra release after [[goose|Goose]]. See [[block-buzz-launch-2026-07-22]].

## Traction Signals

- **2026-07-22 launch** via Jack Dorsey ([[block-buzz-launch-2026-07-22]]); Apache-2.0, on GitHub (`block/buzz`), *"AI Score 9/10"* in the [[dailybrief-roundup-2026-07-21|07-21 brief]] repo-watch.
- **Dogfooded inside Block's AI-native rebuild** — *"block is rebuilding itself to be an intelligence"*; Goose *"works across the company every day,"* and buzz targets the *"seams between tools"* that limit it.
- **[unsourced beyond the launch]** — no external adoption metrics yet; explicitly early (git hosting being wired; mobile/push/approval-gates partial).

## Key Concepts

- **Agent-as-equal-member**: *"an agent on buzz is an equal member of the team"* — agents get their own **keys, channels, and audit trail** (same identity model as people), and can search history, open repos, send patches, review code, run workflows, edit canvases. Everything is **signed + attributable**. The *open, cryptographic* counterpart to [[river|Shopify's River]] (agent-as-shared-Slack-participant) — governance by **attribution + audit** rather than audience.
- **One context**: *"a feature branch becomes a channel"* — patches, CI results, review, and the merge decision live in the same thread as the conversation that shaped them. Directly attacks the [[context-engineering|context]] problem: *"every seam loses information… and agents feel it the most. they can't help with what they can't see."*
- **Self-sovereign / signed-event log**: everything stored as a **signed event on a relay you host** (message, patch, review, workflow step, approval) — *"one record, one search."* Federation between relays is the stated path to decentralization.
- **Harnesses**: ships integrations for **[[goose|Goose]], [[codex|Codex]], and [[claude-code|Claude Code]]** — model/harness-agnostic, *"no lock-in, including to us."*

## Compared To

- **[[goose|Goose]]** — Block's agent *substrate* (the harness); buzz is the *workspace/collaboration layer* around it. Complementary Block open-source stack.
- **[[river|River]]** (Shopify) — same *agent-as-shared-team-member + transparency* thesis, but River is internal/private-Slack-based (governance by audience); buzz is open-source, Nostr-based, cryptographic-identity (governance by signed attribution). Two takes on [[ai-native-organizations|AI-native-org]] transparency substrate.
- **Slack + GitHub** — the incumbent stack buzz explicitly aims to replace by removing the seams between them.

## Resources
- [[block-buzz-launch-2026-07-22]] — Jack Dorsey's launch announcement (primary)
- `block/buzz` on GitHub — Apache-2.0
- [[block]] — maker; [[goose]] — sibling; [[river]] — parallel pattern
