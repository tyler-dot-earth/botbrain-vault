---
type: pkm
created: 2026-10-15
updated: 2026-10-21
role: how this vault works
---
# [[about daily]]

This folder holds daily notes, one per day, named like `YYYY-MM-DD`. The Periodic Notes community plugin (by Liam Cain) creates them here, configured for daily notes only. The morning brief seeds each one.

Items get checked off where they are. Nothing moves between sections

The core Daily notes plugin is turned off on purpose, so Periodic Notes is the only daily notes system. Leave it off.

## activity

- Agents write what they did at the bottom of that day's note, under `## activity`, instead of in separate log notes
- One short bullet per thing done, starting with the local time and signer, with the agent name as a wikilink to its `agents/` note so renames carry through, like `- 5:37pm (grokbot/[[example agent]]): ...`, with wikilinks to the notes it touched
- Only things worth knowing later, like a decision trail, a finding, or context a future reader needs. Skip retries, routine no-ops, and logging for its own sake
- If the day's note doesn't exist yet, create it with frontmatter and just the `## activity` section
- Agents add their own bullets and never edit other lines

## Status
- YYYY-MM-DD (kind/agent name): created with the daily notes setup
- 2026-10-21 (grokbot/chief): agent activity moved to short `## activity` bullets with a linked agent name, only when useful
