---
name: Herdr
type: tool
category: platform
status: emerging
last_updated: 2026-10-08
---

## What It Is

**Herdr** ([herdr.dev](https://herdr.dev/)) is **a runtime for coding agents** — a background server that owns the terminals the agents run in, so sessions outlive your attention.

> *"Herdr is the runtime your coding agents live on. It holds real terminals open on your laptop, your desktop or a box you rent, so **the work survives the lid closing** — and you can attach again from anything with a keyboard."*

**It does not wrap or replace the agents.** One binary for macOS, Linux and Windows; **22 agents detected out of the box**, including [[claude-code|Claude Code]], [[codex|Codex]], Cursor, opencode, Grok, Copilot and Hermes. *"Herdr doesn't wrap them or replace them, it just owns their terminals."*

**Paged 2026-10-08 after five independent surfaces**, having been carried as a create-candidate since July.

## Traction Signals

- **2026-10-07** — **DHH confirms daily use**: *"I use herdr yes. Prefer the terminal. And I have multiple machines. Herdr integrates everything."* ([[dhh-no-magic-sauce-harness-setup-2026-10-06]]) — the first sustained-use report from a named principal.
- **2026-07-29/30** — DHH is **wiring Herdr into Omarchy** ([[raw-batch-roundup-2026-07-30]]), alongside the Termius + Tailscale + tmux laptop-free stack.
- **2026-09-10** — surfaced as a **session-management substrate** ([[croovies-loop-orchestrator-mission-note-2026-09-10]]).
- **2026-09-13** — named as a **composition layer** in the "best multi-agent harness" thread ([[saranormous-best-multi-agent-harness-2026-09-13]]): openscout *"plays well with Herdr and **turns every harness into multi agent harnesses**."*
- **Recurring in practitioner substrate lists** — offered by commenters alongside tmux panes, [[openclaw|OpenClaw]], Hermes, Orca and Beads ([[loop-engineering]]).
- **2026-10-07** — its own landing page and docs, the primary this page is built on.

**Five surfaces, four of them independent of the vendor.** No adoption figures, no star count, no pricing, and no practitioner receipt with a number attached. **Real but unquantified.**

## Key Concepts

- **The runtime, not the app.** *"Herdr isn't an app you keep open. It's a server running in the background, and the terminals live inside it. Close the lid or drop the network and the agents keep working; **restart the machine and Herdr brings the layout back and resumes their sessions.**"*
- **Pane-state detection — working / blocked / idle.** *"Herdr reads every pane and marks each agent working, blocked or idle. When one stops and needs an answer it says so, **so you don't go pane by pane looking for whoever is waiting on you.**"*
- **Agent-native control surface.** *"The CLI and the socket API are the same surface agents drive. They split panes, start each other, prompt each other, and **wait until another agent is genuinely blocked instead of firing keystrokes and hoping.**"*
- **Multi-machine.** Laptop, desktop and rented boxes added over SSH; *"their workspaces and agents sit alongside your local ones… disconnect and they keep working."* **Herdr Cloud** announced as *"coming soon"* — SSH-free machine connection.

## What's Actually Interesting

**The blocked/idle/working detection is the contribution, and it answers a cost the wiki has recorded from two directions without a mechanism.** The [[grok-bot-team-own-workflow-roster-2026-08-19|Grok Bot operator]] *"was checking in on them every 15 minutes and micromanaging the Bots to the point where they asked me why I kept asking so many questions"*; the [[agentic-engineering|six-voice cognitive-load convergence]] reports exhaustion from *"working in five threads to keep the AI busy."* **Both are the cost of not knowing which agent needs you. Reading the panes and labelling them is the cheapest imaginable fix** — it doesn't make the agents better, it makes the supervision targeted.

**"Wait until another agent is genuinely blocked instead of firing keystrokes and hoping" is the sentence worth keeping.** Agent-to-agent coordination through a *declared* readiness signal is the legitimate version of the thing [[ai-vulnerability-discovery|Matthew Green described as an escape channel]] — agents coordinating through shared infrastructure. **The difference is that the channel is designed, typed and observable rather than improvised through a package cache.**

**Session durability is the unglamorous half and the load-bearing one.** *"Close the lid or drop the network and the agents keep working"* is the substrate the [[loop-engineering|long-horizon autonomy]] thread assumes and almost never names — and resuming the *layout* after a machine restart is more than tmux gives you. It sits in the same slot as [[undefinedki-how-to-design-an-agent-harness-2026-08-15|"what survives a crash"]], solved at the terminal layer rather than the file layer.

**It is the opposite bet from the week's other orchestration products.** [[berriai-moyai-self-hosted-coding-agent-2026-10-07|Moyai]] abstracts the harness away (six harnesses, one workspace, identical tools); `getpaseo/paseo` unifies the interface. **Herdr abstracts nothing — it owns the terminals and leaves each agent exactly as it was.** For practitioners who already have working setups, that is the lower-risk shape; it also means Herdr captures none of the routing, cost or permission control the others sell.

## Compared To

- **tmux** — the obvious baseline, and Herdr's own framing is tmux-plus: pane-state semantics, agent detection, a socket API agents can drive, and layout resumption across restarts.
- **[[berriai-moyai-self-hosted-coding-agent-2026-10-07|Moyai]]** — harness-*abstracting* rather than harness-*hosting*; Moyai runs six harnesses in one workspace, Herdr runs 22 agents in their own terminals.
- **`getpaseo/paseo`** (19.2k★) — unified interface over self-hosted agents; the closest direct peer on attention, and the wiki holds no comparison of the two.
- **openscout** — explicitly composes *with* Herdr rather than against it.

## Open Questions

- **No pricing, licence or open-source status captured.** *"One binary"* and an `install.sh` curl are all the landing page gives; whether Herdr is open source materially changes how it should be read.
- ~~**No independent practitioner receipt.**~~ **Partly answered the same day (2026-10-07)**: asked *"are you still using herdr? have you tried just running the native Claude Code or Codex apps instead?"*, DHH replied *"**I use herdr yes. Prefer the terminal. And I have multiple machines. Herdr integrates everything.**"* ([[dhh-no-magic-sauce-harness-setup-2026-10-06]]) — **sustained use by a named principal, by preference, across machines.** Still **no number**: no throughput, no comparison, no failure rate. And note the context, which matters: **DHH's whole position is that there is "no magic sauce" and the models are great out of the box — he keeps Herdr while dropping skills and custom workflows.** A skeptic retaining the substrate is a stronger signal for the substrate than an enthusiast's endorsement.
- **How does pane-state detection actually work?** Reading terminal output to classify agent state is heuristic by nature, and a false "idle" on a blocked agent is the failure that matters.
- **Herdr Cloud** — announced, unshipped, and it inverts the self-hosted premise.

## Resources

- [herdr.dev](https://herdr.dev/) — landing page and docs (primary)
- [[saranormous-best-multi-agent-harness-2026-09-13]] — Herdr as a composition layer under openscout
- [[raw-batch-roundup-2026-07-30]] — DHH wiring it into Omarchy
- [[loop-engineering]] — the substrate slot it fills; [[berriai-moyai-self-hosted-coding-agent-2026-10-07]] — the contrasting bet
