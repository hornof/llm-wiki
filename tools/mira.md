---
name: Mira
type: tool
category: platform
status: emerging
last_updated: 2026-07-12
---

## What It Is

**Mira** is a **no-code AI agent that lives inside Telegram** — you message it in natural language and the automations it runs are called **Skills**. Each Skill is a loop with the standard parts (a trigger, an action, and autonomous execution) that the user never has to wire together. Its positioning line: *"ChatGPT answers, Mira acts"* — it sends the email, files the real Linear ticket, posts the digest, rather than handing back a draft.

> ⚠️ **Signal + provenance caveat.** The sole wiki source is a **promotional article** — [[anatolikopadze-loops-explained-2nd-surface-2026-06-21|AnatoliKopadze's "Loops explained"]] — whose back half is a Mira ad with affiliate-style Telegram links. No independent corroboration is captured. Mira is also **off the wiki's core AI-engineering-career focus** (it's a consumer life-automation bot, not a coding/eng tool). Tracked here mainly to (a) resolve the dangling `[[mira]]` link and (b) **correct a prior misattribution** — see below.

> 📝 **Record correction (2026-07-12).** The first clip of the Kopadze article truncated before the Mira section, so the wiki initially guessed "Mira" (from the title *"Loops explained: Claude, GPT, Mira…"*) was a **model** (Mistral? a new model?). The fuller re-clip confirms **Mira is a Telegram no-code agent product, not a model.** This page and the source's verification-pending notes are corrected accordingly.

## Traction Signals

- **[unsourced beyond one promotional article]** — single Kopadze thread/newsletter (2026-06-20). No adoption metrics, no independent reviews captured.
- Claimed integrations: **500+ apps via [Composio](https://composio.dev)** (Notion, Gmail, Google Calendar, GitHub, Figma, Stripe, …).

## How to Use It

- Message **@mira on Telegram** (free tier claimed); describe a Skill in plain words, e.g.:
  > *"Every weekday at 7am, check my Gmail and Google Calendar. Send me a short brief: my 3 most important meetings, anything urgent, and one follow-up I owe. Under 120 words."*
- The Skill becomes a running loop (time/event trigger → multi-step action → autonomous run → result delivered back in chat).

## Key Concepts

- **Skill** — Mira's name for a loop: trigger + action + autonomous execution, authored as one natural-language message.
- **Model-agnostic** — claims to run GPT / Claude / Gemini depending on the task.
- **Long-term memory** — persists across sessions and group chats (per the source).
- **Composio connectors** — the 500+-app action layer that lets it *act*, not just suggest.

## Compared To

- **[[claude-cowork|Claude Cowork]]** — same "describe it in plain words, it runs autonomously" ambition, but Mira is Telegram-native and consumer-life-focused vs Cowork's desktop/knowledge-work surface.
- **[[slate]]** — sibling case of a loop-engineering explainer used to promote a specific tool; both filed `emerging` with a single-promotional-source caveat.
- **General-purpose LLM chat (ChatGPT/Claude apps)** — Mira's claimed differentiator is *acting* (via Composio) + scheduling + persistent memory, vs answer-and-wait chat.

## Resources
- [[anatolikopadze-loops-explained-2nd-surface-2026-06-21]] — the sole (promotional) source
- Composio — the connector layer Mira is built on
