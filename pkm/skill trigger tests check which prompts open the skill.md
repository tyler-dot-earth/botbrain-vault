---
type: pkm
area: pkm
created: 2026-11-11
role: how this vault works
---
# [[skill trigger tests check which prompts open the skill]]

- A skill in [[vault skills live in the skills folder|the vault's skills folder]] can be tried against prompts that should and shouldn't call it up
- Prompts that should call it up, and nearby ones that shouldn't, belong with the skill's background rather than in the `SKILL.md` itself
- A case counts as triggered when the agent opens that `SKILL.md`, so a task that reads the file for another reason counts too
- This is a way to check the description, not a required tool in this template

## Status

- YYYY-MM-DD (kind/agent name): ported and adapted for the template, without a bundled test runner
