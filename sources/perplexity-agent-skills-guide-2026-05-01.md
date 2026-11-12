---
title: "Designing, refining, and maintaining agent skills at Perplexity"
type: source
medium: article
url: https://www.perplexity.ai/hub/blog/designing-refining-and-maintaining-agent-skills-at-perplexity
ingested: 2026-11-12
---

## Summary

[[perplexity|Perplexity]] Engineering (2026-05-01; Marshall Kiely, Daisy Lee, Jerry Ma, Lauren Kolm) publishes the internal guide its engineers use to write and review Agent Skills for Perplexity Computer. Its argument is that good code habits make bad skills: a skill is context for a model, every token in it is paid by every session, and the work is in the trigger description, the evals and the list of gotchas. It is the most practical skill-authoring document the wiki holds. Found via [[godsystemsmd-skills-are-the-prompts-2026-11-05]].

## Key Claims / Takeaways

- **Code instincts mislead.** Measured against the Zen of Python, *"Of the 20 lines of wisdom, at least half are fully wrong or actively misleading when writing Skills."* Their rewrite of one line: *"If it's easy to explain, the model already knows it. Delete it."*
- **The description is a trigger, not documentation.** *"The description is the routing trigger."* Write *"Load when..."* with a target of *"50 words or fewer"*, phrased the way users actually ask (for a PR-watching skill: *"babysit"* or *"watch CI"*).
- **Three tiers of cost.** The index of names and descriptions costs *"~100 tokens per Skill"* and is paid *"Every session, every user, always paid"*. The body should stay under 5,000 tokens (*"Ideally, the body text does not exceed 5,000 tokens"*), and *"Many threads load anywhere between three and five different Skills"*. Files in `scripts/`, `references/` and `assets/` are unbounded and cost nothing until read.
- **Hierarchy helps, and dumping hurts.** For tax work, *"presenting the model with a single folder containing all 1,945 sections of the U.S. Internal Revenue Code resulted in worse performance than not loading the Skill at all."* Three levels of nesting fixed it, at a real curation cost.
- **When not to write one:** step-by-step git commands the model already knows, repeats of the system prompt, and anything *"changing faster than you can maintain it"*. The test for every sentence: *"Would the agent get this wrong without this instruction?"*
- **Evals come first (Step 0),** drawn from real queries, known failures and "neighbor confusion" with adjacent skills. *"Negative examples are extremely powerful and can matter more than positive examples."*
- **Skills interfere with each other.** *"Every time you add an additional Skill, you risk making every other Skill slightly worse"*. Perplexity's eval suites check loading precision and recall, whether accessory files get read, and end-to-end tasks, across GPT, Claude Opus and Claude Sonnet orchestrators: *"Sonnet and GPT behave quite differently when it comes to Skills."*
- **Maintenance is a gotchas list.** *"Skills are append-mostly."* Failures add gotchas, and changing the description after merge without evals means *"you are off track"*.
- **Against generating skills with an LLM.** It quotes the [[skillsbench-arxiv-2026-02-13|SkillsBench]] paper: *"Self-generated Skills provide no benefit on average"*.
- **For the owner:** this is the one to read of the post's ten links. The sentence test and "Load when..." descriptions apply directly to the owner's own `CLAUDE.md` and skills. [Judgment.]

## Pages Updated

- [[skill-md]] — new 2026-11-12 section
- [[perplexity]] — Traction Signals, Resources
