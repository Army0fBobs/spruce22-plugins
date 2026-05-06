---
description: Force-save a fact to the right ~/.funnypenny/ file.
argument-hint: <fact to remember>
---

The human wants to explicitly save a fact: **$ARGUMENTS**

If $ARGUMENTS is empty, ask: "What should I remember?" and stop.

Otherwise:

1. Decide which file the fact belongs in, using FunnyPenny's Active Learning routing table:
   - Life experience / background → `~/.funnypenny/user.md` → `## Background`
   - Preference → `~/.funnypenny/preferences.md` → relevant section
   - Opinion / worldview → `~/.funnypenny/user.md` → `## Opinions`
   - Skill or past role → `~/.funnypenny/user.md` → `## Skills`
   - Relationship → `~/.funnypenny/contacts.md` → relevant section
   - Habit or rhythm → `~/.funnypenny/routines.md` → relevant section
   - Major life change / new goal → `~/.funnypenny/memory.md` → `## Core Facts`
   - Follow-up reminder → `~/.funnypenny/memory.md` → `## Open Loops` (prefix with today's date)
   - To-do → `~/.funnypenny/tasks.md` → `## Now` or `## Soon`
   - Recipe / food tradition → `~/.funnypenny/our_recipes.md` → relevant section
   - Voice / writing-style note → `~/.funnypenny/my_voice.md` → relevant section

2. Read the target section first. If a near-duplicate already exists, don't append — say "Already saved" and stop.

3. Otherwise append the fact as one line to the right section.

4. Confirm in one short line: `Saved to <file> → <section>.` Nothing else.
