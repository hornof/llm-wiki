---
title: "Raw batch roundup — 2026-10-02 (Claude Code /advisor tree; page-cloning for design references; vibe-fabricated hardware)"
type: source
medium: article
ingested: 2026-10-03
local_source: "_raw/Post by @hanakoxbt on X.md; _raw/made a chrome extension that clones any page into a working local copy....md; _raw/Post by @nikitabier on X.md"
---

## Summary

Three unrelated `_raw` drops. **The first is the most useful thing in this ingest** — a specific, copyable Claude Code configuration that puts a *different* model in the reviewer seat.

## 1. The `/advisor` tree — a different model on call (@hanakoxbt, 2026-09-20)

> *"Claude Code tip: once Opus 5.5 runs your main session, stop leaving Fable 5.1 on the bench — put it on call with `/advisor`. Run `/advisor fable`. Opus 5.5 keeps writing the code. **Fable 5.1 reads the whole session, every tool call included**, and only speaks up at three moments."*

**The three trigger points, which are the contribution:**

| When | The question it asks |
|---|---|
| **Before a plan** | *"is this the right approach?"* |
| **When the same error comes back** | *"am I digging in the wrong place?"* |
| **Before "done"** | *"what did I miss?"* |

> *"Fable 5.1 reviews. Opus 5.5 ships."*

**The full tree as posted:** Opus 5.5 on **high** runs the main session; **explorer** reads the code, **worker** edits and runs tests, **researcher** pulls the docs — *"all three on medium"*; **Fable 5.1 on call as the advisor.**

**And the layer below:** *"jev engineering is the same move one layer down: the forks that need no thinker (which file, which tool, retry or stop) go to [[jev|jev]] in under half a second, and the big model only sees the ones that split."*

The post includes a paste-ready prompt that audits `~/.claude/agents`, sets `effortLevel` and `advisorModel` in settings, **reports rather than changes** the env vars that disable the advisor (`CLAUDE_CODE_DISABLE_ADVISOR_TOOL`, `CLAUDE_CODE_EFFORT_LEVEL`), adds one `CLAUDE.md` rule, and ends *"show me every change as a diff first. No edits until I say go."* Docs: `code.claude.com/docs/en/advisor`.

### Judgment

**This is the cross-model reviewer, as a shipped product feature.** The wiki's standing position is that a judge should not be the model under test — Anthropic's own eval guidance says *"you pick the judge model, and **it should not be the model you are testing**"* ([[anthropic-automating-eval-design-hillclimbing-2026-09-28]]) — and its reference example of the pattern done right was cross-vendor (*Claude implements, Codex reviews*). **`/advisor` makes that a one-line setting inside a single vendor's tool**, which removes the main practical objection: you no longer need two subscriptions and two harnesses to get an independent reader.

**The trigger design is better than "review the diff."** Reviewing output catches bad code. **These three moments catch bad *direction*** — wrong approach before the work, wrong hypothesis during a repeated failure, and premature completion. The second is the one humans reliably miss: *"when the same error comes back, am I digging in the wrong place?"* is a loop-detection trigger, not a quality check.

**Note the effort asymmetry**, which is the cost argument: main session high, three subagents medium, advisor only invoked at three points. **The expensive reader is cheap because it speaks rarely.**

*(Single practitioner post; no measurement, no before/after, no indication of how often the advisor is right. The `/advisor` feature itself is vendor-shipped and documented — that part is verifiable. Not tested by the owner.)*

## 2. Pikspec — cloning a real page so the AI has a reference (r/ClaudeDesign, 2026-10-01)

A Chrome extension that *"walks the whole thing and packs it into a zip: html, css, assets and the hover/interaction states"* — a working local copy from one click.

**The stated rationale is exactly the consensus from three days earlier**: *"when you start a new site with cursor or claude from a blank prompt, you get the same generic ai look every time. same spacing, same fonts, same cards. **if you start from a real page you like, the ai has actual layout, type scale and spacing to work from**."*

On why not DevTools or Playwright: *"you can, but this is **one click**, keeps the **computed styles and states** instead of the raw source, and needs no setup."*

The author adds the caveat himself: *"obviously don't ship someone else's site as your own. use it as a reference and starting point, then make it yours."*

### Judgment

**Three days after the wiki recorded *"feed it references"* as the top consensus method** ([[reddit-claude-beautiful-uis-vs-ai-slop-2026-09-28]]), here is a tool that does nothing but reduce the cost of that one step. **That is the pattern the wiki noted — every working method removes a degree of freedom rather than supplying taste — now with tooling built around it.**

**"Computed styles and states instead of raw source" is the technically interesting bit**: it captures what the page *resolves to*, including hover and interaction states, rather than the authored CSS. For a model that needs a concrete spacing and type scale to work from, resolved values are the useful form.

**The copyright position is the author's and it is not a defence.** *"Don't ship someone else's site as your own"* is correct advice and does not change what the tool produces, which is a working copy of a third party's design. **Recorded as a capability and a legal question, not a recommendation.** No adoption figures; one self-promoting post.

## 3. "Vibe-fabricated" hardware (@nikitabier, 2026-10-02)

> *"We are now entering into an era where any product can be created exactly to a consumer's preferences & needs. I **vibe-fabricated a dog door with a wifi-controlled lock**, perfectly to the specifications & design of my house. **I know nothing about metal fabrication or electrical engineering.** It's now getting manufactured and delivered in 2 weeks — **for almost the same cost** if I bought a mass-produced item off-the-shelf."*

### Judgment

**Recorded for the cost claim, which is the only part that would be new if true.** Bespoke manufacture at roughly mass-produced price is the assertion that matters; custom fabrication being *possible* for a non-expert is not surprising, and *"almost the same cost"* is doing all the work in that sentence. **No price, no vendor, no process, and the item has not arrived** — he says it is being manufactured, with delivery in two weeks.

**The generalisation is the author's and the wiki should not adopt it.** One dog door is not *"any product can be created exactly to a consumer's preferences."* **A door is close to the easiest possible case**: flat panels, a simple mechanism, no certification, no safety envelope, no moving load-bearing parts. The claim gets interesting at the first product where being wrong matters.

**Why it is here at all**: the wiki tracks AI's reach into physical goods thinly ([[ai-for-science]], robotics mentions), and a first-person account of a non-expert specifying a manufactured object is the kind of datapoint that becomes a pattern or doesn't. **Follow-up is the whole value** — whether the thing arrives, works, and cost what he says.

## Pages Updated

- [[claude-code]]
- [[loop-engineering]]
- [[model-rendered-ui]]
