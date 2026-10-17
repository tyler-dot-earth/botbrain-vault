---
type: pkm
created: 2026-10-15
---
# botbrain-vault

A reusable Obsidian vault template for a human plus one or more agents working in the same notes. It ships folder layout, conventions, Bases indexes, and a ready `.obsidian` config (plugins, theme, snippets, Periodic Notes daily setup).

Copy this folder to start a new vault. Do not treat it as a live vault itself.

## Folder layout

| Path | Purpose |
| --- | --- |
| `home.md` | Front page (rename if you want a vault-specific title) |
| `pkm/index.base` | Folder / recently-changed / this-folder views |
| `pkm/projects.base` | Active and all-project views |
| `pkm/transcripts.base` | Saved coding-agent sessions, newest first and by project |
| `pkm/properties.md`, `pkm/properties.base` | What each frontmatter property means, plus by-type, agents, handoffs, transcripts, and missing-type views |
| `agents/` | One note per agent; `agents.md` hub + `example agent.md` template |
| `daily/` | Daily notes (`YYYY-MM-DD`), created by Periodic Notes |
| `to bots/` | Handoffs from human → agents |
| `to human/` | Handoffs from agents → human |
| `ideas/` | Loose early ideas |
| `files/` | Attachments |
| `pkm/` | Notes about how the vault works |
| `archive/` | Retired notes (ignored by search via `app.json`) |

Each content folder has an `about …` note so empty folders survive Obsidian Sync.

## Conventions (short)

- Folders stay **one level deep**; lowercase names
- Status lines look like `- YYYY-MM-DD (human): …` or `- YYYY-MM-DD (kind/agent name): …`
- Agents claim work in `to bots/` with `claimed_by` / `claimed`, then file the note elsewhere
- Agents leave results for the owner in `to human/`, or set `needs: human` elsewhere
- Secrets stay out of the vault
- Full detail: [[how we use this vault]] (open `pkm/how we use this vault.md`)

Placeholders to fill after copying:

- `{owner}` — the human who owns the vault
- `{kind}`, `{agent_id}` — on agent notes
- `{org}`, `{repo}`, `{vault-name}` — in optional examples

## Required / included plugins

Community plugins already listed in `.obsidian/community-plugins.json`:

- Periodic Notes (daily notes folder = `daily`; core Daily notes is off on purpose)
- Calendar, Calendar Bases, Natural Language Dates
- Templater
- Mermaid View, Diagram Popup (mermaid-popup)
- Iconize (obsidian-icon-folder)
- Style Settings
- Blockreffer, Lanes, [Tapedeck](https://community.obsidian.md/plugins/tapedeck) (optional but included)

Core: Bases on; Daily notes off; Sync left on for humans who use Obsidian Sync (agents using headless sync should turn Sync off on their device — see the headless sync note).

Theme: Baseline. Snippet: `font.css`. Fonts: Inter and Dank Mono, not bundled; see `.obsidian/fonts/FONTS.md`.

## Start a new vault from this template

1. Copy the whole folder somewhere new, e.g. `cp -a ~/templates/botbrain-vault ~/documents/jobs/my-vault`
2. Open that folder as an Obsidian vault
3. Optionally rename `home.md` to your vault title and update wikilinks that point at `[[home]]`
4. Fill `{owner}` (and other placeholders) in `pkm/` and `agents/`
5. Delete or rewrite `agents/example agent.md` into your first real agent note; keep `agents.md` as the hub
6. Point Obsidian Sync (or headless `ob`) at the new folder; do not reuse another vault's encryption password casually — set up Sync for this vault
7. Create today's daily note via Periodic Notes and start logging

## What this template deliberately omits

- No dated `daily/` notes
- No real agent configs beyond the example template
- No `archive/` content beyond the about note
- No `workspace.json` or other per-device Obsidian state
- No personal paths or tokens in plugin `data.json` files

## License / origin

Structure and conventions are meant to be forked freely for any human+agent vault.
