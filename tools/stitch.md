---
name: Stitch / DESIGN.md
type: tool
category: platform
status: emerging
last_updated: 2026-04-24
---

## What It Is
Stitch is a Google Labs tool for AI-assisted design workflows. In April 2026, Google open-sourced its `DESIGN.md` specification format — a portable, vendor-neutral way to define and export design rules across projects and tools. The core idea: instead of AI agents guessing design intent, they read a `DESIGN.md` file that encodes your design system rules explicitly.

## Traction Signals
- Google open-sourced the draft DESIGN.md spec in April 2026 via official Google Labs blog announcement — [[datachaz-google-design-md]]
- Positioned as a direct competitive move against Anthropic's Claude Design rate limits
- Official @stitchbygoogle account announced; spec designed to work across any tool or platform

## How to Use It
- Define your design rules in a `DESIGN.md` file at the project root
- Export/import rules across projects for consistency
- Any agent or tool that respects the spec can read your design intent without requiring inline prompting each session
- GitHub repo: https://github.com/google-labs-code/design.md

## Key Concepts
- **DESIGN.md**: markdown spec file encoding design rules (colors, components, constraints, naming conventions) in a format agents can read
- **Portability**: same design rules travel with your project across tools — no re-explaining design system per session

## Compared To
- **CLAUDE.md**: Anthropic's project-level instruction file for Claude Code; DESIGN.md is the same pattern applied to design rules specifically
- **Claude Design** (Anthropic): AI design tool that prompted Google's response; has rate limits that DESIGN.md's open spec tries to undercut
- **Cursor rules / `.cursorrules`**: per-project coding conventions for Cursor — conceptually analogous but scoped to code style, not design

## Community Sentiment
- April 2026: one commenter called it "a glorified markdown doc with a linter" — skepticism about technical novelty; the value may be in standardization/adoption rather than innovation — [[datachaz-google-design-md]]

## Resources
- [[datachaz-google-design-md]] — @DataChaz X post announcing the open-source release; competitive framing
