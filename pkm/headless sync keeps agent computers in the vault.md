---
type: note
area: pkm
---
How an Obsidian vault stays synced on an agent's computer without the Obsidian app, and what any agent bringing its own computer needs to know to join. It works for any kind of agent or model, as long as the agent can run shell commands.

## how it works

- **obsidian-headless** (the `ob` command, an npm package) is Obsidian's official command-line sync client. It keeps a local folder in sync with an Obsidian Sync remote vault, end-to-end encrypted, with no desktop app needed
- It needs **Node 22 or newer**. Node 20 fails because it has no built-in WebSocket. The `better-sqlite3` dependency may need build tools (`build-essential` on Debian or Ubuntu)
- `ob sync --continuous` keeps running and syncs changes both ways. Wrap it in something that restarts it, like a systemd user service, a launchd agent, or a shell loop started at login, and log its output somewhere you can check
- Agents work with the vault as plain markdown files. Nothing needs to talk to Obsidian itself

## recommended settings

Check and change these with `ob sync-status` and `ob sync-config`:

- mode `bidirectional` (use `pull-only` for an agent that should only read)
- conflict strategy `merge`
- attachments: image, audio, pdf, video
- configs: **none**. With configs off, `.obsidian` settings, themes, and plugins don't sync, so an agent's computer can't overwrite the human's setup. It's also why an agent's copy won't show the human's theme
- device name: something that says who the agent is, like `<agent>-<computer>`, so version history shows who changed what

## why the app's own sync is off

- Obsidian supports only **one sync method per device**
- If the desktop app is also installed on an agent's computer (it's handy for viewing and for the `obsidian` CLI, which only works while the app runs), turn off the app's core **Sync** plugin: `"sync": false` in `.obsidian/core-plugins.json`

## joining from your own computer

1. Install Node 22+, then `npm install -g obsidian-headless`
2. `ob login` with the vault owner's Obsidian account. That's the human's step, since agents shouldn't hold their password
3. `ob sync-list-remote` should list the vault. Run `ob sync-setup` with your local path, and give it the vault's encryption password (the human provides it)
4. `ob sync-config --device-name <agent>-<computer>`, and leave configs off
5. Start `ob sync --continuous` under a restart wrapper, then check that `ob sync-status` and your log say "Fully synced"
6. Read [[how we use this vault]] before writing anything

## things to watch

- `.sync.lock` in `.obsidian/` means a sync is running. Don't delete it while `ob` is going
- Empty folders don't sync, so put a note in a new folder to keep it
- Simultaneous edits get merged, which can garble a note. Edit gently and re-read the result
- If sync stalls, check that the process is actually running before anything else, then check the log
- Never put the encryption password or account credentials in the vault

## optional example: Grok Bot agents

One agent type's real setup. Other agents don't need to copy it.

- Grok Bot agents share one Linux computer. A shared vault can live at a path like `/home/box/vaults/{vault-name}` there, so every Grok Bot agent reads and writes it directly with no sync of its own
- `ob` runs on Node 22 and is linked on `PATH`
- A shell loop like `~/.local/bin/{vault-name}-sync.sh` runs `ob sync --continuous`, restarting shortly after any exit, and logs somewhere checkable. There's often no service manager, so a login profile starts the script if it isn't already running
- The device name should identify the agent and computer, and the other settings match the recommendations above
- Obsidian desktop may be installed too, with its Sync plugin off, for queries like `obsidian base:query path="projects.base" view="active" format=md`

## Status
- YYYY-MM-DD (kind/agent name): documented the headless sync setup for the template
