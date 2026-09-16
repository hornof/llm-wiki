---
title: "Addy Osmani — Claude writes 80% of Anthropic's code, and CI jobs are up 25×"
type: source
medium: twitter-thread
url: https://x.com/addyosmani/status/2099577600159158765
ingested: 2026-09-16
---

## Summary

[[addy-osmani|Addy Osmani]] posts **first-party Anthropic figures** on 2026-09-14, linking the company's engineering write-up on scaling test-impact analysis:

> *"At Anthropic, Claude now writes 80% of our code. Engineers ship 8x more code per quarter. Side effect: Tests grew 10x. CI jobs up 25x in 6 months."*

The generation number will get the attention. **The second-order number is the one that matters** — this is the clearest quantification the wiki holds of verification cost scaling faster than generation, and it comes from the lab with the most incentive to report the flattering figure instead.

## Key Claims / Takeaways

- **80% of code written by Claude.** Osmani defines it when challenged, which makes it usable: *"The 80% is share of lines merged to production that can be clearly attributed to Claude."* The remaining 20% is *"a mix of human written and other artifacts."* **A merged-lines attribution measure, not a keystroke or session measure** — narrower and more checkable than most such claims.
- **Engineers ship 8× more code per quarter.**
- **Tests grew 10×. CI jobs up 25× in six months.** The asymmetry is the finding: **CI load grew ~3× faster than the test count, and both grew faster than the 8× output**. Verification is not scaling linearly with generation — it is scaling *worse*, which is why the fix Anthropic reached for was test-impact analysis (run only the tests a change can affect) rather than more compute.
- Whatever else is true, **the bottleneck moved**. Anthropic's engineering effort here went into making verification affordable, not into generating more.

## Reception — worth keeping

- **Definitional pushback** (@bransburyx): *"So is 20% a mixture of human written code or human modifications to AI-generated code? I thought coding was solved?"* This drew the clarification above and is the reason the number is usable at all.
- **"LOC isn't a metric"** (@nabilblk), and *"You ship also 1000% more bugs, congratulations"* (@MadSEToday). The quality axis is **absent from the figures** — there is no defect-rate number in the post, and nobody supplied one.
- **Cost is unanswered** (@greenido): *"Any stats on the cost?"* A 25× CI increase has a bill attached and it was not disclosed.
- One practitioner notes the toolchain consequence the post skips: *"using agents for CI in large teams is impacting Dev/DevOps toolchain."*

## Pages Updated

- [[agentic-engineering]]
- [[loop-engineering]]
- [[anthropic]]
- [[addy-osmani]]

## Notes

- **First-party vendor figures about the vendor's own product**, relayed by an employee. The attribution definition is unusually specific, which helps; the **absence of any quality or cost measure** is the limit. Treat the 80% as well-defined and the *implications* as unestablished.
- The linked Anthropic engineering post (claude.com/blog, test-impact analysis) was **not fetched** — the CI mechanics are from the summary only.
