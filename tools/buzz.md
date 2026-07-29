---
name: Buzz
type: tool
category: platform
status: emerging
last_updated: 2026-07-28
---

## What It Is

**Buzz** (by **[[block|Block]]**, announced by [[jack-dorsey|Jack Dorsey]] 2026-07-22) is an **open-source (Apache-2.0) team workspace** that puts *"people, agents, conversations, and code on the same level, behind one cryptographic identity system."* Built on **Nostr**, model-agnostic, and **self-hosted** (you run your own relay), it's Block's attempt to **reduce dependency on Slack + GitHub** by collapsing chat, code, CI, review, and agent tools into one signed, searchable event log. Block's 2nd major open-source agent-infra release after [[goose|Goose]]. See [[block-buzz-launch-2026-07-22]].

## Traction Signals

- **2026-07-22 launch** via Jack Dorsey ([[block-buzz-launch-2026-07-22]]); Apache-2.0, on GitHub (`block/buzz`), *"AI Score 9/10"* in the [[dailybrief-roundup-2026-07-21|07-21 brief]] repo-watch.
- **Dogfooded inside Block's AI-native rebuild** — *"block is rebuilding itself to be an intelligence"*; Goose *"works across the company every day,"* and buzz targets the *"seams between tools"* that limit it.
- **[unsourced beyond the launch]** — no external adoption metrics yet; explicitly early (git hosting being wired; mobile/push/approval-gates partial).
- **2026-07-24/26 practitioner amplification** ([[graph-engineering-cluster-2026-07-26]]): @hot_town's hands-on review (*"Slack + OpenClaw + Herdr"* — agents as first-class citizens on **any** harness, choose models incl. local, agents delegate + run parallel in git worktrees) and [[greg-isenberg]]'s **shared-compute** thread. Early-adopter interest, still pre-metrics.
- **38-min hands-on walkthrough** ([[greg-isenberg]], 2026-07-28, [[dailybrief-roundup-2026-07-29]]): a full setup/use-case tour — swap the model under any agent *while keeping all context*, **live audio "huddles"** with agents, *"get agents to build and deploy a real app (a full CRM) from one ask,"* a **context loop** feeding live app data back to the agents, and community **shared compute**. Deepest practitioner how-to captured; still framed as early ("who it's for right now, and what's still" rough).
- **"First proper multiplayer agent harness" framing** (@jtwald, 2026-07-25, [[dailybrief-roundup-2026-07-27]]): *"Buzz is not a slack killer. It's much bigger. It's the first proper multiplayer agent harness. The network effects of who wins at that layer will decide where value accrues as models commoditize."* Reframes Buzz from a Slack competitor to a **new infrastructure layer** — the wiki's harness→loop→graph ladder ([[graph-engineering]]) applied at the *multiplayer/org* scale. Reply-thread receipts: Larry Velez (*"needed a bridge between two sets of agents and buzz may be it"*), @0xGuavaGuy (daily use since launch, forked to add agent-thread visibility). Sharpest pushback: *"why would a general harness win over a specific harness the company builds itself?"*

## Key Concepts

- **Agent-as-equal-member**: *"an agent on buzz is an equal member of the team"* — agents get their own **keys, channels, and audit trail** (same identity model as people), and can search history, open repos, send patches, review code, run workflows, edit canvases. Everything is **signed + attributable**. The *open, cryptographic* counterpart to [[river|Shopify's River]] (agent-as-shared-Slack-participant) — governance by **attribution + audit** rather than audience.
- **One context**: *"a feature branch becomes a channel"* — patches, CI results, review, and the merge decision live in the same thread as the conversation that shaped them. Directly attacks the [[context-engineering|context]] problem: *"every seam loses information… and agents feel it the most. they can't help with what they can't see."*
- **Self-sovereign / signed-event log**: everything stored as a **signed event on a relay you host** (message, patch, review, workflow step, approval) — *"one record, one search."* Federation between relays is the stated path to decentralization.
- **Why Nostr** (per @hot_town's explainer, 2026-07-24, [[dailybrief-roundup-2026-07-28]]): every Buzz object is *"just a simple Nostr event — id, timestamp, kind, tags, content, signature"*; you sign it and push to **relays** (plain servers anyone can run — Buzz spins one up on startup, or self-host). *"The events are the source of truth, not any one app's database,"* which is what lets anyone follow/build on them (person, agent, or bot) and is the technical reason Buzz can do things *"closed platforms can't."*
- **Harnesses**: ships integrations for **[[goose|Goose]], [[codex|Codex]], and [[claude-code|Claude Code]]** — model/harness-agnostic, *"no lock-in, including to us."*
- **Shared compute** (per [[greg-isenberg]], [[graph-engineering-cluster-2026-07-26]]): the under-discussed Buzz idea — one person runs the machine and loads an open model (e.g. Gemma), and the whole community shares that compute. Framed as the fix for "the strongest open models need hardware most people won't buy alone, and it's a pain to set up if you're not technical."

## Compared To

- **[[goose|Goose]]** — Block's agent *substrate* (the harness); buzz is the *workspace/collaboration layer* around it. Complementary Block open-source stack.
- **[[river|River]]** (Shopify) — same *agent-as-shared-team-member + transparency* thesis, but River is internal/private-Slack-based (governance by audience); buzz is open-source, Nostr-based, cryptographic-identity (governance by signed attribution). Two takes on [[ai-native-organizations|AI-native-org]] transparency substrate.
- **Slack + GitHub** — the incumbent stack buzz explicitly aims to replace by removing the seams between them.
- **PromptQL** (Hasura / Tanmai Gopal) — competing "AI version of Slack" claim (*"$136M to kill Slack,"* 2026-07-08); a reply to @jtwald's post argued PromptQL shipped the multiplayer-agent-workspace layer weeks earlier and has been in production since March. Prior-art contender for the same "agent-collaboration layer," closed/hosted vs Buzz's open-source + cryptographic-identity model. *(Single-mention competitor claim; not independently verified.)*

## Resources
- [[block-buzz-launch-2026-07-22]] — Jack Dorsey's launch announcement (primary)
- `block/buzz` on GitHub — Apache-2.0
- [[block]] — maker; [[goose]] — sibling; [[river]] — parallel pattern
