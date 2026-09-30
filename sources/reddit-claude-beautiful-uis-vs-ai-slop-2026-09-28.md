---
title: "How are people actually getting Claude to build beautiful UIs instead of generic AI slop?"
type: source
medium: reddit-post
url: https://www.reddit.com/r/ClaudeAI/comments/1ws9oix/how_are_people_actually_getting_claude_to_build/
published: 2026-09-28
ingested: 2026-09-30
---

## Summary

An r/ClaudeAI thread, 100+ comments, asking a question the wiki has not had a good answer for: **why does agent-built UI converge on the same look, and what do the people getting good results actually do differently?**

The original poster is precise about the failure, which is what makes the thread useful:

> *"Claude is actually pretty good at structure, UX flow, information architecture, and getting a functional dashboard together. But when it comes to the **visual layer**, everything starts looking like generic AI-generated SaaS: cards everywhere, random gradients / glows, huge border radiuses, Lucide icons everywhere, pills and badges for no reason, generic spacing… Basically AI slop."*

And explicitly rules out the answer he expects to get: *"I'm not really looking for another 'use better prompts' answer. I'm trying to understand the repeatable process behind the genuinely good results."*

## Key Claims / Takeaways

### The auto-generated consensus (subreddit bot, after 100 comments)

> **"The overwhelming consensus is that you're getting slop because you're not being a director."**

Four methods, in the order the bot ranked them:

1. **Feed it references** — *"this is the big one."* Screenshots, Figma files, or links to Dribbble / Awwwards / Mobbin. *"Tell it to replicate the style and layout, not just the content."*
2. **Use a design system** — build one with Claude first (colours, fonts, spacing) or adopt a pre-made one. *"This locks in your aesthetic and prevents the generic AI look."*
3. **`impeccable.style`** — named repeatedly, the single most-upvoted reply (94 points) is just *"give impeccable a try, it's been a game changer for me."*
4. **Iterate with a feedback loop** — *"the screenshot → critique → fix cycle is essential. Don't expect a one-shot success."*

The bot's closing line is the thread's thesis: *"Claude is an incredibly fast and capable junior developer, but it still needs a senior designer (you) to tell it what to do."*

### The loop the OP actually wants, which nobody claimed to have

> *"Claude builds the page → opens the app → looks at the actual rendered UI → realizes that an illustration/icon/banner would improve it → creates or finds the asset → places it → takes another screenshot → critiques the result → iterates until the UI actually looks polished."*

**That is a verifier loop with a taste oracle, and the thread's answer is that the oracle is still a person.** Closest reported approximation: connecting to the iOS simulator and attaching an image generator, with a custom skill for illustration assets (`santoso-git/contentcoach-skill`).

### The dissent, which is the best comment in the thread

A 13-point reply pushes back on `impeccable.style` on the grounds of its own website:

> *"IMO the Impeccable website is atrocious, so I'm not sure why anyone would want to use their tool for design. It has all the classic signs of tasteless design, it thinks more is better and is horribly busy and overdone… Just look at the hero image alone. 5 buttons, 10 icons, text all over the place."*

Then adds the part that makes it credible: *"although I find it a painful site to consume, the guy behind it seems to have some serious skill, and it's easy to crap on someone else's work from a keyboard."*

## Judgment

**The interesting finding is not the tool list — it is that the diagnosis is a taste problem being solved with process.** Every one of the four methods works by **removing a degree of freedom**: a reference constrains the target, a design system constrains the vocabulary, a screenshot loop constrains by comparison. **None of them makes the model have taste; all of them make taste unnecessary at that step.** That is the same move as constraining an agent's output with a schema rather than asking it to be careful, and it belongs with [[model-rendered-ui]].

**It also names a real limit of the verifier pattern.** [[loop-engineering]] argues the loop is only as good as the thing that can say no. **On visual quality, nobody in this thread has an automated no** — the screenshot-critique cycle still routes through a person with taste. The OP asked for the closed loop by name and the answer was, in effect, *be the loop*.

**Discount the `impeccable.style` signal accordingly.** It is a single strong recommendation with several me-toos, and the most substantive reply argues against it from its own landing page. **One tool, one thread, no evaluation.** Recorded as a name to watch, not an endorsement.

**Practitioner sentiment, self-selected, unmeasured.** No before/after anyone can inspect, no definition of "beautiful", and the OP's own premise — that the good results on X and YouTube are real — is unexamined.

## Pages Updated

- [[model-rendered-ui]]
- [[loop-engineering]]
