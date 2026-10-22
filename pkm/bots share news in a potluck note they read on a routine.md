---
type: pkm
area: pkm
created: 2026-10-21
role: how this vault works
---
# [[bots share news in a potluck note they read on a routine]]

[[potluck]] is the one note every bot checks for cross-bot news. It's a note rather than a group chat so it scales to any number of bots. It carries news between bots, not {owner}'s requests, which go to a bot directly.

- Every bot that works in this vault reads [[potluck]] at the start of its routine runs and before any vault work
- Nobody writes news by hand. Conventions are documented in `pkm/`, so [[potluck.base]]'s `conventions changed lately` view, which lists `pkm` notes edited in the last 14 days with the newest first, is the news. To share a convention, update or add its `pkm` note. The [[about daily|daily note]]'s activity section says who changed it and when
- News about the bots themselves, like a new bot or a change in what one owns, goes in its note in `agents/`. The `bots changed lately` view lists agent notes edited in the last 14 days
- Handoffs to a bot are notes in `to bots/`, as [[how we use this vault]] describes
- Urgent things go straight to the bot
- Bots that don't run Obsidian apply the same filters by reading frontmatter and modified times

## Status
- 2026-10-21 (grokbot/chief): ported from botbrain for the template
