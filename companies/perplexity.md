---
name: Perplexity
type: company
focus: AI search; agent products (Perplexity Computer)
status: gaining-traction
last_updated: 2026-11-12
---

## What It Is

**Perplexity** is an AI search company led by CEO **[[aravind-srinivas|Aravind Srinivas]]**. It uses models from several labs (GPT, Claude Opus and Claude Sonnet orchestrate its agent product), and a Reddit commenter describes it as a company that "doesn't make models". Forbes's 2026 AI 50 lists it at $1.7B raised ([[forbes-ai-50-2026]]). Its agent product, Perplexity Computer, runs on a curated library of Agent Skills ([[perplexity-agent-skills-guide-2026-05-01]]).

The wiki tracks it for two things: Srinivas's argument that the model is no longer the product, and the company's published practice for writing agent skills.

*(Rewritten 2026-11-12 against its sources to remove automated-pass filler. The earlier version gave a "$20B valuation" as fact; that figure comes only from a Reddit post's title. It also attributed lines to Srinivas that the post's author wrote. Both are corrected below.)*

## Traction Signals

- **2026-05-01: published its internal Agent Skills guide** ([[perplexity-agent-skills-guide-2026-05-01]]). Perplexity Computer runs on a curated skills library, including tax skills nested three levels deep, and evaluates skill loading across GPT, Claude Opus and Claude Sonnet orchestrators. See [[skill-md]].
- **2026-06-24: Srinivas on 20VC, via Reddit** ([[srinivas-perplexity-20vc-model-not-product-2026-06-24]]). An r/ArtificialInteligence post summarizes a 95-minute interview in which, per the poster, Srinivas argued that the value is in the layer around the model and that the market *"looks more like Salesforce than Google"*: many workflows customers get locked into, not one product everyone uses. The interview wasn't watched. The post's title calls Perplexity a "$20B AI company", which no other source in the wiki confirms. The lines about "boring glue" and swapping models by Friday are the poster's own, not Srinivas's.
- **A user's counterpoint in the same thread:** one Pro subscriber said they hadn't touched Perplexity in weeks since Google put Gemini into Search, and didn't plan to renew. Another commenter noted that a CEO whose company doesn't make models has a reason to say models don't matter. One anecdote, not a churn figure.
- **2026-05-20: named as an agent-search API** alongside Brave Search API and Tavily, in the brief item on Exa ([[dailybrief-roundup-2026-05-20]]).

## Key People

- **[[aravind-srinivas|Aravind Srinivas]]**: CEO.

## How to Use It

- AI search, on the web and through the Perplexity Search API for agents.
- Perplexity Pro is the paid tier. Its pricing and features aren't recorded in the wiki.
- Perplexity Computer is its agent product. The [[perplexity-agent-skills-guide-2026-05-01|skills guide]] is useful to anyone writing skills, whether or not they use Perplexity.

## Compared To

- **[[google]]**: Gemini in Search competes directly with Perplexity's core product, as the subscriber's comment above illustrates.
- **[[anthropic]]**: the clearest contrast to Srinivas's thesis. Anthropic pairs its own models with its own harness (Claude and [[claude-code|Claude Code]]), which one Reddit commenter called the vertical alternative. If owning both the model and the harness wins, labs win; if the layer is interchangeable across models, companies like Perplexity do. See [[anthropic-claude-tag-slack-65-percent-prs-2026-06-23]] and [[silicon-vertical-integration-2026-06-24-openai-jalapeno-qualcomm-modular-cluster]] for the vertical side.

## Resources

- [[perplexity-agent-skills-guide-2026-05-01]]: how Perplexity writes, evaluates and maintains Agent Skills
- [[srinivas-perplexity-20vc-model-not-product-2026-06-24]]: Reddit summary of Srinivas's 20VC interview
- [[forbes-ai-50-2026]]: funding figure
- [[dailybrief-roundup-2026-05-20]]: agent-search API category
- [[block-builderbot-launch-2026-06-17]]: an in-house agent layer at Block, cited in the same vertical-vs-horizontal debate
