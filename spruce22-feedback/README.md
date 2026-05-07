# spruce22-feedback

A single-purpose plugin for the [spruce22-plugins](../) marketplace. Adds an `/improve` slash command that lets you file a GitHub issue against the marketplace repo without leaving Claude Code.

## What it does

Type `/improve` (with or without a one-liner). The plugin walks you through three short questions (which plugin, issue type, anything else worth including), shows you a preview of the issue, and only submits after you confirm.

Submission tries `gh issue create` first (uses your existing GitHub CLI auth, files under your identity). If `gh` isn't installed or authenticated, it falls back to opening a prefilled GitHub issue URL in your browser — you click submit.

No surprise issues. No telemetry. No auto-included session data.

## Install

```
/plugin marketplace add Army0fBobs/spruce22-plugins
/plugin install spruce22-feedback@spruce22-plugins
```

That's it. `/improve` is now available.

## Usage

```
/improve
```

or with a starter summary:

```
/improve grocery list bundling skips items when I have 3 dogs
```

The plugin handles the rest.

## What you're filing

All issues land in [Army0fBobs/spruce22-plugins](https://github.com/Army0fBobs/spruce22-plugins/issues), tagged with the plugin name in the title (e.g., `[funnypenny] bug: ...`). Bob reviews, accepts or declines, and ships fixes from there.
