---
type: pkm
created: 2026-11-11
role: how this vault works
---
# [[each decision option gets its own checkbox]]

- When a note lists decisions for {owner}, **each option gets its own checkbox**, so they pick one by ticking it
- One checkbox for a whole decision leaves nowhere to mark which option was chosen
- Part of [[owner writing and note preferences]]
- Each decision is a question in [Tincan](https://github.com/tyler-dot-earth/obsidian-tincan) syntax, shaped like [[open questions get a spot for answers]]
- The question is the callout title: `> [!question|choice] Question text?` when they pick one, `> [!question|choices] Question text?` when they can pick several
- Its options go in the callout body after a blank `>` line, one per line as `> - [ ] option`, each a distinct one-line label in the Markdown source; the text can wrap on screen. One nested `[!note]` under an option is supported
- `🤖` at the start of an option's label marks the recommended one, like `> - [ ] 🤖 option`, at most one per decision
- No "something else" checkbox: Write another answer… opens the custom editor. Its saved `Other:` paragraph appears in an Other answer callout, with Edit and Clear actions
- Whoever acts on the decision reads the pick from the question's direct `- [x]` options or its `Other:` paragraph. Checkboxes inside notes are not picks
- Add a note can comment on an option without selecting it. The indented note stays with that option when picks change; a trailing direct nested note comments on the whole question. Neither counts as an answer
- For one pick, choosing an option replaces the previous pick or custom answer. Tincan asks before removing written custom text; multiple picks can accompany a custom answer
- Keep question titles unique in their note and option labels distinct. Preserve saved picks and notes when reshaping a question

```markdown
> [!question|choice] How should the app be installed?
>
> - [ ] 🤖 Flatpak
> - [ ] The distro package
>   > [!note]
>   > Check which version the package provides.
```

---

## Status

- YYYY-MM-DD (kind/agent name): ported the Tincan 0.4.0 option shape and adapted it for the template
