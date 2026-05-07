# spruce22-plugins

A collection of Claude Code plugins from Spruce22.

## Install (recommended — via marketplace)

```
/plugin marketplace add Army0fBobs/spruce22-plugins
/plugin install funnypenny@spruce22-plugins
/plugin install initiative-creator@spruce22-plugins
```

That's it — Claude Code handles cloning, caching, and updates.

## Install (alternative — local clone, for development)

If you want to hack on the plugins yourself:

```bash
git clone https://github.com/Army0fBobs/spruce22-plugins.git ~/spruce22-plugins
/plugin add ~/spruce22-plugins/funnypenny
/plugin add ~/spruce22-plugins/initiative-creator
```

## Plugins

### [FunnyPenny](funnypenny/)

A witty, high-integrity personal AI assistant. Markdown-only — no app, no server.

Helps with to-do management, recipe voting, grocery lists organized by store section, and remembers what you tell it across sessions. Personal data lives at `~/.funnypenny/` and never enters this repo.

```
/plugin install funnypenny@spruce22-plugins
/funnypenny:init
```

See [funnypenny/README.md](funnypenny/README.md) for full setup and usage.

### [Initiative Creator](initiative-creator/)

A conversational PM coach that walks you through creating an expertly-articulated product initiative — Insight → Initiative → KPIs (hierarchical, with retention and revenue-vs-margin) → Epics → Pitch.

Output is a single markdown file you can paste into Notion, Linear, or Jira. Your PM profile (reporting stack, default KPIs, etc.) lives at `~/.initiative-creator/` and never enters this repo. Initiative documents are written to whatever working directory you run it from.

```
/plugin install initiative-creator@spruce22-plugins
/initiative:init
cd ~/wherever-makes-sense
/initiative "your initiative title"
```

See [initiative-creator/README.md](initiative-creator/README.md) for full setup and usage.

---

## Feedback

Both plugins ship with an `/improve` slash command. Type `/improve` from inside Claude Code, answer two short questions, preview the issue, and it gets filed against this repo via your `gh` CLI (or a browser fallback if you don't have `gh`). Bob reviews and ships fixes from there. Issues land at [github.com/Army0fBobs/spruce22-plugins/issues](https://github.com/Army0fBobs/spruce22-plugins/issues).

---

More plugins coming.
