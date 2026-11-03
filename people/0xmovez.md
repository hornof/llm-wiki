---
name: Movez (@0xMovez)
type: person
affiliation: independent
signal_sources: [twitter, substack]
last_updated: 2026-11-03
---

## Who They Are

**Movez (@0xMovez)** posts on X and Substack about self-improving agents, agent loops, harnesses and evals. The wiki has two of their posts, from 2026-06-18 and 2026-06-29, and files them under [[loop-engineering]]. Background unknown.

*(Rewritten 2026-11-03 to remove automated-pass filler. Quotes checked against the source pages.)*

**Not the same person as @0xMoysei**, who posted about Karpathy's LLM-wiki pattern on 2026-06-23 ([[moysei-karpathy-llm-wiki-pattern-amplification-2026-06-23]]). Earlier lints confused the two handles.

## Their Current Focus

- **2026-06-29: the loop, the harness and evals** ([[movez-ex-google-engineer-ai-agent-loops-harness-evals-2026-06-29]]). Promotes a 20-minute video by an ex-Google engineer and states a five-step loop: *"trace every run → judge it with an LLM → diagnose → fix → ship"*. The post quotes [[0xcodez|0xCodez's]] 14-step roadmap.
- **2026-06-18: a 300-agent swarm on Kimi K2.6, checked by Opus 4.8** ([[movez-kimi-opus-300-agent-self-improving-loop-2026-06-18]]). A ten-step playbook, originally published 2026-04-22. Kimi K2.6 runs up to 300 parallel sub-agents across 4,000 coordinated steps, and Opus 4.8 verifies the output. The 4,000 steps are a budget for the whole swarm, so about 13 per agent.

## Notable Takes

- **Split the worker from the checker** (06-18): *"The engine learns. The closer keeps it honest."* A cheap model does the work and a stronger one verifies it.
- **Save the workflow once, replay it cheaply** (06-18): *"20 minutes on run one. 30 seconds on run fifty."* The speedup comes from saving the workflow as a Skill after the first run. It's the author's own figure.
- **The stack** (06-29): *"Agent loops + memory + harness + evals - thats the stack."*
- **A reply worth keeping** (06-29, adelbucetta): *"that loop is just the surface, there's the dark matter of agent judgment calls that nobody talks about."*

## Where to Follow

- X: [@0xMovez](https://x.com/0xMovez)

## Resources

- [[movez-ex-google-engineer-ai-agent-loops-harness-evals-2026-06-29]] — five-step loop and the four-part stack
- [[movez-kimi-opus-300-agent-self-improving-loop-2026-06-18]] — the 300-agent playbook
- [[loop-engineering]] — the concept these posts feed
- [[0xcodez]] — the roadmap quoted on 06-29
- [[moysei-karpathy-llm-wiki-pattern-amplification-2026-06-23]] — the other handle, for disambiguation
