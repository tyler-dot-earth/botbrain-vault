---
type: pkm
created: 2026-11-11
role: how this vault works
---
# [[open questions get a spot for answers]]

- Any question for {owner} in a note gets a 🤖 recommendation they can easily pick and a place right under it to write an answer
- Questions are written in [Tincan](https://github.com/tyler-dot-earth/obsidian-tincan) syntax, so they can be answered in reading view
- Part of [[owner writing and note preferences]]

## the shape

- Each question is its own top-level `[!question]` callout, with the question as the title and text that's unique in the note
- A question left as a bullet or paragraph has nowhere to be answered, so it counts as a miss, even in a rough note
- **Make each question answerable on its own:** say what each option is in a few plain words, and link the heading with the details (`[[#heading|details]]`), so {owner} shouldn't have to read the whole note to answer
- Context goes in the question title or on a line just above the callout, since the callout body is where the answer goes
- **With a 🤖 recommendation:** `> [!question|choice] Question text?` with the rec as a `> - [ ] 🤖 ...` option, so {owner} can pick it with one tick. Tincan offers Write another answer… for a custom answer, saved as an `Other:` paragraph without another checkbox
- **With no recommendation:** a plain `> [!question] Question text?`, which offers Answer… and saves the text in the callout body on Done
- A checked option, saved custom answer, or nonblank text answer counts as answered; the callout uses the theme's success color and a check icon, with no separate completion checkbox
- Separate callouts with a blank line, keep them out of lists, and put an explicit `>` on every body line, including blank lines
- Keep explanations above the callout or in a nested `[!note]`; a pick body holds options, an optional `Other:` paragraph, and notes, not a free-standing context paragraph
- Add a note can annotate the whole question or an individual option, even one not selected. Notes are comments, not answers or selections
- Tincan's controls work in reading view; rendered callouts in Live Preview share the styling. All open copies of the note must be in reading view for Tincan to save
- [[every question carries its own context]] also applies here

```markdown
> [!question] What should the hooks send?

> [!question|choice] Who listens to the hooks?
>
> - [ ] 🤖 one generic webhook, with one bot as the first listener
```

- For questions with several options, see [[each decision option gets its own checkbox]]

---

## Status

- YYYY-MM-DD (kind/agent name): ported the Tincan 0.4.0 authoring shape and adapted it for the template
