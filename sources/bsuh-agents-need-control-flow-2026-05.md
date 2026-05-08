---
title: Agents need control flow, not more prompts
type: source
medium: article
url: https://bsuh.bearblog.dev/agents-need-control-flow/
ingested: 2026-05-07
---

## Summary

Brian (bsuh.bearblog.dev) argues that reliable agents tackling complex tasks need **deterministic control flow encoded in software, not increasingly elaborate prompt chains**. Treats the LLM as a component within a larger system rather than the primary decision-maker. Frames "MANDATORY" / "DO NOT SKIP" language in prompts as a symptom that you've hit prompting's limit. Underlying problem: prompts are "non-deterministic, weakly specified, and difficult to verify" — adding more prompt rules doesn't change those properties, only obscures them. Conceptual post; no code patterns or framework recommendations.

## Key Claims / Takeaways

- **Core argument**: reliability comes from explicit state transitions and validation checkpoints, not from better prompts. The LLM should sit *inside* a software system structured for control flow, not *be* the system.
- **Diagnostic signal**: when your prompt has imperatives in caps ("MUST", "DO NOT", "ALWAYS"), you're patching non-determinism with persuasion. The fact that this works at all is fragile and degrades silently as agents take on more state.
- **Software-engineering style for agents**: recursive composability, libraries, modular functions — treat agent systems like traditional software, not like long prompt chains.
- **No concrete patterns provided** — the post is a conceptual stake-in-the-ground, not an implementation guide.

## Why This Matters for the Wiki

This is a **counter-positioning** voice in the practitioner conversation. Most of the May 2026 wiki content (skills frameworks, prompt cheatsheets, "8 senior prompts" patterns) is about **better prompting**. Brian's claim is that prompting itself is the wrong axis — if your agent matters, you need control flow primitives in code. Aligns with:

- **Zohar Einy's organizational harness** in [[benln-x-karpathy-agentic-engineering-2026-05]] — agents need governance/orchestration/measurement layers around them, not just smarter prompts. Brian extends this from organizational scale to per-agent architectural scale.
- **Karpathy's spec-first framing** in [[agentic-engineering]] — the spec is what enables deterministic structure; prompts implement details inside it.
- **Cheng & Zhang's localization gap** in [[cheng-zhang-distributed-icl-2026-05]] — if model behavior is not cleanly localizable, building reliability via prompt-tuning becomes harder still; control flow side-steps the problem.

## Pages Updated

- [[control-flow-agents]] — new concept page (counterpoint to prompt-engineering-as-panacea)
- [[agentic-engineering]] — new "Counter-Position: Control Flow Over Prompts" subsection
