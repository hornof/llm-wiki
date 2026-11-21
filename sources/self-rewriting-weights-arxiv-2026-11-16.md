---
title: "Language Models Can Rewrite Their Own Weights"
type: source
medium: paper
url: https://arxiv.org/abs/2611.21885
ingested: 2026-11-20
local_source: "_raw/self-rewriting-weights-arxiv-2026-11-16.txt"
---

## Summary

arXiv 2611.21885 (Jiajun Fan, Ge Liu and nine others; v1 2026-11-16, v2 2026-11-18). An open 27B model is given its own weights, its graded answers and the ability to run itself, and edits its weights by reasoning, with no gradients. Only the abstract was read. It's an unreviewed preprint that claims a first, so treat the numbers as the authors'.

## Key Claims / Takeaways

- **The claim:** *"to our knowledge for the first time, a language model rewrites its own weights by its own reasoning and becomes better, with no gradients and no training."* The authors call it self-rewriting.
- **Gain:** *"its own edit makes it 6.6 points more accurate on problems it never saw."* *"over eight consecutive sessions its accuracy only rises"*; it tests edits on practice problems and submits only those that work.
- **Repair:** a damaged copy that *"solves almost nothing"* is brought back *"to over 80% of the original accuracy on image tasks it never saw"*, without reading the original weights.
- **Scale:** in one model family *"the smaller models make no edit or break themselves, and only the largest improves and repairs itself."*
- **Their framing:** they call it *"a necessary step toward recursive self-improvement"* and say *"The wall between training and inference is a limit of our tools, not a property of intelligence."*
- **Not stated in the abstract:** which model, which benchmarks, or how the edits are made. The brief's note, "wait for replication", stands.

## Pages Updated

- [[recursive-self-improvement]]
