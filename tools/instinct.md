---
name: Instinct
type: tool
category: platform
status: emerging
last_updated: 2026-10-10
---

## What It Is

A **personal AI agent that runs inside iMessage**, built by a company whose founder is **Remy Gaskell**. Instead of an app or a chat surface of its own, it occupies a thread in a messaging client the user already reads, and executes real-world errands from there: booking haircuts, making restaurant reservations, handling **visa applications**, signing up for loyalty programmes ([[isenberg-remy-gaskell-instinct-ai-2026-09-15]], 2026-09-15).

The wiki referenced Instinct four times before holding a page for it — [[guillermo-rauch|Rauch]] names it as an exemplar agent, [[greg-isenberg|Isenberg]] names it as the exemplar *incomplete* agent. The founder interview is what finally clears the bar.

## Traction Signals

- **Named as a canonical successful agent** by [[guillermo-rauch|Guillermo Rauch]] (2026-09-23, [[rauchg-agent-anatomy-drives-2026-09-23]]) alongside **Muse, OpenClaw and Claude Code** — the reference set he uses to argue every working agent decomposes into Brain / Hands / Files.
- **Founder interview on a large operator podcast** — Remy Gaskell with Isenberg, 28 minutes, 2026-09-15.
- **Valued at "$10B" by Isenberg** (2026-09-25, [[gregisenberg-escalate-to-human-button-2026-09-25]]). **Unsourced** — an aside in a post, not a reported round. Do not repeat as a figure.

Three surfaces, two of them from the same commentator. **Real but thin**: no user counts, no revenue, no funding confirmed, and no independent evaluation.

## Update — one day later (2026-09-28)

