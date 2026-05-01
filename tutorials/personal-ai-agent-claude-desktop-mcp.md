---
name: Personal AI Agent on Claude Desktop + MCP
type: tutorial
tool: claude-desktop
difficulty: beginner
last_updated: 2026-05-01
---

## Goal

Build a personal life-management agent using only [[claude-desktop]] and three [[mcp]] servers (Filesystem, [[playwright-mcp]], a custom 25-line Telegram). After setup, you type short commands (`gm`, `done: gym`, `x post idea`, `evening review`) and the agent reads/writes local markdown files, browses real websites, and pushes results to your phone via Telegram.

Total incremental cost: $0 on top of an existing Claude Pro subscription. Setup time: 20–30 minutes.

Source: [[seelffff-personal-ai-agent]] (April 2026 X tutorial). This page is the wiki-side, source-cited derivative — *not* a first-hand walkthrough yet (the wiki owner has not personally followed this tutorial as of 2026-05-01; see "What I Actually Learned" below).

## Prerequisites

- Claude Pro subscription (~$20/mo)
- macOS or Windows with [Claude Desktop](https://claude.ai/download) installed
- Node.js installed locally (verify with `node --version`)
- A free Telegram account and access to [@BotFather](https://t.me/BotFather)

## Architecture

```
YOU → Claude Desktop (the brain)
        ├── Filesystem MCP   → ~/agent-system/
        │                          ├── CLAUDE.md     (agent instructions)
        │                          ├── tasks.md      (daily habits checklist)
        │                          ├── context.md    (about you)
        │                          └── notes.md      (research output)
        ├── Playwright MCP   → real Chrome (TechCrunch, X, Polymarket, any site)
        └── Telegram MCP     → your phone (push notifications)
```

The agent runs locally. The only external traffic is the Telegram message itself.

## Steps

### 1. Create a Telegram bot

1. Open Telegram, search for `@BotFather`, send `/newbot`, give it a name.
2. Copy the **bot token** (looks like `1234567890:ABCdef...`). Treat as a password — revoke via `/revoke` in BotFather if it leaks.
3. Send any message to your new bot, then visit `https://api.telegram.org/botYOUR_TOKEN/getUpdates` and grab the `id` field inside the `chat` object — that's your **CHAT_ID**.

### 2. Build the Telegram MCP server (25 lines)

```bash
mkdir -p ~/.mcp-servers/telegram
cd ~/.mcp-servers/telegram
npm init -y
npm install @modelcontextprotocol/sdk zod
```

Create `server.js`:

```javascript
import { McpServer } from "@modelcontextprotocol/sdk/server/mcp.js";
import { StdioServerTransport } from "@modelcontextprotocol/sdk/server/stdio.js";
import { z } from "zod";

const BOT_TOKEN = process.env.BOT_TOKEN;
const CHAT_ID   = process.env.CHAT_ID;

const server = new McpServer({ name: "telegram", version: "1.0.0" });

server.tool(
  "send_telegram_message",
  { message: z.string().describe("Message to send") },
  async ({ message }) => {
    const url = `https://api.telegram.org/bot${BOT_TOKEN}/sendMessage`;
    await fetch(url, {
      method: "POST",
      headers: { "Content-Type": "application/json" },
      body: JSON.stringify({ chat_id: CHAT_ID, text: message, parse_mode: "HTML" })
    });
    return { content: [{ type: "text", text: "Message sent." }] };
  }
);

const transport = new StdioServerTransport();
await server.connect(transport);
```

Add `"type": "module"` to `package.json`.

### 3. Configure Claude Desktop's MCP servers

Edit `~/Library/Application Support/Claude/claude_desktop_config.json` (macOS):

```json
{
  "mcpServers": {
    "playwright": {
      "command": "npx",
      "args": ["@playwright/mcp@latest"]
    },
    "filesystem": {
      "command": "npx",
      "args": [
        "-y",
        "@modelcontextprotocol/server-filesystem",
        "/Users/yourname/agent-system"
      ]
    },
    "telegram": {
      "command": "node",
      "args": ["/Users/yourname/.mcp-servers/telegram/server.js"],
      "env": {
        "BOT_TOKEN": "YOUR_BOT_TOKEN",
        "CHAT_ID":   "YOUR_CHAT_ID"
      }
    }
  },
  "preferences": { "allowAllBrowserActions": true }
}
```

### 4. Create the four-file agent folder

```
~/agent-system/
├── CLAUDE.md     ← instructions (next step)
├── tasks.md      ← daily habits checklist
├── context.md    ← background about you
└── notes.md      ← agent writes here
```

`tasks.md` example:

```text
# Daily Habits
- [ ] ML Course (1 lesson)
- [ ] Post on X
- [ ] Gym
- [ ] Reading (30 min)
- [ ] Water (2L)
```

`context.md` example: a short paragraph about you — goals, focus, voice. The agent reads this before generating personalized output.

### 5. Write `CLAUDE.md` — the agent's brain

The full source `CLAUDE.md` is in [[seelffff-personal-ai-agent]]. Core structure:

```text
# MY PERSONAL AI AGENT — Operating Instructions

