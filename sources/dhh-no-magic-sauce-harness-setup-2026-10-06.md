---
title: "DHH: \"There's no magic sauce\" — and dax on tinkerers falling behind the models"
type: source
medium: twitter-thread
url: https://x.com/dhh/status/2107836476780314716
published: 2026-10-06
ingested: 2026-10-08
---

## Summary

**The sharpest counter-position to the wiki's harness and skills thesis that it holds**, from a practitioner who ships, quoting a second who states it more aggressively.

> **DHH:** *"This. People keep asking me for my setup. It's really just **any harness, multiple agents concurrently, barely any skills, and using adversarial reviews**. **There's no magic sauce (or source!). The models are great out of the box.**"*

Quote-tweeting **dax (@thdxr)**, 2026-10-06:

> *"a weird inversion with LLMs is **the models improve faster than the tinkerers**. when i see people with custom workflows and setups **they're all addressing problems that don't exist anymore**. the person naively using vanilla codex is more likely to be experiencing state of the art."*

And, in reply to *"are you still using herdr? have you tried just running the native Claude Code or Codex apps instead?"*:

> **DHH:** *"I use herdr yes. Prefer the terminal. And I have multiple machines. **Herdr integrates everything.**"*

## Key Claims / Takeaways

**DHH's actual stack, as stated** — and the composition is the useful part, because it is mostly *subtraction*:

| Keeps | Drops |
|---|---|
| **Any harness** (he uses [[herdr|Herdr]], for terminals and multiple machines) | **Custom workflows** |
| **Multiple agents concurrently** | **Skills** — *"barely any"* |
| **Adversarial reviews** | **"Magic sauce"** of any kind |

## Judgment

**This is the deflationary case in its strongest form, and it is stronger than the version the wiki already holds.** [[garry-tan|Tan's]] *"a coding harness done right is syntactic sugar"* was posed by an enthusiast against himself and left unresolved. **dax's claim is sharper and falsifiable: custom setups "are all addressing problems that don't exist anymore."** That is not "harnesses add little" — it is **"harness work depreciates faster than you can do it,"** which if true makes the whole accretion thesis a treadmill.

**But read what DHH actually keeps, because it is the most useful thing here.** He drops skills and custom workflows and keeps **three** things — a terminal substrate, concurrency, and **adversarial review**. **Those are precisely the three parts of the wiki's harness record with independent evidence behind them**: session durability ([[undefinedki-how-to-design-an-agent-harness-2026-08-15|"what survives a crash"]]), parallelism (croovies, DoorDash), and a reviewer that is not the thing being reviewed ([[anthropic-automating-eval-design-hillclimbing-2026-09-28|"it should not be the model you are testing"]], the `/advisor` pattern, OpenAI's `verify-fix`). **A skeptic's minimal stack converging on exactly the components the evidence supports is a stronger endorsement of those three than any enthusiast's list.**

**So the two positions are narrower in conflict than they look.** The disagreement is not about harnesses — it is about **skills and codified workflow**, which is where [[gstack]], [[addyosmani-agent-skills-repo-2026-10-03|Osmani's 25 skills]] and the [[skill-md]] lineage live. **DHH says "barely any skills" and ships; Tan says a few hundred skill files are the labor pool.** Both report working systems. **The wiki should stop treating the skills thesis as settled and record this as an open empirical disagreement between two practitioners who both deliver.**

**And dax's claim has a specific test attached.** If custom workflows address problems that no longer exist, then **the deletion condition matters as much as the accretion rule** — which is exactly what the harness essay says (*"delete it when a better model has made it pointless"*) and what almost nobody does. **The failure mode dax describes is a rules file nobody prunes**, and the wiki's own [[claude-md-pattern|template-stack history]] is an instance of it.

**It also resolves an open question I wrote hours ago.** The new [[herdr]] page's first open question was *"no independent practitioner receipt — nobody has reported running it with a number attached."* **This is the receipt, minus the number**: DHH uses it daily, by preference, across multiple machines. **Still no measurement**, but it is a named principal confirming sustained use rather than a mention in a list.

**Caveats.** Two X posts and a reply. **No measurement of anything** — not his throughput, not the adversarial-review hit rate, not what "barely any skills" means numerically. **DHH is a well-known skeptic of industry orthodoxy by disposition**, which makes his position consistent but not independent of his priors; and *"the models are great out of the box"* is exactly what someone with a decade of Rails conventions already encoded in their repos would experience. **dax's "vanilla codex is more likely to be experiencing state of the art" is asserted with no evidence at all.**

## Pages Updated

- [[domain-specific-harness]]
- [[skill-md]]
- [[herdr]]
- [[loop-engineering]]
