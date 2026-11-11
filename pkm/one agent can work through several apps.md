---
type: pkm
created: 2026-11-11
related:
  - "[[agents]]"
  - "[[how we use this vault]]"
---
# [[one agent can work through several apps]]

- One identity can work through several apps, with a shared purpose and a section for each app
- The identity stays the same when the app or model changes
- Part of how [[agents]] are organized

## the shape

- Keep one identity note per agent, with shared purpose and working agreements first, then a section for each app
- The shared note describes the intended role; each app's live settings determine what actually runs there
- Snapshots of app settings need their source and date
- Single-app agents can keep a `kind` and `agent_id` on the note
- A multi-app identity leaves those off shared frontmatter and records each app's id in its own section, as [[properties]] describes

## claims and provenance

- Sign meaningful changes as `kind/name`, with the `kind` naming the app that did the work, like `kind/[[example agent]]`
- Claim a handoff with app and identity, such as `kind/[[example agent]]`; other execution contexts respect that active claim until it is explicitly transferred, including when they run the same identity
- Include a thread or session reference in the handoff when concurrent conversations in the same app could otherwise mistake the claim
- Keep the same handoff note through an execution transfer and record what is done, what remains, and the context handling the next step; moving execution does not discharge the agent's responsibility
- Re-read after claiming; a synced Markdown claim is a courtesy, not an atomic lock

## continuity comes from the vault

- Share decisions, useful findings, and next steps through the existing notes and handoff folders
- Each version reads those notes when taking work up; a saved note does not notify or wake another app
- Private chat history and app memory remain local unless deliberately shared
- Credentials stay scoped to the account, task, and app where they were granted
- Each routine needs an explicit app that runs it, alongside its owner identity, so a second app does not start a duplicate

## Status

- YYYY-MM-DD (kind/agent name): ported the multi-app identity convention and adapted it for the template
