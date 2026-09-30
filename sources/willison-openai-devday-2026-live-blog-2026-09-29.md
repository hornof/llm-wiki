---
title: "OpenAI DevDay 2026 live blog"
type: source
medium: article
url: https://simonwillison.net/2026/Sep/29/openai-devday-2026-live-blog/
published: 2026-09-29
ingested: 2026-09-30
---

## Summary

[[simon-willison|Simon Willison]] live-blogging **OpenAI DevDay 2026** from Fort Mason, timestamped through the keynote and four breakout sessions. **This is the primary** for the DevDay items the 09-29 and 09-30 briefs carried at headline depth — and it is better than the briefs in the way a firsthand account usually is: **it carries the pricing slide, and it records the demos that failed.**

Willison discloses a free ticket and a creator-area seat.

## The pricing table, read off the slide

**This closes the open item the wiki flagged on 09-29** — the uncached rate for GPT-6.1 Sol was uncaptured, and the *"fifth of the price"* claim was unverified against anything.

| | GPT-6.1 Sol | GPT-6 Astra |
|---|---|---|
| **Input** | $2.00 | $10.00 |
| **Cached input** | $0.10 | $1.00 |
| **Output** | $10.00 | $50.00 |

**Exactly one fifth on all three lines.** Not a marketing approximation — a uniform 5× cut across input, cached input and output. → [[gpt-6-astra]], [[ai-margin-collapse]]

## Key Claims / Takeaways

### The Decisions API — a direct answer to Jev, two weeks later

> **10:24** *"Also today: previewing a new **Decisions API**. Lets the model respond 'in a fraction of a second'. It works by giving the **Luna** model 'a predefined set of options to choose from'. Sounds like their response to [Jev](https://simonwillison.net/2026/Sep/21/jev/), which came out of stealth **less than two weeks ago**!"*

Willison's read, and the timeline supports it: [[jev|Jev]] launched **2026-09-15**; OpenAI previewed a constrained-choice API on **2026-09-29**. → [[jev]]

### Dots — and what powers them

- **Powered by Astra.** Willison: *"That would be an expensive default model!"* Altman calls Astra *"our most aligned model"*, to let you trust a Dot with *"as much responsibility as you are comfortable with."*
- **Available to ChatGPT Pro and Enterprise customers the same day.**
- **Dots have their own identities in OpenAI's Slack**, and staff delegate to them there. Willison: *"I guess this is OpenAI's answer to Claude Tag."*
- **Specialist dots** for legal, finance etc., built with enterprises, plus a Microsoft 365 tie-in.
- **ChatGPT Space** — shared collaborative documents with a Notion-style slash menu. *"Google Docs meets the artifacts pattern."*
- **Thibault Sottiaux on where Dots came from**: *"dots came out of the Codex harness getting more reliable and being able to handle longer tasks."*

**The live demo failed.** *"'Dottie is having a slow morning' — we got a 'still checking' and an embarrassing silent moment."* And Willison couldn't create one afterwards: the create-your-dot link returned *"Please create a dot on your computer."*

### Ultrafast, and a new plan

- **8× faster, up to 300 tokens/second**, at **6× the price** of standard. *"You know what, it's worth it,"* says Altman. Available for Astra today, Sol 6.1 soon.
- **Pro 500** — a new subscription with Ultrafast access and **25× the usage of Plus**. The $200/month plan goes back on sale for new subscribers.
- **Sottiaux's receipt for it**: Ultrafast *"made building impossible things possible"* — they used it to **merge the ChatGPT desktop and Codex desktop apps in 28 days.**

### The capability chart worth keeping

> **10:28** A chart comparing January and July 2026 agent success rates by task duration. **Success on 8–16-hour tasks with zero interventions: 10% in January → 35% in July.**

**A stated trajectory on long-horizon autonomy with a zero-intervention bar**, which is the metric that matters and the one almost nobody publishes. Vendor-reported, on OpenAI's own internal research tasks. → [[loop-engineering]]

Also from Tejal Patwardhan: *"our models helped optimize the harness we use for Computer Use"*, producing **"a 2× latency win that we've shipped to all of you"** — the model improving its own harness, which is the [[loop-engineering|harness-is-the-hero]] thesis with the loop closed.

### Codex Security Cloud — the most detailed engineering content of the day

