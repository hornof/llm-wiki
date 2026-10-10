---
title: "Raw batch roundup — 2026-10-10 (evals as the interface; Claude Dashboards/Motion reaction)"
type: source
medium: article
ingested: 2026-10-10
local_source: "_raw/Post by @jerryjliu0 on X.md; _raw/Introduction Claude Dashboards and Claude Motion.md"
---

## Summary

Two `_raw` drops, both thin. **One is a strong position stated in five sentences; the other is a clipping whose body never made it into the file.**

## 1. Evals as the interface (@jerryjliu0, 2026-10-09)

> *"These days, you can pretty much solve any task by **defining an eval and hillclimbing over it, instead of directly defining the deterministic/agentic workflow** to solve it. The data provider companies' entire job is to define evals for all economic activity to make the frontier models capable of doing anything. **Your job then becomes pointing frontier intelligence in the right direction — defining what to solve, and how to measure what good looks like.** Agent application interfaces will evolve to capture this. The most complex processes will still need some sort of explicit workflow builder interface, but **most tasks can be compressed into goals and eval instructions.**"*

### Judgment

**This is the eval-first position at its logical extreme, and it is the natural reading of [[anthropic-automating-eval-design-hillclimbing-2026-09-28|the hillclimbing tooling]]**: if `build-eval` and `hillclimb` are commands, **the eval is the program** and the workflow is a compilation artifact.

**It is also in direct conflict with the six decisions**, and the conflict is clean rather than muddy. [[undefinedki-how-to-design-an-agent-harness-2026-08-15|The harness essay]] says what matters is the stopping rule, the tool menu, memory discipline, crash survival, **permissions**, and who says it's done. **An eval expresses none of those.** The honest synthesis: **an eval can specify *what good looks like* and cannot specify *what the agent may touch*** — and the same week produced three containment products precisely because the second question does not reduce to the first.

**The replier's objection is the right one and goes unanswered**: *"depends how much you care about repeatability and consistency across repeated tasks."* **An eval passing 75% per attempt passes three consecutive runs 42% of the time.** *"Compress the task into goals and eval instructions"* is a specification without a reliability guarantee.

**Note the interest.** The author runs a data-infrastructure company, and the post's second sentence asserts that **data providers' job is "to define evals for all economic activity."** A replier confirms the alignment — *"what we do at @findatasets."* **The position is worth taking seriously and it is also the author's business model stated as a thesis.**

*(Single X post; no implementation, no measurement.)*

## 2. Claude Dashboards and Claude Motion — reaction only (r/ClaudeCode, 2026-10-09)

**The clipping captured 73 comments and no announcement.** The post body is empty in the file, so **the wiki has two product names and nothing about either** — *Dashboards* and *Motion* are inferred from the title alone.

**Recorded for the practitioner reaction, which is consistent and worth one line.** The highest-voted substantive comments are about **data access**, not capability:

> *"Hey guys, don't you mind connecting all your databases with all your precious private data to Claude, pretty please, okay, thaaanks"* (60 points) — answered with *"this 'we wont train on it we promise'"* (26 points).

And on *Motion*, a dissent from the displacement framing: *"nobody made in house custom animations for corporate presentations. **There are not many if any jobs for this kind of animation.**"*

### Judgment

**Not folded to any entity page, and the reason is the reason it is interesting.** Two products from the vendor whose agents the same week's briefs report filing visa applications and submitting false police tips — **and the top practitioner response is reluctance to connect production databases.** That is not a reaction to Dashboards; **it is the trust cost of the control story landing at the same time as the product.**

**The wiki holds nothing about what either product does.** Fetch the announcement before creating anything. *(Reddit clipping with an empty body; product names from the title, no features, pricing, availability or Anthropic framing captured.)*

## Pages Updated

- [[loop-engineering]] (the evals-as-interface position)
