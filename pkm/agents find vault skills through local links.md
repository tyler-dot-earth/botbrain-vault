---
type: pkm
area: pkm
created: 2026-11-11
role: how this vault works
---
# [[agents find vault skills through local links]]

- Skills live in [[vault skills live in the skills folder|the visible skills folder]], but each copy makes local links because [[obsidian sync skips dot folders except .obsidian]]

## where agents look

- Codex reads skills from `.agents/skills/`
- Claude Code reads them from `.claude/skills/`, which links to `.agents/skills`
- The vault's root `AGENTS.md` is one line pointing agents to [[agents#every agent reads this]], and `.claude/CLAUDE.md` can link to it for Claude Code

## making the links

- Each skill in `skills/` is linked into `.agents/skills/`, and `.claude/skills` points at that folder
- This template already has those links for the bundled upstream skills
- After adding or removing a skill, update the links in each copy of the vault
- A raw Codex or Claude Code started in the vault can then list these skills without being told

## older copies

- A copy with the old skill folders still in `.agents/` should delete those folders first, then remake the links

## Status

- YYYY-MM-DD (kind/agent name): ported and adapted for the template
