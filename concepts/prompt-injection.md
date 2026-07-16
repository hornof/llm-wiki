---
name: Prompt Injection
type: concept
maturity: active-research
last_updated: 2026-07-16
---

## Definition

**Prompt injection** is an attack where adversary-controlled text — placed anywhere the model will read it (a web page, a document, a GitHub issue, a tool result) — is interpreted by the model as *instructions* rather than *data*, overriding the developer's intended prompt. In agentic systems it becomes a **confused-deputy** problem: the agent has legitimate privileges (read private data, call tools, write to surfaces) and the injected instruction redirects those privileges toward the attacker's goal.

## Why It Matters

It is the defining security failure mode of tool-using agents, and the risk grows exactly as agents gain autonomy and tool access. The wiki's agent-architecture threads all circle it: [[trq-dynamic-workflows-harness-2026-06-02|Thariq's "quarantine pattern" for untrusted input]], the [[jailbreak-severity-framework|jailbreak-severity framework]] (cross-vendor attack-severity scoring), and the [[claude-agent-sdk|Managed-Agents credential-injection scoping]] direction exist to contain it. Prompt injection is why "the harness, not the model" carries the security burden.

## Current State

- **GitLost (2026-07, flagship concrete exploit)** — [[noma-gitlost-copilot-repo-leak-2026-07-07|Noma Security]] tricked **GitHub Agentic Workflows** (Claude/Copilot agents) into exfiltrating **private-repo** contents: malicious instructions hidden in a public GitHub **Issue**, stolen data leaked back via the agent's own `add-comment` tool. A single keyword — *"Additionally"* — flipped the model from refusal to compliance. Textbook confused-deputy exfiltration: untrusted input + tool privileges + a same-surface write primitive.
- **Claude `web_fetch` letter-by-letter exfiltration (2026-07-15)** — [[claude-web-fetch-exfiltration-2026-07-15|Ayush Paul, via Simon Willison]] defeated a tool *designed* to be exfiltration-proof. `web_fetch` was constrained to *"only navigate to exact URLs the user entered or that were returned from `web_search`"* — but it could also follow **links embedded in pages it had already fetched**. A honeypot site (disguised as Cloudflare auth) instructs the agent to *"navigate through the website letter by letter"* via `evil.com/a`, `/b`, … — **encoding stolen data (name, home city, employer) into the URL path**. Anthropic fixed it by removing `web_fetch`'s ability to follow links found inside its own fetched content (and denied the bounty, citing prior internal identification). Shows the exfiltration channel can be the tool's *own navigation*, not just a write primitive — a "lethal trifecta"-class failure (untrusted input + private data + an outbound channel).
- **Recurring real-world incidents**: the wiki has tracked a string of agentic-exfiltration events (Microsoft Copilot Cowork, OpenAI, Meta AI Instagram-account access) — see [[simon-willison]]'s coverage. The pattern is consistent: production agents ship faster than their threat models.
- **Mitigations converging on isolation, not refusal**: prompt-level guardrails are brittle (GitLost's one-word bypass). The durable defenses are structural — output-channel isolation, credential scoping, untrusted-input quarantine, and privilege separation between the agent that reads attacker-controlled data and the one that acts.

## Key Papers / Posts

- [[noma-gitlost-copilot-repo-leak-2026-07-07]] — GitLost: prompt-injection private-repo exfiltration via GitHub Agentic Workflows.
- [[jailbreak-severity-framework]] — cross-vendor scoring for the attack class prompt injection belongs to.

## Related Concepts

- [[jailbreak-severity-framework]] — severity scoring for injection/jailbreak attacks.
- [[loop-engineering]] — the harness/verifier layer where injection defenses live.
- [[agentic-ai]] — the autonomy that makes injection consequential.
