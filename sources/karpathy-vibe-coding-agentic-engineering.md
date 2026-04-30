---
title: "Andrej Karpathy: From Vibe Coding to Agentic Engineering"
type: source
medium: video
url: https://www.youtube.com/watch?v=96jN2OCOfLs
ingested: 2026-04-29
---

## Summary
Andrej Karpathy speaks at Sequoia Capital's AI Ascent 2026 event (April 2026), interviewed by Sequoia partner Stephanie Zhan. He covers the December 2025 inflection point in agentic AI tools, introduces his framing of "agentic engineering" as distinct from vibe coding, discusses the Software 1.0/2.0/3.0 paradigm, verifiability as a theory of AI capability distribution, jagged intelligence, and the enduring value of human understanding. He also confirms his ongoing personal LLM Wiki practice.

## Key Claims / Takeaways
- December 2025 was a qualitative inflection point where agentic workflows "actually started to work" — models stopped needing correction and he started trusting the system end-to-end.
- **Software 3.0**: Programming has become prompting; the context window is the lever over an LLM "interpreter"; programming paradigm is now "what is the piece of text to copy paste to your agent?"
- **Vibe coding vs. agentic engineering**: Vibe coding raises the floor (everyone can build). Agentic engineering preserves the quality bar of professional software at higher speed. Distinct disciplines.
- **10x multiplier claim**: Karpathy believes the agentic engineering speedup is "a lot more" than 10x for engineers who master it.
- **Verifiability thesis**: LLMs excel where outputs can be verified (math, code) because labs use RL with verification rewards. This explains the "jagged" capability profile of current models.
- **Jagged intelligence**: Models that can "refactor a 100,000 line codebase or find zero day vulnerabilities" simultaneously tell you to walk 50 meters to a car wash. Jaggedness = not part of the RL circuits.
- **Ghosts vs. animals**: LLMs are "summoned ghosts" shaped by data and reward functions, not animal intelligences with intrinsic motivation. Implications: yelling at them doesn't work; they are statistical simulation circuits.
- **Human skills that gain value**: taste, aesthetics, engineering judgment, system-level design decisions (e.g., insisting on unique user IDs), spec authorship and oversight. Details (API signatures, etc.) safely handed to the agent.
- **"You can outsource your thinking but you can't outsource your understanding."** — tweet Karpathy cited as his most thought-provoking recently.
- **Agent-native infrastructure**: everything is currently written for humans; the transition to agent-native docs, deployment systems, and services is mostly unbuilt.
- **Neural computers**: speculative long-run vision — neural nets become the host process; CPUs become co-processors for deterministic appendages.
- **LLM Wiki habit confirmed**: Karpathy still maintains a personal wiki from articles and uses it to ask questions and gain insight; calls it "synthetic data generation over fixed data."
- **Code quality concern**: agentic-generated code is often "bloaty," with "copy paste and awkward abstractions that are brittle" — expects models to improve on this; cites microGPT simplification as a task models currently fail at.
- **Hiring framing**: traditional puzzle-based interviews are old-paradigm. New framing: give a large project (e.g., "build a Twitter clone, make it secure, then have agents try to break it").
- **Fine-tuning lever**: if you're in a verifiable domain not covered by frontier lab RL, you can fine-tune using your own RL environments — valid strategy for founders.
- **MenuGen example**: Karpathy built a full app to add pictures to restaurant menus (OCR + image gen + Vercel deployment), then discovered the Software 3.0 version is "give a photo to Gemini and say use NanoBANANA to overlay" — his own app "shouldn't exist."
- **OpenClaw installer**: installation is a block of text to paste to your agent, not a shell script — cited as a canonical example of Software 3.0 thinking.

## Pages Updated
- [[andrej-karpathy]]
- [[llm-wiki-pattern]]
- [[agi]]
- [[claude-code]]
- [[agentic-ai]]

## Pages Created
- [[software-3-0]]
- [[vibe-coding]]
- [[agentic-engineering]]
- [[verifiability-and-jagged-intelligence]]
- [[eureka-labs]]
