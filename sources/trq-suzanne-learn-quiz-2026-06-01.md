---
title: "Thariq Shihipar: Suzanne's Learn Quiz prompt (Anthropic-internal session-recap pattern)"
type: source
medium: twitter-thread
url: https://x.com/trq212/status/2061545633560010826
ingested: 2026-06-02
---

## Summary

[[thariq-shihipar|Thariq Shihipar]] (Anthropic Claude Code team; @trq212 on X) shares (2026-06-01) a **Claude post-session "Learn Quiz" prompt** from his Anthropic colleague Suzanne — a practitioner pattern Anthropic employees use to *stay in the loop with Claude and fully understand the work being done*. **2nd wiki-captured Thariq Shihipar surface** (first was [[willison-html-effectiveness-2026-05|Willison's surfacing of his "Unreasonable Effectiveness of HTML" framing]]). **First wiki-captured concrete Anthropic-internal Claude-usage practice** beyond the published cookbook and Founder's Playbook.

## Key Claims / Takeaways

### The Learn Quiz pattern

> *"been asking others at Anthropic how they stay in the loop with Claude and fully understand the work being done — this is one of my favorites from Suzanne… this is usually what she runs after Claude has done some work in a session."*

**Pattern shape**: after Claude completes a substantive piece of work in a session, run a prompt that asks Claude to **quiz the operator on what was just done**. The operator answers the quiz; the quiz reveals comprehension gaps; the operator can drill into the gaps before context-clears.

**Full prompt available at**: [gist.github.com Learn Quiz](https://gist.github.com/...) (specific gist URL in the post). Primary not deeply fetched.

### Pairs with adjacent practitioner-content register patterns

- **[[nateherk-opus-4-8-aios-2026-05-29|Nate Herk's `/session-handoff` slash-command]]** — both are *post-session retrospective primitives* for context-management. Nate Herk's pattern is *summary-for-resume-after-context-clear*; Suzanne's pattern is *quiz-for-comprehension-before-context-clear*. **Two distinct retrospective primitives addressing the same context-window-bounded-attention problem from opposite ends** (preserve work-state vs preserve operator-state).
- **[[karpathy-html-output-taxonomy-2026-05-08|Karpathy's HTML output framing]]** — surfaced via amplification in the comment thread by @WuTangAI (Deepak Dhingra): *"Karpathy mentioned sometimes back about asking the agent to explain in html, so now, I just ask claude to explain the session in HTML and it does phenomenal job."* **Same post-session-comprehension pattern, different output format (quiz vs HTML explainer).**
- **[[claude-md-pattern|CLAUDE.md pattern]]** — the Learn Quiz operates at the *per-session* level rather than the *per-project* level of CLAUDE.md, but the underlying discipline (operator-side investment in comprehension before automation-at-scale) is consistent across both.

### Why it matters for Anthropic-internal-practice tracking

- **First wiki-captured concrete Anthropic-internal Claude-usage practice** surfacing from a non-employee-position-paper, non-cookbook surface. Anthropic-internal practice is structurally different from external practitioner-content because Anthropic engineers have:
  - Earlier access to model capabilities
  - Inside understanding of training-side intent (what Claude is *designed* to do well)
  - First-hand pressure to validate their own practices on the product they ship
- **Anthropic-employees-using-Claude-as-quiz-master** is a *meta-recursive* usage pattern — using Claude to manage operator-side comprehension of Claude's own work. Pairs with [[eng-khairallah|eng_khairallah's]] *"system that prompts itself"* framing as the operator-discipline-at-internal-scale instantiation.

### Comment-thread amplifications worth surfacing

- **Gaurang Karia** (@GaurangKaria): *"On similar lines, I built this as hooks which can be saved to Obsidian too."* — links `gkaria/vibe-learn` GitHub repo. **First wiki-captured Claude-Code-hooks → Obsidian save-pattern artifact.** Adjacent to the wiki's own `claude-obsidian:save` skill pattern.
- **Serge Doubinski**: *"I have an Agent look through everything you and team post every day and try to synthesize 😅 Also stored as wiki and applied contextually during projects to bring in the new practices."* — **first wiki-captured Anthropic-team-content auto-synthesis-to-personal-wiki practitioner workflow.** Pairs with [[autoresearch|the autoresearch pattern]] applied to a specific source (Anthropic-team output).

### What's notably absent from the post

- **Suzanne's last name / team** at Anthropic — not specified
- **The specific gist content** — primary not deeply fetched
- **Suzanne's prior practitioner-content surfaces** — none captured in the wiki yet

## Pages Updated

- [[thariq-shihipar]] — 2nd wiki surface; Anthropic-internal-practice surfacing role added; pairs with HTML output framing as the prior Thariq surface
- [[anthropic]] — Anthropic-internal-practice signal added as adjacent to the strategic-coordination bundle; specific internal-team-member practices now wiki-tracked
- [[claude-md-pattern]] — Learn Quiz pattern noted as the *per-session* operator-discipline complement to the *per-project* CLAUDE.md discipline
- [[nateherk-opus-4-8-aios-2026-05-29]] — Learn Quiz as the *quiz-for-comprehension* counterpart to Nate Herk's *summary-for-resume* `/session-handoff` pattern
- [[karpathy-html-output-taxonomy-2026-05-08]] — comment-thread cross-confirmation of HTML-explainer pattern

Verification-pending: Suzanne's full identity + team at Anthropic; the specific Learn Quiz prompt content via the gist; whether Suzanne has prior wiki-relevant practitioner-content surfaces.

## Adjacent sources

- [[willison-html-effectiveness-2026-05]] — prior Thariq Shihipar surface (HTML output framing)
- [[nateherk-opus-4-8-aios-2026-05-29]] — `/session-handoff` paired session-management primitive
- [[karpathy-html-output-taxonomy-2026-05-08]] — HTML-explainer pattern Suzanne's quiz pattern adapts
- [[anthropic-claude-cookbook-2026-05]] — official Anthropic cookbook this practice would complement
- [[eng-khairallah]] — *"system that prompts itself"* meta-framing the Learn Quiz instantiates
- [[autoresearch]] — Doubinski's auto-synthesize-Anthropic-team-content workflow uses the autoresearch shape
