---
name: Instinct
type: tool
category: platform
status: emerging
last_updated: 2026-09-28
---

## What It Is

A **personal AI agent that runs inside iMessage**, built by a company whose founder is **Remy Gaskell**. Instead of an app or a chat surface of its own, it occupies a thread in a messaging client the user already reads, and executes real-world errands from there: booking haircuts, making restaurant reservations, handling **visa applications**, signing up for loyalty programmes ([[isenberg-remy-gaskell-instinct-ai-2026-09-15]], 2026-09-15).

The wiki referenced Instinct four times before holding a page for it — [[guillermo-rauch|Rauch]] names it as an exemplar agent, [[greg-isenberg|Isenberg]] names it as the exemplar *incomplete* agent. The founder interview is what finally clears the bar.

## Traction Signals

- **Named as a canonical successful agent** by [[guillermo-rauch|Guillermo Rauch]] (2026-09-23, [[rauchg-agent-anatomy-drives-2026-09-23]]) alongside **Muse, OpenClaw and Claude Code** — the reference set he uses to argue every working agent decomposes into Brain / Hands / Files.
- **Founder interview on a large operator podcast** — Remy Gaskell with Isenberg, 28 minutes, 2026-09-15.
- **Valued at "$10B" by Isenberg** (2026-09-25, [[gregisenberg-escalate-to-human-button-2026-09-25]]). **Unsourced** — an aside in a post, not a reported round. Do not repeat as a figure.

Three surfaces, two of them from the same commentator. **Real but thin**: no user counts, no revenue, no funding confirmed, and no independent evaluation.

## Key Concepts

- **Messaging-native agent** — the agent lives in iMessage rather than owning a surface. No install, no new habit; the cost is that everything the agent can do must fit a text thread.
- **Spend-limited virtual cards** — how Instinct bounds financial risk. The agent gets a card with a ceiling, not an account.
- **Trusted-person network** — the growth theory, per the episode description: users vouch for users. Framed as a potential network effect; no evidence it is operating as one.

## What's Actually Interesting

**The spend-limit mechanism is the contribution.** The wiki has tracked the agent-payment-authority question as a set of *positions* — delegate, block, supervise — without a mechanism underneath any of them. *"Give the agent a card with a ceiling, not an account"* is a boring, auditable, pre-AI answer to a problem people keep framing as novel: **the budget is the blast radius**. It bounds loss without requiring the agent to be trustworthy, which is the right shape for a control on a system whose judgment you cannot verify.

**The failure boundary is where the category actually is.** It breaks on **phone apps** and **complex checkout pages** — i.e. it works where there is a drivable web surface and a simple enough form. That is the same wall every browser-driving agent hits, and having a founder's own framing concede it is worth more than a capability list.

**The retention concern is real and unanswered.** The episode description names **copies of email retained after disconnection**. That inverts the revocation model users assume: disconnecting an integration stops future reads, it does not recall what was already taken. The wiki holds **no statement from Instinct** on retention period, deletion path, or what the copies are used for. **This is the first thing to check before recommending it to anyone.**

## Compared To

- **Muse** ([[meta|Meta]]) — the platform-scale competitor; opening connectors to third-party developers ([[isenberg-muse-ai-connectors-app-store-2026-09-25]]). Instinct's bet is the opposite: not a platform, a thread.
- **OpenClaw**, **Claude Code** — named in the same Rauch set, but those are developer-facing. Instinct is explicitly for, in the episode's framing, *"normal people."*

## Open Questions

- **Nobody operates the low-confidence branch.** [[greg-isenberg|Isenberg]] again, ten days after interviewing the founder: *"Instinct is worth $10B and it never hands anything to a person… there's the 1 thing a week that needs an actual person. Right now I'm the person."* An errand agent with no escalation path fails silently on exactly the errands that matter. See [[loop-engineering]].
- What is the retention policy on disconnected mailboxes?
- Is the trusted-person network actually gating signup, or is it aspirational?
- Company name, funding and headcount are all uncaptured — the wiki knows the product and the founder, not the entity.

## Resources

- [[isenberg-remy-gaskell-instinct-ai-2026-09-15]] — founder interview; product, virtual cards, failure modes, retention concern. **Listing depth; no transcript.**
- [[gregisenberg-escalate-to-human-button-2026-09-25]] — the missing-escalation critique and the unsourced $10B.
- [[rauchg-agent-anatomy-drives-2026-09-23]] — Instinct as an exemplar in the Brain/Hands/Files decomposition.
