---
description: First-time setup — bootstrap ~/.initiative-creator/ from this plugin's templates.
---

You are running initiative-creator's initial setup. This is a one-shot setup task — do NOT invoke the initiative-creator skill itself.

Do this:

1. **Locate the templates directory.** It's at `$CLAUDE_PLUGIN_ROOT/templates/` if that env var is set. Otherwise, search likely plugin install locations (`~/.claude/plugins/`, `~/.claude/data/plugins/`, `/Users/bobbennett/spruce22-plugins/initiative-creator/`) for an `initiative-creator` directory and use its `templates/` subfolder.

2. **Ensure `~/.initiative-creator/` exists.** Create it if missing.

3. **Copy `profile.md`** from the templates directory to `~/.initiative-creator/profile.md`, ONLY if the destination does not already exist. NEVER overwrite an existing profile.

   Note: do NOT copy `initiative.md` from templates — that's the per-initiative document template, used at runtime by the skill, not a profile file.

4. **Print a brief report:**
   - "Created: ~/.initiative-creator/profile.md" — or "Already existed (skipped)"

5. End with: "Now open `~/.initiative-creator/profile.md` and fill in your reporting stack, default KPIs, and retention definition. Then `cd` to wherever you want the output and run `/initiative` to start a new initiative."

Prefer a single bash invocation. Be quiet about implementation details — just report the result.
