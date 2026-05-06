---
description: Resume an in-progress initiative draft. Picks up at the first unfinished step.
argument-hint: [path to draft, default: first initiative-*.md in CWD]
---

Invoke the `initiative-creator` skill in resume mode.

Locate the draft:
- If $ARGUMENTS is provided, treat it as the file path.
- Otherwise look for `initiative-*.md` files in the current working directory.
  - If exactly one exists, use it.
  - If multiple, ask which one.
  - If none, tell the PM there's nothing to resume and suggest `/initiative` to start fresh.

Read the file's status markers (the `<!-- step-N: draft|confirmed -->` lines at the top). Find the first step with `draft` status. Begin coaching at that step. Don't re-do already-confirmed steps unless the PM explicitly asks.
