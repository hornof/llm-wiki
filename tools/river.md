---
name: River
type: tool
category: platform
status: emerging
last_updated: 2026-05-11
---

## What It Is

[[shopify]]'s **internal AI coding agent**, used by Shopify engineering and (per [[tobi-lutke]]) increasingly by non-engineering functions. Not a publicly available product — surfaced via CEO description in a public post amplified by [[simon-willison]].

## Defining Design Choice

**River refuses direct messages.** All work has to happen in public Slack channels. The DM path is closed by design. Lütke frames this as the agent's primary governance feature, not a configuration flag — work-with-River is *constitutively* visible to the rest of the organization.

This is a categorically different deployment topology from the dominant agent-coding pattern in 2026:
- **Per-developer harness** (e.g., [[claude-code]], Cursor): agent lives in your terminal/IDE/shell, conversations are private by default.
- **Shared-channel participant** (River): agent lives in shared rooms, conversations are public by default.

## Traction Signals

- **May 11 2026 — Shopify CEO public description**: [[tobi-lutke]] describes River and the no-DMs design choice; surfaced and amplified by [[simon-willison]] ("Learning on the Shop floor") — [[willison-shopify-river-2026-05]]. First widely-discussed publicly-described internal-agent example following this deployment pattern.
- **Pedagogical side effect**: forcing every River interaction to be a public transcript turns the agent's day-to-day work into onboarding material for newer employees — "learning on the shop floor."

## Why It Matters Beyond Shopify

- **Existence proof for agent-governance-by-transparency**: rather than gating agents with permission systems, gate them with audience. Cheaper to enforce, harder to circumvent, generates organizational memory as a byproduct.
- **Connects to [[company-brain]]**: every River interaction becomes a record in shared channels — the agent action *is* organizational memory by design, not by retro-instrumentation.
- **Counterpoint to the [[ai-native-organizations]] framing** in [[block]]: Block's model emphasizes per-DRI rebuild of the corporate operating system. River suggests a *shared-substrate* alternative where transparency is the operating system.

## How to Use It

Not publicly available. No SDK, no API.

## Compared To

- [[claude-code]] — per-developer harness, private by default; closest analog as an agent-coding tool but inverted topology.
- [[goose]] — Block's internal harness, also dogfooded; differs from River in being agent-as-tool rather than agent-as-shared-participant.

## Resources

- [[willison-shopify-river-2026-05]] — Lütke's "Learning on the Shop floor" via Simon Willison, May 11 2026 (primary surfacing)
- [[shopify]] — operator/company
- [[tobi-lutke]] — author of the no-DMs design choice
