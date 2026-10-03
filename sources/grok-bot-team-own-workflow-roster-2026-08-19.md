---
title: "The Grok Bot Team's Own Workflow: 11 steps to the roster they actually run"
type: source
medium: twitter-thread
url: https://x.com/0xCarnagee/status/2090102148344262659
published: 2026-08-19
ingested: 2026-10-04
---

## Summary

A long-form write-up of **the internal bot roster the Grok Bot team published on launch day** — *"the bots they actually run rather than the marketing use cases. Almost everyone skipped it and rewrote the press release instead."* Eleven steps, each attributed to a named person at SpaceXAI or Cursor. **Backfill: published 2026-08-19.**

**The four hard limits are the most valuable part, and they are the vendor's own, omitted from the announcement.**

## The four hard limits

> **No dry run.** *"A test run does real work: it navigates sites, changes files, calls connected tools. **Your first run is a live run.**"*

> **Bots are not a security boundary.** *"Every bot on your account shares one computer, so same files, same sessions, same logins. **Your Expense Manager reaches everything your Talent Scout reaches.**"*

> **Approvals prevent, they do not reverse.** *"Sensitive actions stop for you and 2FA hands back the screen, but **the session stays live afterwards for every bot you own**, and Auto Review is a model checking a model."*

> **The far end sees you.** *"The bot acts inside your session, so logs on the other side show your name. **No queryable audit log yet**, and no SOC 2, ISO 27001, GDPR or HIPAA claims in the docs today."*

## Key Claims / Takeaways

- **The bot is a file, not a chat window.** Three memory layers: **User** (name, timezone, preferences — *"shared across every bot, and any bot can update it"*), **Agent** (that bot's own profile and interaction history — *"the layer you write"*), **Project** (*"decisions and conventions that belong to the work, not to one teammate"*).
- **Chain skills instead of writing better prompts.** The receipt: *"In 15 minutes, I have a working prototype available in my Cursor app. I bind the port and play with it."* — **"one working prototype a day, and his entire input is typing 'yes'."**
- **Build the bot that watches, not the bot that answers.** The product bot is *"the slow lane: once a day it reads the big announcement channels and posts one update."*
- **Let one bot hand work to another**; point bots at *"the ugly internal tool nobody will ever integrate"* — **74 assets shipped out of a tool with no API.**
- **"The hard part is training yourself to stop checking."** *"When I first started, I was checking in on them every 15 minutes and **micromanaging the Bots to the point where they asked me why I kept asking so many questions.** Now I let it do its thing and it's just gotten better with time."*
- **"Your rules are a prompt, so write them like a contract."**

## Judgment

**Limit 2 is the same finding as [[dailybrief-roundup-2026-10-01|Matthew Green's shared-cache escape]], arriving from the vendor's own documentation seven weeks earlier.** *"Every bot on your account shares one computer, so same files, same sessions, same logins"* — **per-agent separation that is organisational, not technical.** Green's contribution was showing agents can *deliberately* exploit a shared substrate; this says a major platform ships one as the default and says so in its docs. **Two independent routes to the same conclusion: a shared mutable substrate defeats per-agent isolation, whether or not anyone is attacking it.**

**Limit 3 is the sharpest thing here, and the wiki should adopt the phrasing.** *"Approvals prevent, they do not reverse"* — and *"the session stays live afterwards"* means **the approval gates an action, not a capability.** Set against the [[undefinedki-how-to-design-an-agent-harness-2026-08-15|93% approval rate]], the picture is bleak in a specific way: **a control people click through, that only stops one action, on a session that stays open.** And *"Auto Review is a model checking a model"* is the vendor conceding the thing [[loop-engineering]] says about self-grading.

**Limit 4 names a problem the wiki has not recorded: attribution.** *"Logs on the other side show your name."* **Every agent action is indistinguishable from a human action to the counterparty** — which is the mirror of the [[shopify|agent-access]] question. Amazon blocking agents and Shopify admitting them both presume agent traffic is *identifiable*; this says that at the session layer it is not. **No queryable audit log, and no compliance certifications claimed.**

**Treat the productivity receipts as the weakest part.** *"One working prototype a day, entire input is typing yes"* and *"74 assets"* are self-reported by launch-day enthusiasts, with no quality measure, no baseline, and no definition of "prototype" or "asset." **The honest version: these are existence proofs of the workflow, not measurements of it.**

**The stop-checking finding is a real behavioural observation** and the wiki has nothing else like it — *"they asked me why I kept asking so many questions"* is a supervision cost showing up as the agent's complaint. Compare the [[agentic-engineering|cognitive-load convergence]], where the cost shows up as practitioner exhaustion.

**Secondhand throughout.** A third party's write-up of a vendor roster, quoting named people without links. No primary docs fetched.

## Pages Updated

- [[ai-vulnerability-discovery]]
- [[ai-native-organizations]]
