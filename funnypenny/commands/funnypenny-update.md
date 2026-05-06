---
description: Pull FunnyPenny scaffolding updates from the public repo. Never touches ~/.funnypenny/ personal data.
---

You are running FunnyPenny's update flow. Do NOT invoke the funnypenny skill itself.

Do this:

1. **Locate the plugin directory.** Use `$CLAUDE_PLUGIN_ROOT` if set; otherwise discover via the same heuristic as `/funnypenny:init`.

2. **Pull from the remote.** Run `git -C <plugin_dir> pull --ff-only`. If the pull fails (no remote, conflicts, dirty working tree, network error), report the specific error and stop. Do not proceed to the diff step.

3. **Diff templates against personal data.** For each `*.md` file in `<plugin_dir>/templates/`:
   - Extract its `## ` section headers (lines starting with "## ").
   - Compare against the headers in the corresponding file at `~/.funnypenny/<filename>`.
   - If the template has new headers the user's file doesn't, list them.

4. **Report:**
   - The new commits pulled (subject lines only, last ~5).
   - Any new template sections worth grafting in: `Template foo.md has new sections you don't have yet: ## Bar, ## Baz. Add them by editing ~/.funnypenny/foo.md directly.`
   - If nothing changed, just say "Already up to date — no scaffolding changes."

5. **NEVER write to anything in `~/.funnypenny/` during update.** This command is read-only with respect to personal data.

Keep the report tight. The human is checking in, not reading release notes.
