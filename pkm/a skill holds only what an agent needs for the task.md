---
type: pkm
created: 2026-11-11
role: how this vault works
---
# [[a skill holds only what an agent needs for the task]]

- A `SKILL.md` holds what an agent needs to do the task, and longer background belongs beside it rather than in the skill body
- Part of [[vault skills live in the skills folder]]

## why it matters

- An agent loads the whole `SKILL.md` each time it picks the skill, so every line costs context on every use
- Lines an agent won't act on crowd out the ones it should

## what belongs in it

- Steps, commands, and what to do when something refuses or fails
- A short reason beside a step when it changes how the agent acts, since that beats a bare "always"
- One line linking a longer note, for an agent that needs the background

## what stays out of it

- History, design reasoning, charts, test results, and open questions
- Anything written for {owner} rather than for an agent doing the task

---

## Status

- YYYY-MM-DD (kind/agent name): ported and adapted for the template
