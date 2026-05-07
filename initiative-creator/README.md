# Initiative Creator

A conversational PM coach that helps you write expertly-articulated initiatives — with the insight, the build, hierarchical KPIs, the dashboard, the epics, and the pithy story — in one sitting.

The output is a single markdown file you can paste into Notion, Linear, or Jira. The plugin doesn't try to be your PM tool; it just produces the artifact your PM tool needs.

## How it works

You run `/initiative` in any working directory. The plugin walks you through five steps:

1. **Insight** — what did you observe that led you here? Coached until specific and grounded.
2. **Initiative** — what are you building, and what 3-5 things must be true to call it done?
3. **KPIs (hierarchical)** — top-line, sub-KPIs, retention check, revenue-vs-margin call, dashboard mockup.
4. **Epics** — you list, the coach weighs in, then suggests 1-3 you might be missing.
5. **Pitch** — the "we saw X, so we're building Y, measured by Z" one-paragraph version. Lives at the top of the file.

Your initiative document is written incrementally as you go. If you're interrupted, `/initiative:resume <file>` picks up at the next unfinished step.

## Install

1. Install via the spruce22-plugins marketplace:

   ```
   /plugin marketplace add Army0fBobs/spruce22-plugins
   /plugin install initiative-creator@spruce22-plugins
   ```

   (For local development, you can clone and add by path instead — see the [parent README](../README.md#install-alternative--local-clone-for-development).)

2. Bootstrap your PM profile:

   ```
   /initiative:init
   ```

   Creates `~/.initiative-creator/profile.md`. Edit it with your reporting stack, default KPIs, retention definition, etc. The plugin reads this on every run so you don't re-answer the same questions.

3. Run it from wherever you want the output file to land:

   ```
   cd ~/wherever-makes-sense
   /initiative "tighten checkout abandonment"
   ```

   The output lands in your CWD as `initiative-tighten-checkout-abandonment.md`.

## Privacy

- **Public scaffolding** = this folder. Templates have no real product info.
- **Your PM profile** = `~/.initiative-creator/profile.md`. Outside any repo by default.
- **Your initiative documents** = your CWD when you run `/initiative`. You choose where (your product repo, your scratch dir, etc.). Never written into the plugin folder.

Defense in depth: `.gitignore` at the plugin root blocks `profile.md` and `initiative-*.md` so even an accidental copy won't get staged.

## Commands

| Command | What it does |
|---|---|
| `/initiative [title]` | Start a new initiative. Walks the 5-step flow. |
| `/initiative:init` | Bootstrap `~/.initiative-creator/profile.md`. |
| `/initiative:resume <file>` | Pick up an in-progress initiative at the next unfinished step. |
| `/initiative:update` | Pull plugin scaffolding updates. Never touches your data. |
| `/improve [summary]` | File a GitHub issue against this plugin's repo (bug, feature, improvement, question). Shows a preview before submitting. |

## Coaching style

The plugin pushes back. If your insight is "users want better search," it'll ask what specifically you saw. If your KPIs are MAU and signups, it'll ask whether retention belongs in there. If your top-line is "revenue," it'll ask whether margin is the truer call for this initiative. The point is to produce something that holds up in a strategy review — not to validate a wishlist.
