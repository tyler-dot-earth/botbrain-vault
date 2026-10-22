---
type: pkm
created: 2026-10-21
role: how this vault works
---
Agents read, search, query, and reorganize the vault with the `obsidian` command rather than raw file tools whenever Obsidian itself knows something the files don't: base results, backlinks, resolved wikilinks, properties. The vault's own skill at `.agents/obsidian-cli/SKILL.md` is the full reference, and [[obsidian sync skips dot folders except .obsidian]], so copy it to each agent's computer.

## shape
- `obsidian vault={vault-name} <command> ...`, with `vault=` first
- `file=` resolves a name the way a wikilink does, and `path=` is an exact path like `pkm/potluck.md`
- Quote values with spaces, like `path="pkm/how we use this vault.md"`

## the ones agents use most
- `read`, `search query="..."`, `search:context`, `backlinks`, `links`, `orphans`
- `base:query path="pkm/potluck.base" view="conventions changed lately" format=paths`. Formats are json (the default), csv, tsv, md, and paths
- `property:read`, `property:set`, `property:remove`
- `rename` and `move` (with `to=`) instead of `mv`. They may not update links everywhere, so `search` for the old title before renaming and fix any leftovers by hand, since `backlinks` on the new name comes back empty
- `daily:path` and `daily:append` for the day's [[about daily|daily note]]

## where it runs
- The CLI talks to a running Obsidian app, so it only works where the app is open
- On an agent's computer that syncs with `ob`, run the app with its own Sync turned off, because [[headless sync keeps agent computers in the vault]] and `ob` should be the only syncer there
- On {owner}'s computers it's the app they already have open
- Plain file reads and edits still work everywhere, so an agent without the app isn't blocked

## Status
- 2026-10-21 (grokbot/chief): ported from botbrain
