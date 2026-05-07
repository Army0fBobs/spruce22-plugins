---
description: First-time setup — bootstrap ~/.funnypenny/ from this plugin's templates.
---

You are running FunnyPenny's initial setup. This is a one-shot setup task — do NOT invoke the funnypenny skill itself.

Do this:

1. **Locate the templates directory.** It's at `$CLAUDE_PLUGIN_ROOT/templates/` if that env var is set. Otherwise, search likely plugin install locations (`~/.claude/plugins/`, `~/.claude/data/plugins/`, `/Users/bobbennett/spruce22-plugins/funnypenny/`) for a `funnypenny` directory and use its `templates/` subfolder.

2. **Ensure `~/.funnypenny/` exists.** Create it if missing.

3. **For each `*.md` file in the templates directory**, copy it to `~/.funnypenny/` ONLY if the destination file does not already exist. NEVER overwrite an existing file.

4. **Print a brief report:**
   - "Created: <list of new files>"
   - "Already existed (skipped): <list of files left untouched>"

5. End with: "FunnyPenny is funny, witty, clean, and high-integrity by default — no setup required. Run `/funnypenny` whenever you want her. Optionally edit `~/.funnypenny/soul.md` to refine her voice for your taste over time, but don't feel obligated; defaults work."

Prefer a single bash invocation that handles everything (find + cp -n or equivalent). Be quiet about implementation details — just report the result.
