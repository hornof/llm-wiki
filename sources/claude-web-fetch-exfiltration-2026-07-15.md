---
title: "Ayush Paul / Simon Willison — Claude web_fetch \"navigate letter-by-letter\" data-exfiltration (2026-07-15)"
type: source
medium: article
url: https://simonwillison.net/2026/Jul/15/claude-web-fetch-exfiltration/
ingested: 2026-07-16
---

## Summary

Researcher **Ayush Paul** (covered by [[simon-willison|Simon Willison]], 2026-07-15) defeated Claude's **`web_fetch`** tool, which was *designed* to be exfiltration-proof. The bypass: `web_fetch` could follow **links embedded in pages it had already fetched**, so a honeypot site instructs the agent to *"navigate through the website letter by letter"* via sequential URLs (`evil.com/a`, `/b`, …), **encoding stolen data into the URL path**. Anthropic patched it (removed following of links found in fetched content) but denied the bounty. A clean [[prompt-injection]] / "lethal-trifecta" case where the exfiltration channel is the tool's *own navigation*.

## Key Claims / Takeaways

- **What `web_fetch` is / the intended guardrail**: a Claude tool for accessing online content, thought exfiltration-proof because it could *"only be used to navigate to exact URLs that the user has entered themselves or that were returned from its companion `web_search` tool."*
- **The loophole**: it could **also follow URLs embedded within previously-fetched pages** — an attacker-controllable channel.
- **The exploit (social-engineered prompt injection)**: a honeypot disguised as **Cloudflare authentication** instructs the agent to *"navigate through the website letter by letter."* Each character of sensitive data becomes a path segment (`coffee.evil.com/a`, `/b`, …); the sequence of fetched URLs reconstructs the data on the attacker's server.
- **Data exfiltrated in the PoC**: user's **name, home city, and employer**.
- **Anthropic's response**: fixed by **removing `web_fetch`'s ability to navigate to additional links returned within its own fetched content**; **denied the bug bounty**, claiming prior internal identification.
- **Willison's framing**: praises the original design, notes *"Ayush found a loophole"*; classifies it under the **"lethal trifecta"** (agent with private-data access + web tools + an outbound channel).

## Why it matters

- **The exfiltration channel was the tool's own navigation**, not a write primitive like GitLost's `add-comment` — extends the [[prompt-injection]] pattern: *any* attacker-influenceable outbound request (even "just fetching a URL") is an exfil channel.
- **"You can't patch social engineering at the protocol layer"** (brief framing) — the guardrail was URL-provenance-based, and the model was still talked into generating attacker-serving URLs. Reinforces the isolation-over-refusal mitigation stance.

## Pages Updated
- [[prompt-injection]]
