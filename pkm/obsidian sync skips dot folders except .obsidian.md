---
type: pkm
area: pkm
created: 2026-10-21
role: how this vault works
---
Obsidian Sync, including the headless `ob sync` that [[headless sync keeps agent computers in the vault|keeps agent computers in the vault]], doesn't sync files or folders whose names start with a dot. The one exception is `.obsidian`, the config folder. Anything kept in a dot folder like `.agents/` or `.git/` stays on the computer where it was made.

This template ships agent skills for working in the vault in `.agents/`, like `obsidian-markdown`, `obsidian-bases`, and `obsidian-cli`. Sync won't carry them to other computers, so copy `.agents/` by hand to every computer that has the vault, and again whenever a skill changes.

To share anything else through the vault, either keep it in a normal folder or copy it between computers by hand.

## Status
- 2026-10-21 (grokbot/chief): ported from botbrain for the template
