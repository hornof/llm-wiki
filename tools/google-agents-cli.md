---
name: Google Agents CLI (google/agents-cli)
type: tool
category: cli
status: gaining-traction
last_updated: 2026-10-02
---

## What It Is

**google/agents-cli** is Google's CLI + 7 bundled skills that turn **any coding assistant** into an expert at creating, evaluating, and deploying AI agents on Google Cloud. Launched 2026-06-27 ([[google-agents-cli-launch-akshay-pachaar-walkthrough-2026-06-27]]). One install injects the skills into every coding agent at once — [[antigravity|Antigravity]], [[claude-code|Claude Code]], [[codex|Codex]], or any other.

## How to Use It

- Install: `uvx google-agents-cli setup` (installs skills across every coding agent); skills-only: `npx skills add google/agents-cli`.
- **The 7 skills**: workflow (dev lifecycle, code-preservation rules, model selection) · adk-code (ADK Python API) · scaffold · eval (LLM-as-judge + adaptive rubrics) · deploy (Agent Runtime, Cloud Run, GKE, CI/CD) · publish (Gemini Enterprise registration) · observability (Cloud Trace + logging).
- **6 CLI commands**: setup, scaffold, eval-generate, eval-grade, deploy, publish-gemini-enterprise.
- Walkthrough workflow (per the launch clip): Install → Build → Test locally → Evaluate → Deploy → Register to Gemini Enterprise.

## Why It Matters

The vendor-tier version of the skill-substrate pattern ([[dac]] pioneered it): methodology shipped as cross-agent markdown skills rather than a proprietary harness — Google betting horizontal (works in every agent) where [[claude-agent-sdk|Anthropic's SDK]] bets vertical.

## Unverified

Pricing/billing, adoption metrics, and the Karpathy survey figures the launch coverage cited (89% observability vs 52% evals) — source citation never found.

## Resources

- GitHub: https://github.com/google/agents-cli · Docs: https://google.github.io/agents-cli/
- [[google-agents-cli-launch-akshay-pachaar-walkthrough-2026-06-27]] · [[google]] · [[antigravity]] · [[agentic-engineering]]

> Page history: rewritten 2026-10-02 — the 2026-06-29 version was corrupted with "canonical-" filler from an automated pass.
