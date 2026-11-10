---
title: "Quoting Prompting Claude Fable 5.2 (Simon Willison)"
type: source
medium: article
url: https://simonwillison.net/2026/Nov/10/prompting-claude-fable-52/
ingested: 2026-11-10
---

## Summary

[[simon-willison|Simon Willison]] quotes Anthropic's "Prompting Claude Fable 5.2" documentation (2026-11-10). The point: Fable 5.2 changes how it treats a codebase depending on whether the prompt says the code is its own. The Anthropic docs page itself wasn't fetched.

## Key Claims / Takeaways

- **The effect.** *"Claude Fable 5.2 responds closely to what the prompt says about who owns the code it works on."* If the prompt says nothing, or calls the code someone else's, the model *"tended to add to the existing structure, even when that repeated existing code."*
- **The suggested sentence:** *"This codebase is yours: what it's for and how it's built are your call, and you'll keep building on it."*
- **Size of the effect.** The model *"merged repeated code in about half of the tries with this sentence, and in under a tenth of the tries without it."* Anthropic tested this on small coding tasks only.
- **Use.** Worth adding to a CLAUDE.md for a repo you want the agent to refactor freely. Leave it out where you want minimal, additive diffs. [Judgment.]

## Pages Updated

- [[claude-fable-5]] — When to Use It (ownership prompt)
