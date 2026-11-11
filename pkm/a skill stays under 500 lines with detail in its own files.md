---
type: pkm
created: 2026-11-11
role: how this vault works
---
# [[a skill stays under 500 lines with detail in its own files]]

- A `SKILL.md` stays under 500 lines, with long detail moved into files beside it
- Part of [[vault skills live in the skills folder]]
- The [Agent Skills spec](https://agentskills.io/specification#progressive-disclosure) asks for under 500 lines and about 5000 tokens, since the whole file loads when an agent picks the skill
- Long reference material goes in `references/`, code in `scripts/`, and templates in `assets/`
- `SKILL.md` links each one by its path from the skill's folder, one level deep, and says when to read it
- [[a skill holds only what an agent needs for the task]] keeps it short in the first place

## Status

- YYYY-MM-DD (kind/agent name): ported and adapted for the template
