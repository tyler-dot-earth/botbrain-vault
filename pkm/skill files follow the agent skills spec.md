---
type: pkm
area: pkm
created: 2026-11-11
role: how this vault works
---
# [[skill files follow the agent skills spec]]

- Skills in [[vault skills live in the skills folder|the vault's skills folder]] follow the [Agent Skills spec](https://agentskills.io/specification)

## file format

- A `SKILL.md` has no `type`, `created`, H1 self-link, or Status lines, since [[a skill holds only what an agent needs for the task]]
- Its `name` matches its folder in lowercase hyphenated words
- [[a skill's description says what it does and when to use it]], since that's how agents choose it
- Extra fields such as a source URL go in `metadata` as strings, since the spec allows no extra top-level keys

## linking

- Every skill file is `SKILL.md`, so link one by its path, like `![[skills/obsidian-cli/SKILL]]`

## Status

- YYYY-MM-DD (kind/agent name): ported and adapted for the template