You are my personal life agent. You help me stay focused, informed,
and consistent with my habits.

## CORE RULES
1. After every command, send the result to Telegram. Never skip this.
2. Be direct. No filler, no disclaimers.
3. When you need data from a website, use Playwright — don't guess.
4. Read context.md before generating any personalized content.

## COMMANDS

### gm
Morning briefing: open TechCrunch via Playwright, get 3 top AI/tech
stories. Read tasks.md, list unchecked habits. Add one motivational
line based on context.md. Send to Telegram.

### done: [task]
Find [task] in tasks.md and mark complete (change [ ] to [x]).
Confirm and send to Telegram.

### evening review
Read tasks.md, summarize wins, what was missed, and one improvement
for tomorrow. Send to Telegram.

### research [topic]
Browse 3 sources via Playwright, synthesize, save to notes.md, send
summary to Telegram.

### x post idea
Read context.md for voice/niche. Browse trending tech on X. Write 3
post hooks: contrarian, personal-story, "here's what I learned."
Send all to Telegram.
```

### 6. Restart Claude Desktop, create a Project, add the folder

Restart Claude Desktop. Create a new **Project** and attach `~/agent-system` to it — Projects auto-read project files at session start, which is what gives the agent persistent memory across sessions.

### 7. Type `gm` and check your phone

The agent reads `CLAUDE.md`, sees the `gm` definition, opens a real Chrome via Playwright, fetches today's TechCrunch headlines, reads `tasks.md` for unchecked habits, formats the briefing, and sends to your Telegram. ~30–60 seconds.

## What I Actually Learned

> [!note] Not yet first-hand
> The wiki owner has not yet personally followed this tutorial. This page is sourced entirely from [[seelffff-personal-ai-agent]] (April 30, 2026). After hands-on use, replace this section with first-person notes on friction points, surprises, and changes worth making.

Open questions to resolve when actually building it:
- How well does Claude Desktop's Project memory survive across long-running sessions vs. fresh sessions? Worth comparing against [[claude-code]]'s session model.
- Is the "scheduled morning briefing at 7am" capability that the source claims for Claude Desktop actually present in the current desktop app? The seelffff post implies it is — verify.
- How brittle is Playwright-driven scraping against TechCrunch / X / Polymarket DOM changes? Is there a graceful-failure pattern for skill commands?
- Does the agent ever bypass step 1 of CORE RULES (always send to Telegram)? If so, what's the recovery pattern?

## Next Steps

After the basic stack works:

- **Scheduled morning briefing** — the source claims Claude Desktop supports scheduled tasks natively; auto-trigger `gm` at 7am.
- **Weekly review** — agent compares this week's habit completion to last week and surfaces patterns.
- **X-post drafting** — agent writes a full draft, saves to a `drafts.md`, you review before publishing.
- **Learning tracker** — log ML lessons completed; weekly study report.
- **Mood log** — daily one-line description, agent surfaces patterns over time.

Each addition is a new section in `CLAUDE.md` and (sometimes) a new MCP server.

## Related

- [[claude-desktop]] — the host
- [[mcp]] — the protocol
- [[playwright-mcp]] — the browser-automation MCP (third independent practitioner use, contributing toward `gaining-traction` promotion)
- [[company-brain]] — the same factual-memory pattern at enterprise scale ([[ashwingop]] / [[sentra]]); useful conceptual contrast for what this stack would have to add to scale beyond a single user
- [[claude-code]] — sibling harness; same CLAUDE.md schema-driven configuration philosophy
- [[tomcrawshaw-claude-code-blueprint]] — independent corroboration of CLAUDE.md as the central control surface ("the trick that makes Claude predictable, not chaotic")
