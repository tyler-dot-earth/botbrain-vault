---
type: pkm
created: 2026-11-11
role: how this vault works
---
# [[a skill's description says what it does and when to use it]]

- A skill's `description` says what it does and when an agent should use it, since that's all an agent sees when choosing
- Part of [[vault skills live in the skills folder]]

## why it matters

- Agents load only each skill's `name` and `description` at startup, and read `SKILL.md` only after picking it, per the [Agent Skills spec](https://agentskills.io/specification#progressive-disclosure)
- So a description that skips the "when" leaves a skill unused

## what it says

- What the skill does, in one plain sentence about the task, not its steps
- When to use it, with the situations and words that should call it up, like "Use when {owner} shares a URL and asks to save it"
- Enough to tell it apart from a nearby skill, so the wrong one doesn't fire
- Under 1024 characters

---

## Status

- YYYY-MM-DD (kind/agent name): ported and adapted for the template
