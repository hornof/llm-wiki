---
title: "@AlfieJCarter — LinkedIn Posting Stack on Claude Code + Playwright MCP"
type: source
medium: twitter-thread
url: https://x.com/AlfieJCarter/status/2049908404349501820
ingested: 2026-04-30
---

## Summary

X post (April 30 2026) describing a Claude Code + Playwright MCP stack that **writes, approves, and publishes a full week of LinkedIn posts from a single Sunday session**. The author claims the system produces three draft variants per topic at 70-80% publish quality, matches each post to a folder photo by descriptive filename, and uses Playwright MCP to schedule the posts directly inside LinkedIn without the user opening the platform.

The detailed playbook (skill file, configuration) is **DM-gated** behind a like + "SKILL" comment + follow gate, so this source captures the *announcement and pattern*, not the implementation. The substantive contribution is a clean articulation of the **profile.md + hooks.md voice-scaffolding pattern**: two persistent context files that give Claude permanent voice and format context across all sessions.

## Key Claims / Takeaways

- **`profile.md` for voice context**: permanent file containing the author's voice, stories, professional background, and ICP. Loaded at the start of every session so generated posts read as the author from session one.
- **`hooks.md` for format library**: curated list of proven post formats with concrete examples, plus a **"no-go list"** of overused openers Claude must avoid. Functions as both a positive (formats to imitate) and negative (lines saturating the space) constraint.
- **Three drafts per topic, not one**: deliberate variant generation so the user picks the best angle. 70-80% quality out of the box, "5 minutes of editing gets them publishable." A direct application of the senior-role prompt pattern (cf. [[aina-ai2-eight-senior-prompts]]) with output-structure constraints.
- **Photo matching by descriptive filename, not vision**: Claude reads the photo folder's *filenames* (e.g. `coffee-shop-laptop-warm.jpg`) and matches by feel/vibe — sidestepping the cost and complexity of running every image through a vision model. A pragmatic content-routing trick.
- **Playwright MCP for end-to-end browser automation**: the MCP server opens LinkedIn, pastes the post, uploads the photo, handles image resizing, and schedules at the user's default time. The user never touches the LinkedIn UI.
- **Cadence claim**: one Sunday hour produces and schedules a full week of posts. Most LinkedIn creators ship two posts a week if lucky; consistency is the moat, not single-post quality.

## The Author's Framing

> "The accounts that build pipeline aren't the ones with the best single post, they're the ones publishing consistently in a voice that sounds genuinely human every week."

This positions the stack as a **consistency machine** rather than a quality machine — Claude is doing the un-fun work (drafting, photo selection, scheduling, resizing) so the human-loop only handles judgment ("pick the best angle out of three"). It's a **GTM-engineer / founder-creator** workflow, not a content-mill workflow.

## Comments / Pushback

The first reply ([@Prithvi_Jadwani](https://x.com/Prithvi_Jadwani/status/2049934770294116414)) calls it "an AI ghostwriter, not a GTM savior" — a fair pushback. The stack does outsource voice production, even if `profile.md` is meant to keep that voice yours. The line between "scaffolded my voice" and "let an LLM speak for me" is doing a lot of work in the framing. Worth tracking whether `profile.md`/`hooks.md` produces output the author can defend as authentically theirs in 6 months.

## Why It Matters

Three things make this worth filing despite the DM-gate:

1. **profile.md / hooks.md is a clean, named pattern** for voice context that practitioners are starting to converge on — extends the [[julian-goldie-notebooklm-skills-factory]] source-grounded skills pattern with a *named decomposition* (voice context vs. format library, kept as separate files).
2. **Playwright MCP is showing up as the default browser-automation MCP server** in real practitioner workflows (also referenced in [[heygurisingh-career-ops]] for ATS PDF generation). Worth a thin tools/ stub.
3. **Three-draft-per-topic** generalizes — pick-the-best-of-N is a standard technique for any creative task where rejection is cheaper than fixing.

## Pages Updated

- [[claude-code]] — added April 2026 traction signal: profile.md + hooks.md voice-scaffolding pattern; Playwright MCP as the default browser-automation MCP
- [[writing-claude-code-skills]] — added "Voice-Scaffolded Skills (profile.md + hooks.md)" sub-pattern under Source-Grounded Skills
- [[playwright-mcp]] — created (this source is the third practitioner mention, plus career-ops)

## Pages Created

- [[playwright-mcp]] — emerging tool stub
- This source page

## Resources

- Original post: https://x.com/AlfieJCarter/status/2049908404349501820
- Related: [[julian-goldie-notebooklm-skills-factory]] — broader source-grounded skills pattern this extends
- Related: [[heygurisingh-career-ops]] — same week, also Playwright MCP, also a "skill stack" framing
- Related: [[aina-ai2-eight-senior-prompts]] — companion pattern: structured deliverable + role assignment is the same shape as profile.md + hooks.md
