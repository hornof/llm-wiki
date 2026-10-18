---
title: "Post by @akshay_pachaar on X — Google open-sources Harness²"
type: source
medium: twitter-thread
url: https://x.com/akshay_pachaar/status/2111753928031531232
ingested: 2026-10-18
---

## Summary

[[akshay-pachaar|Akshay Pachaar]] (2026-10-18) on **Harness²**, a Google Research repo that has an agent rewrite its own harness (system prompt, tools, memory, skills, subagents) for each task while the model weights stay fixed. I fetched the repo README (`github.com/google-research/harness2`) to check the post's claims. The clipping's `published: 2026-06-08` is the date of the older post he quotes, not of this post.

## Key Claims / Takeaways

- **Method (README):** two levels of recursion.
  - *Task level:* a "Propose–Probe–Compose" step. The agent proposes harness edits, runs several candidate versions, and builds a better harness by comparing how the runs behaved. It uses no ground-truth answer or grader.
  - *Across tasks:* adopted harnesses and "evidence-supported lessons" are saved and used as the starting point for the next task.
- **Editable parts (README):** system prompt, guardrails, memory, tool guidance, subagents, skills, scripts, plugins. The edits are carried out through OpenCode (default) or [[codex|Codex]].
- **Results (README, self-reported, "up to"):** one step beats the base harness by up to 11.5 points on WorkBuddy-Bench, 4.5 on JobBench, and 11.8 percentage points on LAB's partial pass rate. More recursion budget gives further gains. Models: Gemini 3.5 Flash and GLM-5.
- **Repo facts at capture:** Apache 2.0; about 6.1k stars; 3 commits; no releases. Paper: arXiv:2610.14224.
- **Dating:** a commenter complains about "JUST" being used for something that happened months ago. The arXiv number 2610.x puts the paper in October 2026, so the complaint looks wrong. The quoted June post is about [[akshay-pachaar-opik-self-repairing-harness-2026-06-08|Opik's self-repair loop]], a different project.

## Pages Updated

- [[loop-engineering]] — new section: the harness edits itself, with no grader
- [[akshay-pachaar]] — notable take
