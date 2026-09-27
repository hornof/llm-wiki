---
title: "JEV-as-a-Judge: Accept When Confident, Escalate When Unsure"
type: source
medium: paper
url: https://arxiv.org/abs/2609.26550
published: 2026-09-22
ingested: 2026-09-28
---

## Summary

The **primary** for the CMU evaluation of [[jev|Jev]] that the wiki folded secondhand on 2026-09-27 from a practitioner thread. **arXiv:2609.26550**, v1 submitted **2026-09-22**, by **Yubo Li, Yidi Miao, Ramayya Krishnan and Rema Padman** (Carnegie Mellon).

Retrieving it was flagged as a verification item yesterday — *"CMU paper title and arXiv ID not captured; retrieve before citing the figures anywhere load-bearing."* **Good thing, because the primary is more favourable to Jev than the secondhand rendering was**, and the wiki's page needed correcting. See below.

## Abstract (verbatim)

> *LLM-as-a-judge enables evaluation across diverse tasks, but inference cost and confidence reliability become critical at scale. We study whether a decision-only judge can provide an economical first pass and identify when stronger evaluation is needed. Comparing jev-as-a-judge with **sixteen generative and reward-model judges**, with **blinded human adjudication**, we find it within **three percentage points** of a state-of-the-art LLM judge, our strongest comparator, on ordinary preference and evidence-grounded factuality at **0.36% of the comparator's fee**. Larger gaps arise when judgments require **checking a derivation** or **resisting an elaborately written wrong answer**. On several benchmarks, JEV's gap to this comparator is **concentrated in low-confidence decisions**. A frozen cascade that accepts confident verdicts and escalates uncertain ones retains **99% of the comparator's accuracy at lower cost**.*

## What the primary changes

### Methodology is stronger than the thread conveyed

**Sixteen judges** — generative and reward-model — with **blinded human adjudication**. Neither detail survived into the secondhand summary, and both matter for how much weight the 3-point result carries.

### The confidence finding is the opposite way round from what the wiki recorded

The thread rendered the limitation as: *"in those cases, confidence did not reliably expose the errors."* The wiki folded that as **independent confirmation of its own warning** that Jev's confidence signal might not be trustworthy.

**The abstract says something close to the reverse**:

> *"On several benchmarks, JEV's gap to this comparator is **concentrated in low-confidence decisions**."*

**That is the confidence signal working.** If the errors cluster where confidence is low, the signal is doing its job — which is precisely *why* the cascade retains 99% of accuracy. A signal that failed to expose its own errors could not support a cascade at all.

The two are not flatly contradictory — *"several benchmarks"* is not all of them, and the harder categories may behave differently — but **the wiki overstated the failure, and the correction goes on [[jev]].**

### One number in the wiki is not in the paper

The wiki cited the cascade as *"~57% of its fee"*, from the thread. **The abstract says only "at lower cost"** and gives no percentage. The **0.36%**, **3 percentage points** and **99%** figures are all confirmed verbatim; **57% is not.** Treat it as unsourced until the full text is read.

## What still stands

The named boundary is confirmed in the abstract: **larger gaps arise on checking a derivation and on resisting an elaborately written wrong answer.** The wiki's operational guidance — that the routing pattern is strongest on shallow, reference-grounded judgments — survives intact. What does not survive is the claim that confidence fails to flag those cases.

## Pages Updated

- [[jev]] (correction)
- [[loop-engineering]] (correction)

## Notes

- **Abstract only.** The full PDF was not read; per-benchmark breakdowns, the identity of the "state-of-the-art" comparator, and the cost basis behind 0.36% are all unexamined.
- Krishnan and Padman are CMU Heinz College faculty; the wiki has not verified affiliations beyond the arXiv listing.
