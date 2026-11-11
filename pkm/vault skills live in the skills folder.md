---
type: pkm
area: pkm
created: 2026-11-11
role: how this vault works
related:
  - "[[skill files follow the agent skills spec]]"
  - "[[skills have their own review rules]]"
  - "[[skill trigger tests check which prompts open the skill]]"
  - "[[agents find vault skills through local links]]"
  - "[[skills reach other vaults only by hand]]"
---
# [[vault skills live in the skills folder]]

- This vault's own skills live in `skills/<name>/` at the vault root, so Obsidian shows them and Obsidian Sync carries them to every copy
- The folder can also hold general skills that every agent uses in any project
- [[skill files follow the agent skills spec]], with `SKILL.md` and optional `references/`, `scripts/`, and `assets/` in each folder
- Every bot should check [[skills]] before vault or Obsidian-specific work

## skills here

- [[skills]] is the folder's front page, with a Base that finds every `SKILL.md`
- A skill's scripts sit in its `scripts/` folder and find the vault from where they are

## how skills reach agents

- Agents started in a copy of the vault list skills from [[agents find vault skills through local links|local links]]

## naming

- A skill's name says who it's for, not where it lives
- Skills that act on the vault can carry a vault-specific prefix, while general ones get names that stand apart from other tools' skills without one

## Status

- YYYY-MM-DD (kind/agent name): ported and adapted for the template
