# spruce22-plugins

A collection of Claude Code plugins from Spruce22. This repo focuses on personal/family plugins. Product-management plugins now live in their own home: [Army0fBobs/product-management-suite](https://github.com/Army0fBobs/product-management-suite).

## Install (recommended — via marketplace)

```
/plugin marketplace add Army0fBobs/spruce22-plugins
/plugin install funnypenny@spruce22-plugins
```

That's it — Claude Code handles cloning, caching, and updates.

## Install (alternative — local clone, for development)

If you want to hack on the plugin yourself:

```bash
git clone https://github.com/Army0fBobs/spruce22-plugins.git ~/spruce22-plugins
/plugin add ~/spruce22-plugins/funnypenny
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

---

## Looking for the PM tools?

Initiative Creator and other product-management plugins moved to their own marketplace: **[Army0fBobs/product-management-suite](https://github.com/Army0fBobs/product-management-suite)**.

```
/plugin marketplace add Army0fBobs/product-management-suite
/plugin install initiative-creator@product-management-suite
```

Different audience, different velocity, different release cadence — splitting them keeps both repos focused.

---

## Feedback

FunnyPenny ships with an `/improve` slash command. Type `/improve` from inside Claude Code, answer two short questions, preview the issue, and it gets filed against this repo via your `gh` CLI (or a browser fallback if you don't have `gh`). Bob reviews and ships fixes from there. Issues land at [github.com/Army0fBobs/spruce22-plugins/issues](https://github.com/Army0fBobs/spruce22-plugins/issues).

---

More plugins coming.
