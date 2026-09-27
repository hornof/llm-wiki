---
title: "Jev as a judge — a CMU evaluation, and a community plugin with real evals"
type: source
medium: article
url: https://x.com/akshay_pachaar/status/2104214116999278874
published: 2026-09-27
ingested: 2026-09-27
---

## Summary

Two independent evaluations of [[jev|Jev]] landing the same day — the first real evidence on the model since the wiki paged it on 2026-09-20 with the warning that **calibration was the entire product and entirely unevidenced.**

A **Carnegie Mellon paper** tests Jev as an **LLM-as-judge** substitute, and **an unofficial community plugin** publishes a cross-provider eval of its own. Between them they partly validate that warning and partly answer it.

## Key Claims / Takeaways

### The CMU paper — where Jev works, and the boundary

Relayed by [[akshay-pachaar|Akshay Pachaar]]. The framing: *"many evaluations only need a bounded decision — was the answer grounded? Did it follow the instruction? Which response was better?"*

**Where it holds** — within **three percentage points** of the strongest judge tested, on:
- ordinary response preferences
- evidence-grounded factuality
- final-answer checks

**The cost** — *"On the paper's matched workload, Jev cost only **0.36 percent** of the strongest comparator's fee."* Which, as the thread notes, makes it practical *"to evaluate more agent responses, across more criteria, without scaling the evaluation bill at the same rate."*

**Confidence as a routing mechanism, with numbers**: high confidence → accept; low → escalate to a stronger LLM. *"A frozen version of this cascade retained about **99 percent of GPT-6's accuracy** while using roughly **57 percent of its fee**."*

### The boundary — and it lands exactly where the wiki warned

> *"It fell behind when evaluation required **checking complex derivations** or **resisting an elaborately written wrong answer**. It also struggled with **factuality judgments when no reference evidence was provided**. In those cases, **confidence did not reliably expose the errors.**"*

**That last sentence is the important one.** [[jev]] carries an explicit warning that *if confidence is not well calibrated, the threshold pattern is worse than no pattern, because it converts an unreliable number into an automated action.* **CMU found precisely that failure, in a bounded and named set of cases.** The caveat was right, and it is now specific rather than speculative: the routing pattern is safe where reference evidence exists and the judgment is shallow, and unsafe on derivations, adversarial prose, and unreferenced factuality.

The paper's own conclusion is appropriately narrow: *"the paper is not arguing that Jev should replace every LLM judge."*

### The community plugin — and an unusually honest eval

`github.com/aaddrick/building-with-typesafe-jev`, posted to r/claudeskills with the line *"I'm coming up for air from the bottomless evals ocean."* Contents: best practices, **anti-patterns**, an API reference, and links to **150+ community projects grouped by domain**.

**The methodology is better than most vendor benchmarks**: six Jev coding tasks, **10 runs each**, three conditions — no plugin, TypeSafe's official plugin, and this one — with judgment calls sent to **three judges from three providers** (Claude Opus, GPT-6 Sol, Kimi K3) and **majority deciding**.

| Condition | Share of checks passed |
|---|---|
| No plugin | **0.65** |
| Official plugin | **0.77** |
| This plugin | **0.96** |

Two things follow. **150+ community projects means an ecosystem formed in twelve days** — Jev launched 2026-09-15. And **a community plugin beating the vendor's official one by 19 points** is either a real gap in the official docs or an overfit eval; a commenter asks the right question in the thread — *"Can you share some real use examples of how it helped you?"* — and it is unanswered in the capture.

## Pages Updated

- [[jev]]
- [[loop-engineering]]
- [[skill-md]]

## Notes

- **Neither paper nor plugin fetched directly.** The CMU findings come via Pachaar's thread; the plugin numbers are the author's own self-report on his own plugin, which is the obvious conflict.
- **The plugin eval is self-designed and self-run**, but cross-provider judges with majority vote and 10 runs per task is stronger design than most claims this wiki folds. Recorded as well-designed *and* self-interested.
- **CMU paper title and arXiv ID not captured** — worth retrieving before citing the 0.36% or 99%/57% figures anywhere load-bearing.
