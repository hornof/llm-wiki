---
title: "How Anthropic ships Claude with Claude: Separating the Brain from the Hands"
type: source
medium: podcast-episode
url: https://latent.space/p/opus55/
ingested: 2026-10-28
---

## Summary

Latent Space (swyx, 2026-10-27) interviews Katelyn Lesse and Angela Jiang, Anthropic's heads of engineering and product for the Claude Platform, about the Opus 5.5 launch and Managed Agents. Only the written show notes were read for this page, not the 104-minute transcript. **The useful content is the Managed Agents architecture.** The intro also gets an S-1 figure wrong (below).

## Key Claims / Takeaways

- **A model launch is also an API change:** preserving thinking blocks across turns helps protect reasoning *"against extraction used for distillation"*, but a new requirement *"can also break a customer's existing harness"*.
- **Brain and hands:** Managed Agents *"separates the session log and harness from the sandbox that executes code"*. That means *"a failed sandbox does not have to take the whole agent session with it"*.
- **Security follows from the split:** *"If generated code runs in a sandbox that never receives a service credential, there is no credential in that sandbox for the code to read."* Credentials are attached through a proxy.
- **The design they replaced:** the whole coding agent ran in a sandbox behind an API, so *"if the sandbox disappeared, so did the running agent."*
- **"Dreaming"** is *"one agent inspecting another agent's prior work and writing memories back"*.
- **Priorities:** *"more of its immediate attention has moved to safety as model launches have become harder"*. Latent Space adds that ideas for future capabilities *"should be treated as plans, not shipped promises."*
- **A figure to discard:** the intro credits Anthropic with a *"-126% loss to 19% GAAP profit turnaround"*. The S-1 gives a Q2 GAAP operating margin of 8%, and 19% is the adjusted figure ([[anthropic-s1-public-filing-2026-10-26]]).
- **"Generally accepted #1":** Latent Space calls Opus 5.5 the *"generally accepted #1"* LLM. That's its own description, not a benchmark result.

## Pages Updated

- [[claude-opus-5-5]]: Community Sentiment entry
