# spruce22-plugins

A collection of Claude Code plugins from Spruce22.

## Plugins

### [FunnyPenny](funnypenny/)

A witty, high-integrity personal AI assistant. Markdown-only — no app, no server.

Helps with to-do management, recipe voting, grocery lists organized by store section, and remembers what you tell it across sessions. Personal data lives at `~/.funnypenny/` and never enters this repo.

```
/plugin add /path/to/spruce22-plugins/funnypenny
/funnypenny:init
```

See [funnypenny/README.md](funnypenny/README.md) for full setup and usage.

### [Initiative Creator](initiative-creator/)

A conversational PM coach that walks you through creating an expertly-articulated product initiative — Insight → Initiative → KPIs (hierarchical, with retention and revenue-vs-margin) → Epics → Pitch.

Output is a single markdown file you can paste into Notion, Linear, or Jira. Your PM profile (reporting stack, default KPIs, etc.) lives at `~/.initiative-creator/` and never enters this repo. Initiative documents are written to whatever working directory you run it from.

```
/plugin add /path/to/spruce22-plugins/initiative-creator
/initiative:init
cd ~/wherever-makes-sense
/initiative "your initiative title"
```

See [initiative-creator/README.md](initiative-creator/README.md) for full setup and usage.

---

More plugins coming.
