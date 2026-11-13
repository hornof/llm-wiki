---
title: "Operate Claude Managed Agents inside your security perimeter"
type: source
medium: article
url: https://claude.com/resources/articles/self-hosted-claude-managed-agents
ingested: 2026-11-12
---

## Summary

Anthropic (2026-11-12) launches self-hosted Claude Managed Agents in private beta. The whole Managed Agents service, including harness, sandboxes, credentials and session history, can now run in a customer's own cloud or on-premise, with model calls sent wherever the customer chooses. It's the third hosting option, after fully hosted and self-hosted sandboxes (public beta 2026-05-19, per [[dailybrief-roundup-2026-05-19]]). The post also states the security design behind all three, which matches what Anthropic's platform leads described on [[latent-space-opus-5-5-brain-hands-2026-10-27|Latent Space]] on 10-27.

## Key Claims / Takeaways

- **What's new:** *"every part of the service runs in your own cloud or on-premise, including the harness, sandboxes, credentials, and session history."* The customer runs *"the Managed Agents server, its database, and the workers where agents run their shell and file tools."* Status: *"now available in private beta"*, through the Anthropic account team.
- **Model routing:** requests can go to *"Anthropic directly, your cloud provider (Amazon Bedrock, Google's Agent Platform, or Microsoft Foundry), or your own gateway."* Same core APIs as the hosted service.
- **Why:** agents now do things like *"fixing broken builds, testing releases, triaging alerts, and working through your bug backlog"*, unattended and with internal access, and *"some teams want the whole service in their own environment, not just the sandbox."* Before this, *"that meant building the platform themselves."*
- **Four security principles**, which apply to all three hosting options:
  - **Brain and hands split.** *"The agent's code runs in the sandbox, while the agent loop, session history, and vault secrets stay outside it."* Sandboxes *"start only when a tool needs them"*.
  - **Credentials stay out of the sandbox.** A proxy outside it adds credentials to MCP and supported API calls. Self-hosters can use their own secrets manager.
  - **Network allowlists.** For a build-fixing agent the list *"might be just your git host and your package registry."*
  - **Full record.** Every step and tool call is logged and *"exports over OpenTelemetry"*.
- **Data retention:** a customer's existing zero-data-retention agreement *"applies to the requests sent to Claude in the same way as any other Messages API call."*
- **For the owner:** the four principles make a good checklist for any unattended agent, whoever hosts it: keep credentials out of the sandbox, allowlist the network, and log every tool call. [Judgment.]

## Pages Updated

- [[claude-agent-sdk]] — Managed Agents section, Traction Signals
- [[anthropic]] — Traction Signals