**TechCrunch reports Instinct now has its own phone number and computer, has added AI concierge calling and friend coordination, and is facing competition from [[meta|Meta's]] Muse** ([[dailybrief-roundup-2026-09-28]], via Digg).

**Three things change here.**

**1. "Concierge calling" is not the escalation path — and the distinction matters.** [[greg-isenberg|Isenberg's]] critique is that Instinct *"never hands anything to a person."* An agent that places phone calls itself does not answer that; **it extends the agent's reach rather than adding a human.** If anything it sharpens the problem: the failure modes on this page were phone apps and complex checkout pages, i.e. surfaces the agent cannot drive. Calling routes around those by having the agent talk to a human *on the other side* — the merchant's staff absorb the work instead of the user's. **That is a real capability gain and a cost transfer, not an escalation mechanism.**

**2. "Its own phone number and computer" is the [[guillermo-rauch|Rauch]] "Mac Mini" pattern.** He named Instinct as an exemplar in the Brain/Hands/Files decomposition on 09-23 and argued against exactly this shape — one persistent stateful machine per agent. Instinct now sits with [[meta|Muse's]] per-user Linux VM on the *opposite* side of his argument from where he cited it. **Two of the four systems in his own reference set have shipped the pattern he was arguing against.** See [[loop-engineering]].

**3. Muse is now named as a direct competitor** in reporting rather than only in Isenberg's commentary. Instinct's bet was the thread, not the platform; the test is whether an iMessage-native agent holds against a platform that is simultaneously [[shopify|getting checkout access]] opened to it and opening its own connectors to developers.

**Still unanswered, and now more pressing:** the **retained-email-copies-after-disconnection** concern below. An agent that also holds a phone number and places calls on the user's behalf widens the surface, and the wiki still has no retention statement.

*(TechCrunch via an aggregator summary; no product detail, availability, pricing or limits captured. "Friend coordination" is unexplained and may or may not be the trusted-person network below.)*

## An incumbent ships the same shape (2026-09-30)

**DoorDash launched an AI food-ordering agent inside Apple Messages** — US waitlist, orders placed by text, **checkout with saved payment methods** ([[dailybrief-roundup-2026-09-30]], Digg).

**That is Instinct's product thesis, executed by a company that already owns the transaction.** Six days after this page was created on the argument that a messaging-native errand agent was a distinct bet, an incumbent shipped the messaging-native version of *its own* errand. **The difference is decisive on the exact axis this page flagged**: Instinct's stated failure modes are phone apps and complex checkout pages, and **DoorDash's agent never touches a checkout page** because it owns the checkout. Saved payment methods make the [[instinct|spend-limited virtual card]] unnecessary rather than better.

**The generalisable point is narrower than "incumbents win."** A single-vertical agent inside a messaging app has no integration problem at all; Instinct's bet is that one agent doing *many* errands beats many agents doing one each. **That bet is now testable** — and it gets harder every time a vertical incumbent ships its own thread. *(Digg summary; no detail on scale, availability or whether it uses an agent framework at all.)*

## The card networks arrive (2026-10-03)

**Visa, Mastercard and Stripe are reportedly building safeguards for AI agents that spend users' money** ([[dailybrief-roundup-2026-10-03]], Digg).

**This is the layer that resolves a question the wiki has watched four parties answer incompatibly.** In twelve days: [[meta|Amazon blocked]] Muse from shopping, Meta opened Muse's connectors, [[shopify|Shopify opened checkout]] to browser agents, and Instinct handed its agent a spend-limited virtual card. **Four positions, no shared mechanism — each party improvising a control at its own layer.**

**The card networks are the only participants who can make one control work everywhere.** Instinct's virtual card is a good answer that only Instinct's users get; a network-level safeguard applies to every agent, every merchant and every wallet at once. **If this ships, the spend-limited card stops being Instinct's differentiator and becomes a primitive** — which is good for users and removes the most concrete thing this page credits the product with.

**The open question is which control they build**, and the three candidates behave very differently: a **per-transaction limit** (what Instinct does), **agent identity and attestation** (the merchant knows a bot is paying, and can price or refuse it), or **reversibility** (agent-initiated charges get a longer dispute window). **The first bounds loss, the second settles the Amazon-versus-Shopify disagreement by making agent traffic identifiable, and the third shifts cost to merchants.** Nothing in the report says which.

*(Digg summary of a report; "reportedly," no mechanism, timeline, or participant confirmation. No primary.)*

## The disclosure failure, realised (2026-10-10)

**"My personal AI agent posted my bank details on company Slack"** ([[dailybrief-roundup-2026-10-10]], Business Insider) — **a Grok Bot deployment, not Instinct.** It belongs on this page anyway, because **it is this page's own named risk happening to someone else's product.**

**The page has carried two concerns since it was created**: that Instinct **retains copies of email after disconnection**, and that the agent's reach spans a user's personal accounts. **The [[grok-bot-team-own-workflow-roster-2026-08-19|Grok Bot team documented the mechanism themselves]]**: *"every bot on your account shares one computer, so same files, same sessions, same logins. **Your Expense Manager reaches everything your Talent Scout reaches.**"*

**This is that limit arriving as an incident, in public, with a named victim.** A personal agent with access to financial information and a work channel does not need to be compromised to cause harm — **it needs to be confused about which context it is in**, and the shared-substrate design means there is no boundary to be confused about.

**And it bounds the value of this page's favourite control.** Spend-limited virtual cards cap **financial loss**. They do nothing about **disclosure** — the card limit is irrelevant once the account details are in a channel. **The wiki has been recording spend caps as the cheapest good control on the agent-authority question; this is the harm class they do not touch.**

**The Business Insider framing is also worth keeping**, per the brief's read: the lesson is not *don't give agents Slack access*, it is that **the observability layer that should have caught it did not exist** — Slack caught it, after the fact, by being read by a human. → [[ai-vulnerability-discovery]]

*(Business Insider, not fetched. First-person account; no detail on how the agent obtained the details, what it was asked to do, or Grok Bot's response.)*

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
- [[dailybrief-roundup-2026-09-28]] — own phone number and computer, concierge calling, friend coordination, Muse as competitor.
