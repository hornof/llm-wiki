---
name: Claude Sonnet 5
type: model
provider: Anthropic
status: available
last_updated: 2026-10-15
---

## What It Is

**Claude Sonnet 5** launched **2026-06-30** as Anthropic's **default model on the Free and Pro tiers** (also available to Max, Team and Enterprise). Anthropic's own framing is *"our most agentic Sonnet yet"*, with substantial gains over Sonnet 4.6 on reasoning, tool use, coding and knowledge work.

**The positioning claim is the one that mattered: performance close to Opus 4.8 at lower prices.** That is the first instance the wiki captured of **a Sonnet-tier model approaching the Opus tier at a Sonnet-tier cost** — a pattern that has since repeated across the whole market and now has its own page at [[ai-margin-collapse]].

**A 1M-token context window** and a **January 2026 knowledge cutoff** are both from leaked specs rather than official confirmation.

## Sonnet 5.5 (2026-09-28)

**A point release, reported at listing depth** ([[dailybrief-roundup-2026-09-28]], Digg): *"more than 30% faster than Sonnet 5 and costs up to 30% less per task in its testing, despite unchanged per-token pricing"*, with **new cyber safeguards**.

**Read the pricing claim carefully.** Per-token pricing is unchanged, so *"30% less per task"* is not a discount — **it means fewer tokens to finish the same job.** Efficiency arriving as cost reduction without a price change is a distinct lever from the [[dailybrief-roundup-2026-09-23|40–50% headline cuts of 09-22]], and it is invisible to anyone comparing rate cards. See [[ai-margin-collapse]].

**"Up to 30%" and "in its testing" are both load-bearing hedges.** This is the vendor's own measurement on an undisclosed task mix, relayed by an aggregator. No benchmark, no token counts, no task list.

**The cyber safeguards are unexplained** and land the same week the UK AI Security Institute put a number on [[gpt-6-astra|GPT-6 Astra's]] supply-chain-attack rate (29.2% of simulated trials). Whether Anthropic's safeguards are a response to a measured capability or routine release hygiene is not captured. → [[ai-vulnerability-discovery]]

**No page created for 5.5.** A point release described in one sentence does not clear the bar; it lives here until specs land. *(Note: **Claude Opus 5.5** remains a create-candidate from 09-22 for the same reason.)*

## Strengths & Weaknesses

**Strengths**, per Anthropic and early-access partners:

- **The most agentic Sonnet to that point** — it plans, uses tools (browsers and terminals are named explicitly), and runs autonomously at a level previously seen only in larger models.
- **It checks its own output without being asked.** That is **self-verification shipped as a model feature rather than built in the harness**, which is why this page is cross-referenced from [[loop-engineering]] — the verifier discipline that page argues for, implemented one layer down.
- It finishes complex tasks where previous Sonnets stopped short.
- Agentic work at an attractive price point.

**Weaknesses**: none measured. **No benchmark results against Sonnet 4.6 or Opus 4.8 were ever captured** — the entire strengths list above is vendor and partner testimony.

## When to Use It

- **As the default.** It is the default on Free and Pro, so it is the substrate most Claude users are actually on.
- **For agentic work** — planning, tool use against browsers and terminals, autonomous execution.
- **Where self-verification matters.** The built-in output-checking makes it the natural substrate for the [[loop-engineering|verifier-discipline]] patterns the wiki tracks.

## Community Sentiment

Anthropic at launch: *"our most agentic Sonnet yet"* (2026-06-30).

An early-access partner: *"finishes complex tasks where previous Sonnets stopped short, **checks its own output without being asked**, and does all its agentic work at an attractive price point."*

**Thin, and all of it from the launch window.** No independent evaluation was captured then or since.

## Compared To

- **[[claude-fable-5|Claude Fable 5]]** — the flagship tier to this model's default tier.
- **Claude Opus 4.8** — the comparison the launch positioning rested on: *close performance at lower prices.* **Never benchmarked here.**
- **[[gpt-5-6|GPT-5.6]]** — launched four days earlier (2026-06-26), making a **two-vendor frontier launch cluster inside one week.** The strategies differed: Anthropic shipped **two tiers** (default plus flagship), OpenAI **three** (Sol, Terra, Luna).

## Resources

- [[claude-sonnet-5-launch-2026-06-30]] — the launch, and the substantive source for this page
- [[claude-fable-5]], [[claude-mythos]], [[claude-opus-5-5]] — the rest of the family
- [[gpt-5-6]] — the same-week competing launch
- [[anthropic]] · [[claude-code]] · [[loop-engineering]]

## Verification-pending

- **Pricing** — per-token input and output rates, introductory and post-2026-08-31.
- **Benchmarks against Sonnet 4.6 and Opus 4.8.** The page's central positioning claim has never been checked.
- **The 1M context window and January 2026 cutoff** are leaked, not confirmed.
- **How the self-verification works** — built into the model, or prompted by the harness? This is the most interesting open question here, because the answer decides whether it belongs on [[loop-engineering]] as a model property or a harness one.
- Early-access partner roster.

> [!note] Rewritten 2026-10-15
> The 2026-09-28 version carried **28 instances of `canonical-` filler** from an automated pass. Content preserved, prose rewritten; one path-form wikilink (`[[concepts/loop-engineering]]`) corrected to slug-form. See lint rule 7.
