---
title: "BerriAI/moyai — a self-hosted coding agent for background work"
type: source
medium: github-repo
url: https://github.com/BerriAI/moyai
published: 2026-10-07
ingested: 2026-10-07
---

## Summary

**BerriAI** — the maker of **LiteLLM** — published **Moyai**, an open-source self-hosted coding agent for background work: *"give it a task from your browser or Slack; it edits code, runs tests, and opens a pull request for review. Send corrections while it works or resume with saved files and conversation history."*

**The notable design choice is that it is harness-agnostic by configuration**, and it ships with a cost comparison against a named competitor.

## Key Claims / Takeaways

### Six harnesses, one workspace

Sessions default to the **native Claude Agent SDK with prompt caching enabled**, and per session you can pick **Hermes, Claude Agent SDK, Codex, OpenCode, Deep Agents, or Tool Loop**.

> *"**Every harness runs in the same isolated workspace with the same tools and permissions.**"*

### 100+ providers, keys off the sandbox

Inference runs through **LiteLLM**, so *"it can run on any of the 100+ providers LiteLLM supports… switch models between messages, and **spend is tracked per teammate**."*

> *"**Provider keys stay on the server, and the sandbox never sees them.**"*

### The cost receipt

> **"Before vs after: 79% cheaper. We moved our internal coding agent from Devin to Moyai. Same work, same 31 days: $101,872 on Devin vs about $21,700 on Moyai"** — a saving of **$80,172**, shown as two billing dashboards over 2026-08-30 to 2026-09-29.

### Operational notes

Deployed on Modal; the docs warn *"deployment starts billed compute. Use a fresh Modal workspace; redeploying an existing installation interrupts its active tasks."* Separate docs for deployment, backups, security, and **access boundaries**.

## Judgment

**"Provider keys stay on the server, and the sandbox never sees them" is the line worth keeping**, and it is the [[undefinedki-how-to-design-an-agent-harness-2026-08-15|harness essay's]] credential rule implemented rather than recommended: *"never put long-lived credentials in the sandbox… if the agent can read a key, assume the key is in a context window somewhere."* **A gateway holding the keys while the agent holds only a session is the structural version of that advice** — and it is the same shape as DoorDash's single tool-granting gateway.

**Harness-agnosticism is now a product category, not a position.** The wiki recorded [[rasmic-software-factory-isenberg-2026-09-14|Ras Mic's harness-agnostic argument]] as a stance and `getpaseo/paseo` (19.2k★) as attention. **Moyai is the third surface and the most concrete: six harnesses behind one workspace with identical tools and permissions, selectable per session.** That is a bet that the harness is a swappable component rather than a lock-in point — and BerriAI, whose whole business is provider abstraction, is the natural party to make it.

**The $101,872 → $21,700 comparison is the most specific agent-cost receipt the wiki holds, and it is also the least independent.** It is a vendor comparing its own product to a competitor over a month it chose, with billing screenshots this ingest did not open. **What makes it interesting anyway is the absolute number**: an internal coding agent at **$101,872 in 31 days** is a real datapoint on what agentic coding costs at one small company's scale, and it sits beside [[uber-ai-tool-cap-1500-2026-06-03|Uber's power users at $500–2,000/month]] and [[pachaar-llm-routing-can-cost-more-2026-09-06|the executive who spent $1,200 in a two-hour session]]. **The 79% is marketing; the $101,872 is evidence.**

**One internal tension worth flagging, and it is the same week's other finding.** Moyai advertises *"switch models between messages"* — and [[pachaar-llm-routing-can-cost-more-2026-09-06|Pachaar's routing piece]] says that is exactly what destroys prefix caching inside an agent loop, at **45–80% of input-token savings**. **Moyai also defaults to a harness "with prompt caching enabled."** Those two features are in direct conflict, and nothing in the README acknowledges it. **Whether Moyai pins sessions is unanswered and is the thing to check** before treating mid-session switching as free.

*(Repo README only — not installed, not run, no independent users, no star count captured. BerriAI is LiteLLM's maker and the cost comparison is its own.)*

## Pages Updated

- [[loop-engineering]]
- [[ai-margin-collapse]]
