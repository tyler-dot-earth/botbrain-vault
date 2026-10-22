---
type: pkm
area: pkm
created: 2026-10-16
updated: 2026-10-21
role: how this vault works
---
# [[properties]]

What each frontmatter property in {vault-name} means, what its value looks like, which note types use it, and who sets it. Conventions for using them live in [[how we use this vault]]; `index.base` and `projects.base` depend on the ones marked below.

![[properties.base#by type]]

## core

- **type** — what kind of note this is. Plain lowercase word, set by whoever creates the note. Every non-archive note has one (attachments in `files/` don't). `projects.base` filters on `type == "project"`, and `properties.base` groups on it. Values:

| type | means | where |
| --- | --- | --- |
| `project` | a project hub, with `area`, `status`, `started`. Only hubs, never notes inside a project | a project's folder, or the top level |
| `note` | a general working note; links to its hub with `project` when it belongs to one | anywhere |
| `idea` | an early idea or something to explore later | `ideas/` |
| `agent` | one agent's purpose, instructions, routines | `agents/`, like [[example agent]] |
| `transcript` | a saved coding-agent session | `transcripts/` |
| `handoff` | a note waiting on a bot or on {owner}; keeps `claimed_by`/`claimed`. Retype when it's moved out | `to bots/`, `to human/` |
| `hub` | a front page or index note for a person or area | [[home]], [[human]], [[agents]] |
| `pkm` | how the vault and our note-taking work, including each folder's `about` note | `pkm/`, `about` notes |

- **area** — the broader area a note belongs to, usually matching a folder or product. Plain lowercase slug like `pkm` or `personal`. Optional; general-purpose agents leave it off. Set by the note's creator. `projects.base` groups active projects by it
- **project** — the project hub this note belongs to. A quoted wikilink, `"[[hub note name]]"`. Set by whoever files the note. `projects.base#this project` depends on it
- **related** — other notes this one is about. A list of wikilinks
- **created** — the day the note was started. `YYYY-MM-DD`
- **updated** — the day of the last meaningful edit. `YYYY-MM-DD`. Bumped by whoever makes the edit
- **status** — lifecycle state. For projects: `active`, `paused`, or `done`. For agents: `active` or `paused`. Set by {owner} or the note's owner agent. `projects.base` filters and groups on it
- **role** — what job a note does beyond its type. So far one value, `how this vault works`, on the notes that explain how part of the vault works. Set by whoever writes or adopts such a note. `index.base#how this vault works` lists them, and [[home]] embeds that view

## projects

- **started** — when a project began. `YYYY-MM-DD`. Only on project hubs. Set when the hub is created; shown in `projects.base`

## agents

Used only on `type: agent` notes in `agents/`, set by the chief-of-staff agent or the agent itself.

- **kind** — what sort of agent it is, like `grokbot`. Matches the `kind` half of the `kind/name` author convention
- **agent_id** — the agent's id in its platform. Lets anyone find the exact agent behind a note

## handoff

Used on notes in `to bots/` and `to human/`, or anywhere that needs {owner}. They use `type: handoff`.

- **claimed_by** — which agent picked up a `to bots/` note. `kind/name`, like `grokbot/chief of staff`. Set by the claiming agent
- **claimed** — when it was claimed. Local date and time, `YYYY-MM-DDTHH:MM`. Set alongside `claimed_by`
- **needs** — who has to act, like `human`. Added by an agent, removed once handled

## transcript

Used on `type: transcript` notes, in `transcripts/` where Tapedeck imports them, set by the agent that saves the transcript. `transcripts.base` lists them all (views **all**, newest first, and **by project**): ![[transcripts.base#all]]

- **harness** — the coding tool the session ran in, like `claude code`
- **model** — the model used
- **session_id** — the harness's session id, usually a UUID
- **machine** — the computer's hostname
- **cwd** — the working directory, as a path with `~`
- **resume** — the shell command that reopens the session, like `claude --resume <session_id>`
- **date** — the day the session happened. `YYYY-MM-DD`. Different from `created` (when the note was made), e.g. for an old session imported later
- also **project** and **related**, from core

## automating created and updated
For notes the human makes in Obsidian:
- **created**: a Templater folder template (Settings, Templater, folder templates, `/`) containing:

```
---
created: <% tp.file.creation_date("YYYY-MM-DD") %>
---
```

- **updated**: Templater only runs on creation, so use Linter's YAML timestamp rule or the Update time on edit plugin to bump `updated` on save
- Agents write files directly, so none of this runs for them. Agents set `created` by hand on new notes and bump `updated` when they make a meaningful edit

## Status

- YYYY-MM-DD (kind/agent name): created as the property reference, with `properties.base` and `transcripts.base`
- 2026-10-21 (grokbot/chief): added `role`