OpenAI ran an internal security sprint with **a quarter of their product engineers**, and **fixed 53 critical findings on the first day**. They call it **The Defense Factory**. What shipped from it:

- **Five stages**: Contextualize → Scan → Enrich → Patch → Integrate.
- **A security knowledge base** with architecture details *"not visible in source code"*, plus **`SECURITY.md` files letting product owners define their own threat models** — the [[claude-md-pattern|CLAUDE.md pattern]] applied to threat modelling.
- **36% of discoveries were duplicates.** Deduplication is now a CLI workflow.
- *"They put a lot of work into figuring out who owned what — a surprisingly hard problem in a company growing at OpenAI's rate."*
- **`codex-security patch` generates patches and opens PRs, with a 1% rollback rate** — credited to a **`verify-fix` command**, which Willison describes as *"an adversarial agent against the fix."*
- The shipped flow ends with a human: **validated finding → patch → verify the attack is blocked → replay the original attack path → draft PR → human decides.**
- **The scanner loops until it finds no more issues.** CLI is open source (`openai/codex-security`); runs on the **Daybreak** security model.

→ [[ai-vulnerability-discovery]], [[loop-engineering]]

### Platform and distribution

- **Sign in with ChatGPT** — *"lets people sign into your app and use the tokens they are paying for already."* Willison: *"I've wanted this one for years!"* Altman: *"we should have done it a long time ago."* Against **1.2B weekly ChatGPT users.**
- **Plugin extensions** — plugins that are *"entire applications"* feeling native to ChatGPT and Codex.
- **OpenAI Marketplace**, launched with Adobe, Canva, Figma, Notion, Salesforce, **Vercel** and Zendesk.
- **ChatGPT Sites**: **8m sites already hosted, 70% of OpenAI employees make their own.** Now with **a SQLite database, scheduled tasks, Sign in with ChatGPT, private by default**, and **Plugins in Sites** for per-visitor personalized data. Willison notes Claude Artifacts accessing MCPs is *"the same shape of feature."*
- **WebMCP**: a session argued it is *"much more efficient than using Computer Use."* → [[mcp]]
- The **Codex harness is open source**; Codex is *"fully in the cloud"*; a new **Agents API with Computer Use**.

### The closing Q&A, which Willison found flat

*"I'll be honest, this Q&A has been pretty flat so far — the questions are such low-balls."* Three things survived it:

- **Altman**: *"I did not think we would prove a millennium prize problem within a year of the last DevDay."* Stated in passing, unexplained, and **not verified anywhere in this source.**
- **Sottiaux on decision fatigue**: *"people are hitting decision fatigue over when to use subagents, what reasoning level to make. In six months we'll get back to the simplicity of a system that actually understands what you need."* → [[loop-engineering]]
- **Patwardhan on the gap between benchmarks and reality**: models do well on benchmarks but still struggle with *"professional writing copy, not writing AI slop"*, speed, and reading context.

## Judgment

**The pricing slide is the single most useful thing here** and it is the kind of detail that only survives in a firsthand account — every secondhand version of this launch carried *"a fifth of the price"* as a claim rather than a table.

**The Decisions API is the item with the longest half-life.** OpenAI previewing a constrained-choice endpoint fourteen days after Jev's launch means the decision layer is now contested by an incumbent with distribution, and the [[jev|Jev]] page's economics arguments need re-examining against a competitor that does not need to be found.

**The Codex Security material is better engineering content than the keynote and got a fraction of the coverage.** The `verify-fix` adversarial check producing a 1% rollback rate is a concrete, checkable claim about a verifier working — exactly the kind of receipt [[loop-engineering]] wants and rarely gets. **36% duplicate findings** is the other number worth keeping: it says most of the cost of automated vulnerability discovery is triage, not discovery.

**Willison reports the failures, which is why this is the version to trust.** A failed live demo, a product he couldn't access, a flat Q&A, and a glazed-over AWS section. The briefs carried none of that.

**Everything here is a vendor's launch-day claim**, including the 10%→35% chart, the 2× Computer Use latency win, the 1% rollback rate, the 53 findings, and the millennium-prize remark. **None is independently verified**, and "available today" was not true for at least one product in Willison's own hands.

## Pages Updated

- [[openai]], [[gpt-6-astra]], [[jev]], [[ai-margin-collapse]], [[ai-vulnerability-discovery]], [[loop-engineering]], [[mcp]], [[simon-willison]]
