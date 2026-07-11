---
title: "Alex Lieberman (@businessbarista) — 7 AI-engineering best-practices takeaways from an engineering leader (2026-07-09)"
type: source
medium: twitter-thread
url: https://x.com/businessbarista/status/2075287227706302593
ingested: 2026-07-10
---

## Summary

Alex Lieberman (Morning Brew co-founder, **@businessbarista**) relays **7 takeaways** from a meeting with one of his engineering leaders on AI-engineering best practices. The through-line: getting probabilistic models to behave deterministically comes from **hyper-structured, opinionated file/workflow design and markdown-as-schema** — a manager-tier restatement of the [[claude-md-pattern|CLAUDE.md]] / [[loop-engineering|verifier-discipline]] doctrine, with two genuinely fresh framings: **markdown metadata as the verification gate for non-software tasks**, and a **"strong immune system around markdown files" / autophagy** framing for spec bloat.

## Key Claims / Takeaways

1. **Spec writing + strong reading comprehension are the two most valuable AI-engineering skills today.** (Reply thread reinforces: *"everyone speeds to code, no one wants to think first"*; *"clear paragraph of intent"* beats vibe-coding.)
2. **Being hyper-structured and opinionated** in workflows is how you get probabilistic models to behave deterministically *and* spend tokens efficiently.
3. **Markdown metadata/schema makes non-software tasks verifiable** → *"which allows you to close the agent loop more successfully."* — the cleanest statement yet of *how you build a verifier for knowledge work*: standardized frontmatter/schema is the objective "done" gate that [[loop-engineering]] requires. (The wiki's own [[llm-wiki-pattern]] schema discipline is an instance of exactly this.)
4. **File organization as a first-class skill** — *"thoughtfully structure/organize your files like good engineers always have to get the least entropy from models."*
5. **A "strong immune system around markdown files"** — as a workflow gets more reps, specs bloat with conflicting/unnecessary rules. Their fix: **Hermes agents + a thin memory layer**; open problem = *"memory/markdown autophagy"* (pruning specs so they don't rot). Directly operationalizes the [[claude-md-pattern|CLAUDE.md-compliance-decay-past-200-lines]] problem.
6. **Their engineering-process stack**: *CLI + deeply opinionated folder/file system + markdown metadata + coding agents + Linear as source of truth.*
7. **Mental model**: *"how can we make sure the agent has one way to do things and can validate its output"* — one canonical path (minimize entropy surface) + self-validation.

## Editorial note

Manager/organizational-leader register, not a frontier-practitioner or vendor voice — Lieberman is relaying a lieutenant's takeaways, so no dedicated `people/` page. Value is the **markdown-metadata-as-verifier** and **markdown-autophagy** framings, folded into the concepts the wiki already tracks.

## Pages Updated
- [[claude-md-pattern]]
- [[loop-engineering]]
