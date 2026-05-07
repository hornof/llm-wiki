---
title: "Agents can now create Cloudflare accounts, buy domains, and deploy"
type: source
medium: article
url: https://blog.cloudflare.com/agents-stripe-projects/
ingested: 2026-05-06
---

## Summary
Cloudflare and Stripe co-launch **Stripe Projects**, a protocol that lets AI agents create Cloudflare accounts, purchase domains via Cloudflare Registrar, and deploy applications with API tokens — autonomously, with Stripe acting as identity attester and payment orchestrator. Authors Sid Chatterjee and Brendan Irvine-Broque frame it as treating agents as "first-class concerns" in account provisioning and payments. Concrete agent capability crossing into financial transactions and infrastructure provisioning.

## Key Claims / Takeaways
- **New agent capabilities**: account creation, domain purchase via Cloudflare Registrar, app deployment + API token issuance — all without human dashboard interaction (humans optionally in the loop for permission grants).
- **Three-component protocol**:
  1. **Discovery**: `stripe projects catalog` returns JSON catalog of Cloudflare + third-party services.
  2. **Authorization**: Stripe attests user identity, auto-creates Cloudflare account if needed; existing users authenticate via OAuth.
  3. **Payment**: Stripe issues payment tokens (no raw card data); default $100/month per-provider spending cap, adjustable via budget alerts.
- **Guardrails**: preset budgets rather than direct financial access; user retains approval authority for critical actions ("prompt for input and approval when necessary").
- **Stripe Atlas perk**: $100,000 in Cloudflare credits for startups incorporating through Stripe Atlas.
- **Technical surfaces named**: Stripe CLI with Projects plugin (`stripe projects init`); Cloudflare's Code Mode MCP server; Cloudflare Agent Skills.
- **Strategic framing**: protocol-level co-design between two infra primitives. Pattern for future agent-as-customer relationships across SaaS.
- **Authors**: Sid Chatterjee, Brendan Irvine-Broque (single-post mentions; not warranting people pages yet).

## Pages Updated
- [[cloudflare]] — new company page (first wiki appearance)
- [[mcp]] — added Cloudflare Code Mode MCP server as production traction signal
- [[agentic-ai]] — added "Agent-as-Customer Pattern" note linking Stripe Projects to economic-actor agents
- [[saas-disruption-thesis]] — added Stripe Projects as a concrete infrastructure precondition for agent-driven SaaS purchasing
- [[index]] — added cloudflare under Companies & Labs; source under Recent ingests
