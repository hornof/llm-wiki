---
title: "Equipping agents for the real world with Agent Skills"
type: source
medium: article
url: https://www.anthropic.com/research/equipping-agents-for-the-real-world-with-agent-skills
ingested: 2026-11-12
---

## Summary

[[anthropic|Anthropic]] Engineering's launch post for Agent Skills (2025-10-16; Barry Zhang, Keith Lazuka, Mahesh Murag). It defines the format, explains progressive disclosure with the PDF skill as the example, and gives authoring and security advice. The wiki had covered the standard's later history but not this founding post. A note on the page records the 2025-12-18 release as an open standard. Found via [[godsystemsmd-skills-are-the-prompts-2026-11-05]].

## Key Claims / Takeaways

- **Definition:** *"organized folders of instructions, scripts, and resources that agents can discover and load dynamically to perform better at specific tasks."* The analogy is *"an onboarding guide for a new hire."*
- **Progressive disclosure, three levels.** *"At startup, the agent pre-loads the name and description of every installed skill into its system prompt."* The body loads when relevant, and bundled files load only when needed, so *"the amount of context that can be bundled into a skill is effectively unbounded."*
- **Code inside skills** is for work that should be deterministic. The PDF skill's form-field script runs *"without loading either the script or the PDF into context."*
- **Authoring advice:** *"Start with evaluation"*, split files when SKILL.md grows, watch the name and description closely, and *"ask Claude to capture its successful approaches and common mistakes into reusable context and code within a skill."*
- **Security:** *"malicious skills may introduce vulnerabilities in the environment where they’re used or direct Claude to exfiltrate data and take unintended actions."* Install only from trusted sources and audit the rest.
- **Stated direction:** *"we hope to enable agents to create, edit, and evaluate Skills on their own"*.
- **Read beside Perplexity's guide:** both start from evals and both treat the description as the trigger. They differ on who should write the skill. Anthropic suggests having Claude capture it; Perplexity, citing SkillsBench, argues model-written skills don't help. [Judgment; see [[skill-md]].]

## Pages Updated

- [[skill-md]] — new 2026-11-12 section
