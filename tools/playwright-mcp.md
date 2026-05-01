---
name: Playwright MCP
type: tool
category: api
status: emerging
last_updated: 2026-05-01
---

## What It Is

**Playwright MCP** is an MCP ([[mcp]]) server that exposes the [Playwright](https://playwright.dev/) browser-automation library to Claude (and other MCP clients). Lets Claude open browser tabs, click, fill forms, paste content, upload files, and resize images — driving real web interfaces end-to-end without the user touching the browser.

The official package is published by Microsoft at [`@playwright/mcp`](https://github.com/microsoft/playwright-mcp). It is the **default browser-automation MCP** showing up in real April 2026 practitioner workflows; this page exists to track that pattern, not to provide a configuration tutorial (yet).

## Traction Signals

- **April 2026 — three independent practitioner stacks in two weeks** (third signal arrived end of April):
  - [[heygurisingh-career-ops]] uses Playwright MCP for ATS-optimized PDF generation (Space Grotesk + DM Sans) inside an open-source job-search system at 8.2k GitHub stars.
  - [[alfiejcarter-linkedin-claude-stack]] uses Playwright MCP to open LinkedIn, paste posts, upload photos, handle resizing, and schedule at default posting time — full end-to-end browser automation from a Claude Code skill.
  - [[seelffff-personal-ai-agent]] uses Playwright MCP from [[claude-desktop]] (not [[claude-code]]) for daily life-management commands: TechCrunch headlines, Polymarket odds, X trending topics, multi-source research. Consumer-grade use; expands the user base from "developer building production skills" to "anyone with Claude Pro."
- **Cross-host validation**: Playwright MCP now sees independent practitioner use from both [[claude-code]] (career-ops, LinkedIn stack) and [[claude-desktop]] (seelffff). Cross-host adoption is a stronger signal than within a single host.
- All three practitioners describe Playwright MCP as a default, not a debated choice. The **MCP-server-for-browser-automation niche has consolidated around this single implementation** rather than fragmenting across Selenium/Puppeteer wrappers.
- Microsoft maintenance + Playwright's existing TypeScript-first developer story make it the path-of-least-resistance MCP for any agent that needs a real browser.

> [!note] Status review
> With three independent practitioner uses across two MCP hosts, this tool is on the boundary between `emerging` and `gaining-traction`. Holding at `emerging` for now pending first-hand wiki-owner use; promote on the next ingest if a fourth signal lands or owner builds a workflow.

## How to Use It

The two referenced practitioner uses (above) install Playwright MCP and configure it in Claude Code's MCP settings, then write skill files that invoke browser actions via MCP tool calls. **No first-hand walkthrough captured yet** — this page is a stub pending hands-on use by the wiki owner.

For a starting point, Microsoft's repo at https://github.com/microsoft/playwright-mcp has install instructions and example configurations.

## Key Concepts

- **MCP server** — see [[mcp]]; the server exposes Playwright as a set of tool calls (open URL, click, type, screenshot, upload, etc.) callable by any MCP-compatible client.
- **Browser as agent surface** — many real-world agent workflows hit a hard wall when they need a *real* browser session (logged-in LinkedIn, ATS upload, dynamic JS pages). Playwright MCP is the bridge.
- **Headless vs. headed** — Playwright supports both; for skills that publish content to logged-in services (LinkedIn, internal SaaS), a persistent headed session keeps cookies alive.

## Compared To

- **Bash + curl / web scraping**: works for static GET requests; falls apart on JS-heavy sites, logged-in sessions, file uploads, captchas, and dynamic content.
- **Custom Selenium / Puppeteer wrappers as MCP servers**: pre-Playwright-MCP, practitioners wrote their own; the existence of Microsoft's published `@playwright/mcp` is what made the niche converge.
- **Web-scraping APIs (Browserbase, Browserless, etc.)**: hosted browser-as-a-service alternatives. Playwright MCP runs locally so credentials and cookies stay on-device — a privacy/security tradeoff.
- **Computer-use models (Claude Sonnet computer use, OpenAI Operator)**: Claude-driven *vision-based* GUI automation, which is more flexible but slower, more expensive, and more error-prone than DOM-level Playwright automation. Playwright MCP wins when the target is a known web app; computer use wins for arbitrary desktop apps.

## Caveats

- **First-party MCP, but practitioner workflows are early.** Both April 2026 references are from individual practitioners, not enterprise deployments. Status: `emerging`, not yet `gaining-traction`.
- **No first-hand experience documented in this wiki.** Promote to `gaining-traction` after the wiki owner builds a workflow using it, or after a third independent traction signal arrives.

## Resources

- Microsoft repo: https://github.com/microsoft/playwright-mcp
- Playwright docs: https://playwright.dev/
- [[heygurisingh-career-ops]] — career-ops uses Playwright MCP for ATS PDF generation
- [[alfiejcarter-linkedin-claude-stack]] — LinkedIn posting stack uses Playwright MCP for end-to-end publishing
- [[seelffff-personal-ai-agent]] / [[personal-ai-agent-claude-desktop-mcp]] — Claude Desktop life-management agent using Playwright MCP for browsing TechCrunch / X / Polymarket
- Related: [[mcp]] — the underlying protocol; [[claude-code]] and [[claude-desktop]] — both clients integrating Playwright MCP in real workflows
