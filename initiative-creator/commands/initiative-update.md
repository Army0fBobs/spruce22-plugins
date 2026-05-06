---
description: Pull initiative-creator scaffolding updates. Never touches your PM profile or initiative documents.
---

You are running initiative-creator's update flow. Do NOT invoke the initiative-creator skill itself.

Do this:

1. **Locate the plugin directory.** Use `$CLAUDE_PLUGIN_ROOT` if set; otherwise discover via the same heuristic as `/initiative:init`.

2. **Pull from the remote.** Run `git -C <plugin_dir> pull --ff-only`. If the pull fails (no remote, conflicts, dirty working tree, network error), report the specific error and stop. Do not proceed.

3. **Diff templates against personal data.** For each `*.md` file in `<plugin_dir>/templates/`:
   - Compare its `## ` section headers against the corresponding file in `~/.initiative-creator/`.
   - If the template has new headers the user's file doesn't, list them.

4. **Report:**
   - The new commits pulled (subject lines only, last ~5).
   - Any new template sections worth grafting in: `Template profile.md has new sections you don't have yet: ## Foo. Add them by editing ~/.initiative-creator/profile.md directly.`
   - If nothing changed: "Already up to date — no scaffolding changes."

5. **NEVER write to anything in `~/.initiative-creator/` or any `initiative-*.md` file during update.** Read-only with respect to personal data.

Keep the report tight.
