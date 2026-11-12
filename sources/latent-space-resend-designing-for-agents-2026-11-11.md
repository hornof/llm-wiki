---
title: "Designing for Agents — Zeno Rocha, Resend"
type: source
medium: podcast-episode
url: https://latent.space/p/resend/
ingested: 2026-11-11
---

## Summary

A [[latent-space|Latent Space]] episode with Zeno Rocha, co-founder and CEO of Resend, an email API. It asks why coding agents keep recommending Resend over larger rivals, and what makes a developer product easy for an agent to choose and use. Only the show notes were read, not the transcript. Figures are Rocha's or the cited study's.

## Key Claims / Takeaways

- **Agents pick the default.** *"In a recent AEO study, Claude Code picked Resend first in 64 of the 102 email recommendations the researchers could extract."* SendGrid *"came first seven times, yet showed up 55 times as an alternative."* The study itself was not fetched.
- **Scale (Rocha's figures):** *"4.3 million users and 120,000 paying customers"*.
- **Distribution came from a template.** Resend first released React Email, an email-template library that also worked with SendGrid, so some of Resend's code was already in a project by the time the developer looked for a new provider.
- **Make pages readable by agents.** The pricing page is a slider for people; *"Add .md to the URL and the agent gets a table it can read in one request."*
- **MCP server growth:** *"from roughly 20 tools or fewer at launch to more than 80"*, to match the dashboard.
- **A cheap test for MCP designers:** *"expand the result of a call you make every day and see how much of it the model actually needs."* Rocha found a result too large for the context window, which cutting the tool count wouldn't fix.

## Pages Updated

- [[mcp]] — Current State
- [[claude-code]] — Traction Signals (agent tool choice)
