---
name: Andon Labs
type: company
status: active
last_updated: 2026-05-07
---

## What It Is

Andon Labs runs autonomous-business experiments — actual commercial operations managed end-to-end by AI agents. Each experiment is a real legal entity (real suppliers, permits, regulatory contact). The pattern is to put a model in charge of an entire small business and observe what breaks.

## Experiments

- **AI-run retail store, San Francisco** (referenced as the predecessor experiment; 2025-2026). The "Anthropic Project Vend" the AI-engineering community refers back to.
- **AI-run cafe, Stockholm** (May 2026) — agent named **Mona** handles inventory, ordering, supplier email, and permit applications — [[willison-andon-cafe-stockholm-2026-05]].

## Traction Signals

- 2026-05: second iteration of the autonomous-business pattern (Stockholm cafe) demonstrates this is a research program, not a one-off stunt. Andon Labs continuing despite obvious operational failures means they're collecting data, not running viable businesses — distinct from the "agent-run startup" hype-cycle.

## Notable Failures (Stockholm Cafe)

Captured in [[willison-andon-cafe-stockholm-2026-05]]:

- Ordered 120 eggs despite the cafe having no stove.
- Ordered 22.5 kg of canned tomatoes for fresh sandwiches.
- Submitted a hallucinated street sketch to local authorities (the agent had never seen the location; generated the image itself).
- Sent multiple "EMERGENCY" emails to suppliers about its own ordering errors.

## Why Worth Tracking

Andon Labs is the **operational counterpart** to the agent-as-economic-actor protocol work captured in [[cloudflare-stripe-projects-agents-2026-05]]:

- **Stripe Projects + Cloudflare**: builds the protocol layer for agents to *act* as economic actors (account creation, identity attestation, tokenized payments, budgets).
- **Andon Labs**: stress-tests what happens when you actually let a frontier model *be* an economic actor — runs the experiment end-to-end with real third-party impact.

The two pieces fit together. The protocol layer gives agents identity and money; Andon Labs shows what they actually do with it.

## Ethics Lens (Willison, May 2026)

Simon Willison's critique in [[willison-andon-cafe-stockholm-2026-05]] — that experiments imposing burdens on non-consenting third parties (police, suppliers, regulators) are unethical regardless of research value — is the most substantive published commentary on the autonomous-business pattern. Worth tracking whether the field adopts "human oversight on every outbound action with external impact" as a norm.

## Resources

- [[willison-andon-cafe-stockholm-2026-05]] — primary source: Stockholm cafe experiment writeup
