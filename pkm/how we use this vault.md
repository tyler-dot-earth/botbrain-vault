---
type: pkm
created: 2026-10-15
---
How notes are organized in this vault. Note shape follows [[owner writing and note preferences]] and [[write notes around one useful idea]].

## folders
- Keep folders **one level deep**, with no subfolders
- Use lowercase file and folder names
- `agents/` holds one note per agent, with its purpose, instructions, and routines; [[agents]] is the hub
- `to bots/` and `to human/` are handoff folders, covered below
- `daily/` holds daily notes, one per day named `YYYY-MM-DD`, created by the Periodic Notes community plugin (by Liam Cain), set up for daily notes only with `daily` as its folder. Each note is that day's running activity log. The morning brief seeds it, and anything done that day that wasn't in the brief gets logged too. Check items off in place and never move them between sections
- The chief-of-staff agent helps keep up the whole vault, including docs, folders, and conventions as they change. See [[example agent]]
- `ideas/` holds early ideas, `pkm/` holds notes about the vault, `files/` holds attachments, and `archive/` holds retired notes
- Only [[home]] lives at the top level; all `.base` indexes live in `pkm/`
- Give a topic or project its own folder once it has a handful of notes. Until then, leave notes at the top level, since links do most of the organizing

## projects
- A project is a hub note with `type: project`, an `area`, a `status` of `active`, `paused`, or `done`, and a `started` date
- Notes that belong to a project get `project: "[[hub note name]]"` in their properties
- `projects.base` lists every project, and its **active** view is on the front page
- Embed `![[projects.base#this project]]` in a hub note to list its notes automatically

## say who changed what
- Add a dated line to a note's `## Status` section after a meaningful change, like `- YYYY-MM-DD (human): added pricing source`
- Name the author as `kind/name`, like `grokbot/chief of staff` or `human`

## edit gently
- Agents only fill blanks {owner} leaves, like `{TBA HERE}`, in notes they're actively writing
- Move stale notes to `archive/` instead of deleting them

## files
- Link PRs with your preferred review tool (for example Graphite: `https://app.graphite.com/github/pr/{org}/{repo}/12345?mode=overview`), not raw GitHub, when that tool is the team's front door. Keep GitHub links only for things the review tool can't show, like a specific review anchor
- Put attachments in `files/` and link each one from the note that uses it
- Keep **secrets out**

## handoffs
- Drop a note in `to bots/` when you want an agent to look into it, with no tagging needed
- An agent claims it by adding `claimed_by: kind/name` and `claimed: <date and time>` to its properties, so others leave it alone
- The agent does the work in the note, adds a Status line, and moves it where it belongs, removing the claim
- Agents put things for {owner} in `to human/`, like finished research, questions, or decisions, and {owner} moves or deletes them once seen
- When something outside `to human/` needs {owner}, an agent adds `needs: human` to its properties and removes it once handled
- Agents aren't notified of vault changes, so a note in `to bots/` waits until an agent checks. For anything urgent, message the agent directly
- Each folder holds a short `about` note so the folder survives sync even when empty

## entry points
- [[home]] is the front page
- `index.base` has views for **by folder**, **recently changed**, and **this folder**

## pointing to notes from outside the vault
- When telling the human about a note in chat, email, or anywhere outside Obsidian, prefer an Obsidian deep link that opens it locally, like [home](obsidian://open?vault={vault-name}&file=home)
- Format: `obsidian://open?vault={vault-name}&file=<path without .md>`, URL-encoded (`/` is `%2F`, spaces are `%20`)
- Also give the plain path in a code span as a fallback, in case the link isn't clickable there

- Transcript notes use `type: transcript`, `harness`, `model`, `session_id`, `machine`, `cwd`, `resume`, `date` (when the session happened), `created` (when the note was made), `project`, and `related`

## type on notes
- Every new note gets a `type`: `project` (hubs only), `note`, `idea`, `agent`, `transcript`, `handoff`, `hub`, or `pkm`. See [[properties]] for what each means
- When a handoff moves out of `to bots/` or `to human/`, change its type to fit where it lands

## dates on notes
- Agents set `created: YYYY-MM-DD` on every new note and bump `updated: YYYY-MM-DD` on meaningful edits, since Obsidian templates and plugins never run for files agents write. See [[properties]]

## Status
- YYYY-MM-DD (kind/agent name): adapted for the botbrain-vault template
- YYYY-MM-DD (kind/agent name): added the deep link preference
- YYYY-MM-DD (kind/agent name): added the transcript properties convention
- YYYY-MM-DD (kind/agent name): added [[properties]] as the property reference
- YYYY-MM-DD (kind/agent name): agents set created and updated by hand
- YYYY-MM-DD (kind/agent name): every new note gets a type
- YYYY-MM-DD (kind/agent name): moved the root bases into pkm/
