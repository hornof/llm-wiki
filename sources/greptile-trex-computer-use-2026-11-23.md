---
title: "How should an LLM see a computer?"
type: source
medium: article
url: https://www.greptile.com/blog/trex-computer-use
ingested: 2026-11-23
local_source: "_raw/greptile-trex-computer-use-2026-11-23.txt"
---

## Summary

Greptile's write-up of the experiments behind TREX, its QA agent that runs a pull request's code on a real desktop. It ran seven OpenAI models on the same 172 OSWorld tasks in three setups: screenshots alone, screenshots plus the accessibility tree with clicks by coordinates, and the tree with clicks by element ID. The tree and ID clicks greatly helped weaker models and did nothing for the strongest. TREX uses screenshots at every step, clicks by ID where the tree has the element, and falls back to coordinates elsewhere.

## Key Claims / Takeaways

- **Setup** (Greptile): *"Every setup used the same agent on 172 OSWorld tasks, with one attempt per task, a 50-step limit and low reasoning effort, scored by OSWorld’s own graders."* All seven models are OpenAI's.
- **Screenshots alone** (Greptile): *"GPT-4.1 scored a mere 5.4% with screenshots alone, while the more recent GPT-6.1 Sol scored 83.8%."*
- **The tree helps weak models** (Greptile): *"GPT-5.2 went from 15.8% with screenshots alone to 36.2% after the tree was added, and GPT-4.1 from 5.4% to 20.6%."*
- **ID clicks help them more** (Greptile): *"GPT-5.2 went from 36.2% with the tree + coordinates to 52.8% when it clicked by ID, and GPT-4.1 from 20.6% to 29.3%."*
- **Strong models don't care** (Greptile): GPT-6.1 Sol *"scored 82.7% clicking by coordinates and 82.1% clicking by ID"*, and *"none of the three strongest models changed by a statistically significant amount."* Weaker models *"gained 9 to 37 points with the tree and ID clicks"*.
- **Where the tree fails** (Greptile): canvas apps such as Figma and games publish little or no tree, and some bugs (text overflowing its box) only show in pixels, so the screenshot stays.
- **Why it matters for review** (Greptile): *"Greptile reviewed your code by reading it. TREX adds a new step: it runs the code."* They plan to rerun the experiment for each new model.

## Pages Updated

- [[playwright-mcp]] (Compared To: the computer-use bullet)
