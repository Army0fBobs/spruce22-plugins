# FunnyPenny

I wanted a witty, useful personal assistant that knew me, could help me with my day to day — including to-do management, recipe voting, and grocery lists sorted by area of the grocery store.

Then I wanted to share it with others so they could use the personal assistant and its skills, but keep everything about me private. And not have to spin up databases, or anything — everything just stored in text `.md` files.

**How it works:** you open the plugin in Claude, it automatically gathers context from your `.md` files, and then it's there for whatever you need.

---

## Use case: the friend who actually remembers

FunnyPenny works as the friend who's good with computers and actually gets stuff done. She's funny by default — TARS-from-Interstellar style, dry, witty, never off-color. And she remembers what you tell her between sessions, because she writes it down to a folder on your machine that you control.

She's great for the parts of life that aren't work — household logistics, family memory, your own to-do list, drafts in your voice.

**For example:** Sunday night, you say *"what should I cook this week and what do I need to pick up at the store."* FunnyPenny will:

- Pull from `our_recipes.md` (the family canon you've been adding to over weeks). Skip anything you cooked in the last 14 days. Mix in one wildcard.
- **Vote with you on the meals** — present 5-7 options with who-loves-it and time-to-table, take your "yes / no / swap 6 for something faster" votes, lock the menu for the week.
- **Build the grocery list** — aggregate the ingredients across the locked meals, drop anything in your pantry staples, and sort the list by the section order of *your* grocery store (`grocery_layout.md`). Output is copy-pasteable.

That's three markdown files (`our_recipes.md`, `grocery_layout.md`, plus the `tasks.md` she nudges you on) acting in concert. No app, no server, no signup, no telemetry — and the next time you talk to her, she remembers what you cooked.

**Other things she handles well:** drafting an email in your voice (she reads `my_voice.md`), nagging you about open loops you said you'd follow up on, capturing facts about family/work/preferences silently as you mention them.

**Where this fits in your life:** FunnyPenny isn't competing with Apple Notes, Google Keep, your calendar, or the 14 to-do apps you've tried and abandoned. She's the *interface* on top — the conversational layer that knows what you've told her and acts on it. The data is plain markdown you can edit in any text editor. If you ever want to leave, you take the folder.

---

## Install

1. Install via the spruce22-plugins marketplace:

   ```
   /plugin marketplace add Army0fBobs/spruce22-plugins
   /plugin install funnypenny@spruce22-plugins
   ```

   (For local development, you can clone and add by path instead — see the [parent README](../README.md#install-alternative--local-clone-for-development).)

2. Bootstrap your personal data folder:

   ```
   /funnypenny:init
   ```

   This copies the templates from this repo into `~/.funnypenny/`. Idempotent — re-running won't overwrite anything you've edited.

3. Open `~/.funnypenny/user.md` and put a few lines about who *you* are.
4. Talk to her: `/funnypenny` or just say "hey FunnyPenny, what's on my list?"

Optional, anytime: edit `~/.funnypenny/soul.md` to refine her voice (she's funny + witty + clean + high-integrity by default — soul.md is for context-specific overlays, not redefinition).

## Your data folder

After `/funnypenny:init`, you'll have:

```
~/.funnypenny/
├── soul.md         FunnyPenny's personality, set by you
├── memory.md       Core Facts · Open Loops · Recent Context
├── user.md         Who you are (identity, background, opinions, skills)
├── preferences.md  Likes, dislikes, defaults
├── contacts.md     People in your life
├── routines.md     Daily / weekly / seasonal rhythms
├── tasks.md        Now / Soon / Someday/Maybe / Done
├── our_recipes.md  Your family canon, this week's plan, recently made
├── grocery_layout.md  Your store's section order + pantry staples
└── my_voice.md     Your writing voice (for drafting in your style)
```

You own these files. Edit them in any text editor. Back them up however you want — a private GitHub repo, iCloud, whatever. The plugin doesn't care.

## Privacy: how the public/private split works

- **Public scaffolding** = this repo. The skill, templates, and slash commands. Safe to share.
- **Your private data** = `~/.funnypenny/`. Outside any repo by default. Never gets pushed.

Belt and suspenders: the `.gitignore` at the root of this repo blocks personal-data filenames at the repo root, so even if you fat-finger a `cp ~/.funnypenny/* .`, nothing gets staged.

## Updating the plugin

When the public scaffolding improves (new sections, refined SKILL.md), pull updates without touching your personal data:

```
/funnypenny:update
```

Runs `git pull` on the plugin and surfaces any new template sections you might want to graft into your real files. Never overwrites them.

## Commands

| Command | What it does |
|---|---|
| `/funnypenny [message]` | Talk to her. Runs the startup ritual and answers. |
| `/funnypenny:init` | First-time setup — bootstraps `~/.funnypenny/` from templates. |
| `/funnypenny:update` | Pulls scaffolding improvements; never touches your data. |
| `/funnypenny:remember <fact>` | Force-save a fact to the right file. |
| `/improve [summary]` | File a GitHub issue against this plugin's repo (bug, feature, improvement, question). Shows a preview before submitting. |

## Why "FunnyPenny"

Every assistant should have a name. This one's named after MoneyPenny — the one who actually runs MI6 — with a little more sense of humor.
