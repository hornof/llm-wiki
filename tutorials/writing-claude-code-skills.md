---
name: Writing Effective Claude Code Skills
type: tutorial
tool: claude-code
difficulty: intermediate
last_updated: 2026-04-30
---

## Goal

Write Claude Code slash commands (skills) that fire reliably, produce consistent output, and compound into a skill library that improves overall routing accuracy.

## Prerequisites

- Claude Code CLI installed and working (`npm install -g @anthropic-ai/claude-code`)
- Basic familiarity with Markdown and YAML frontmatter

## Skill File Structure

Skills live at `~/.claude/skills/<skill-name>/SKILL.md` and are invoked as `/<skill-name>` or auto-loaded when Claude's context matches the description.

```
~/.claude/skills/
├── commit/SKILL.md          → /commit
├── code-review/SKILL.md     → /code-review
└── deploy/
    ├── SKILL.md             → /deploy
    └── scripts/helper.sh    (supporting files)
```

## The 6 Patterns

### Pattern 1: Description tells Claude WHEN, not just WHAT

The description is scanned before Claude decides which skill to load. Front-load the use case and trigger keywords in the first 250 characters — that's the context budget.

**Bad:**
```
description: Code review tool
```

**Good:**
```
description: Review code for bugs, security issues, and maintainability.
Use when reviewing pull requests, checking code quality, analyzing diffs,
or when user mentions "review", "PR", "code quality", or "best practices".
```

Skills with descriptions under 50 characters are invoked 3-5x less often.

### Pattern 2: Be directive, not conversational

Skills are instructions, not chat. Use imperative verbs and numbered steps.

**Weak:**
```
Could you please review the code? Maybe check if there are any bugs?
```

**Strong:**
```
Review the current diff. Check for:
1. Security vulnerabilities (OWASP Top 10)
2. Performance issues (N+1 queries, blocking calls)
3. Code style violations

Output as a checklist with severity ratings.
```

### Pattern 3: Specify the output format

Without an explicit format, Claude invents a new one each time. Define the exact structure.

**Without format:**
```
Generate a commit message for these changes.
```
→ Sometimes one line, sometimes paragraphs, sometimes with prefixes.

**With format:**
```
Generate a commit message in this exact format:

type(scope): short description

- Bullet of what changed
- Bullet of why it changed

Type: feat | fix | refactor | docs | test | chore
Scope: affected module name
Description: under 50 characters, present tense, lowercase
```

### Pattern 4: Include a "read first" step

Tell Claude to inspect your project before generating output. This is what separates project-aware output from generic code that breaks your linter.

```
Before writing tests:
1. Read the target file to understand function signatures and types
2. Find the existing test directory and read 1-2 existing tests
3. Identify the testing framework (Jest, Vitest, Pytest, etc.)
4. Note the import style and assertion patterns

Then generate tests matching those exact patterns.
```

### Pattern 5: Define what the skill does NOT do

Listing out-of-scope tasks prevents wrong-skill invocations and broken outputs. Appears in 70% of high-quality skills, almost never in low-quality ones.

```
## Out of Scope

This skill does NOT:
- Push to remote (use /push or git push manually)
- Create PRs (use /pr skill)
- Handle merge conflicts
```

### Pattern 6: Keep it under 500 lines

Every skill loads into Claude's context when invoked. Long skills eat tokens and cause Claude to lose focus and ignore bottom instructions.

For complex skills, use progressive disclosure:

```
SKILL.md            (under 200 lines — always loaded)
├── ADVANCED.md     (loaded only when task needs it)
├── REFERENCE.md    (loaded only when referenced)
└── EXAMPLES.md     (loaded only when Claude needs examples)
```

Reference sub-files in SKILL.md:
```
For complex cases, see [ADVANCED.md](ADVANCED.md)
For full API reference, see [REFERENCE.md](REFERENCE.md)
```

## A Complete Example: /commit

```
---
name: commit
description: Create structured git commits from current changes.
Use when user says "commit", "save changes", "commit this", or after
finishing a feature. Breaks changes into logical units with clear messages.
---

Create commits from current git state.

## Process

1. Run `git status` and `git diff` to see all changes
2. Group related changes into logical units (one feature = one commit)
3. For each unit, generate a commit message:

   type(scope): short description

   - What changed
   - Why it changed (if not obvious)

4. Stage and commit each unit: `git add` then `git commit`
5. Show summary: "Created N commits: [list of titles]"

## Rules

- Type: feat | fix | refactor | docs | test | chore
- Description: under 50 chars, lowercase, present tense
- Never combine unrelated changes in one commit

## Out of Scope

- Pushing to remote (use /push or git push manually)
- Creating PRs (use /pr skill)
- Merging branches
```

## Source-Grounded Skills (NotebookLM Pattern)

The 6 patterns above govern *skill structure*. A complementary practice — circulated by @JulianGoldieSEO in April 2026 — addresses *skill provenance*: where the recipe inside a skill comes from. The pattern uses NotebookLM as a source-curation layer whose grounding-on-sources behavior is reused to author the skill itself.

The five-step loop:

1. Open NotebookLM and add the canonical sources for the task — PDFs, articles, YouTube transcripts, internal docs.
2. Ask NotebookLM to write a `skill.md` file based **only** on those sources. Constrain it to the patterns above (description with trigger keywords, numbered imperative steps, explicit output format, "read first" step, out-of-scope list).
3. Drop the generated file into `~/.claude/skills/<skill-name>/SKILL.md`.
4. Claude follows the recipe every time the skill is invoked. Hallucinations drop because the recipe inherits NotebookLM's source grounding.
5. One skill per job — email composition, landing page, FAQ, support reply — and stack them. Practitioners report ~10 stacked skills functioning as a "mini AI team," substituting for re-explaining context every session.

When this is worth the extra step: tasks where wrongness is expensive (legal, medical, brand voice, customer-specific tone) and where the canonical sources fit inside a NotebookLM notebook. For tasks where the right answer is structural rather than evidential (a /commit skill, a /pr skill), source-grounding adds little.

Mixed-source notebooks work: practitioners confirm YouTube transcripts + PDFs + articles compose well as a single grounding set. Source: [[julian-goldie-notebooklm-skills-factory]].

## Diagnosing Broken Skills

Run through this checklist against any skill that Claude never invokes:

```
1. Description: At least 3 trigger keywords?
2. Description: Use case in the first 250 characters?
3. Instructions: Imperative verbs in numbered steps?
4. Output: Format specified explicitly?
5. Project awareness: Does it tell Claude to read existing files first?
6. Scope: Does it list what the skill does NOT do?
7. Length: Is SKILL.md under 500 lines?
```

Fix failing items. Then test by asking Claude something the skill should handle *without* invoking it manually. If Claude picks the right skill, the description is working.

## What I Actually Learned

*(To be filled in after building a personal skill library.)*

## Next Steps

- Build `/review`, `/commit`, and `/deploy` as a starting set
- After 5+ skills exist, test cross-skill routing (does Claude pick the right one without manual invocation?)
- Read: [[zodchiii-anatomy-perfect-skill]] — source this tutorial is based on

## Resources

- [[zodchiii-anatomy-perfect-skill]] — source thread; 6-pattern framework
- [[julian-goldie-notebooklm-skills-factory]] — NotebookLM-as-skills-factory pattern; source-grounded skill.md authoring
- [[claude-code]] — parent tool page
