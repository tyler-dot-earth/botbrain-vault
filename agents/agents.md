---
type: hub
created: 2026-10-15
updated: 2026-11-11
---
# [[agents]]

- One note per agent that works in this vault, covering its purpose, instructions, and routines
- See [[example agent]] for a template you can copy
- When an agent's real config changes, that agent (or whoever set it up) updates its note, since each note is a snapshot
- A new agent note gets `type: agent`, `kind` (like `{kind}`), and `status` (`active` or `paused`), plus sections for its purpose, `## Instructions`, `## Routines`, `## Works with`, and `## Status`
- A single-app agent can keep `agent_id` on the note; an identity that works through several apps records each app's id in its own section, as [[one agent can work through several apps]] and [[properties]] describe

## every agent reads this

- Shared ground for every bot, whatever app or harness runs it
- Each agent note embeds this section, so it's written once
- Read before working:
  - [[how we use this vault]]
    - [[how we use this vault#say who changed what|say who changed what]] and [[how we use this vault#handoffs|handoffs]]
  - [[owner collaboration preferences]]
  - [[owner writing and note preferences]]
    - [[owner writing and note preferences#shape notes|shape notes]] and [[owner writing and note preferences#small style rules|small style rules]]
- Before a vault task, check [[vault skills live in the skills folder]] for a skill that fits
- Keep secrets, passwords, and credentials out of the vault
- Don't send messages, post, submit forms, spend, or ship on {owner}'s behalf unless they explicitly asked for that action

### app-independent identities

- Every multi-app agent is one identity across its apps, following [[one agent can work through several apps]]
- The agent owns follow-through across apps until its assigned outcome is verified or a concrete blocker is reported, as [[agents own follow-through until the result is verified]] says
- Queuing work in another app is an intermediate step, not completion or a transfer of responsibility away from that identity

### before responding in chat

- Check the actual draft against these conventions and fix mismatches before sending, following the linked note for details
- Do this silently for each chat message
- Before ending a turn, also check the work itself using [[agents own follow-through until the result is verified|own follow-through]]
- [[chat links to notes use obsidian uris|Link vault notes with Obsidian URIs]]
- [[how we use this vault#pointing to notes from outside the vault|Include plain-path fallbacks and put detailed findings in linked vault notes]]
- [[chat follows the same shape as notes|Write chat like a note: short bullets, one sentence each, no paragraphs]]

![[index.base#this folder]]

## Status
- YYYY-MM-DD (kind/agent name): stubbed out for the template
- YYYY-MM-DD (kind/agent name): agent status values are `active` or `paused`
- YYYY-MM-DD (kind/agent name): added a shared section for follow-through and multi-app identity, without botbrain-specific routing
