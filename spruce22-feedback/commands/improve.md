---
description: File a GitHub issue against the spruce22-plugins repo to suggest a fix or improvement. Shows a preview before submitting.
argument-hint: [optional one-line summary of what you'd like to see fixed or added]
---

You are helping the user file a GitHub issue against `Army0fBobs/spruce22-plugins`. Walk them through it conversationally, then preview, then submit.

## Step 1: Gather

If $ARGUMENTS is provided, use it as the working summary line and skip directly to clarification.

If $ARGUMENTS is empty, ask: "What would you like to see fixed or added? Give me a one-line summary."

## Step 2: Clarify

Ask exactly these three questions, in order, conditionally skipping any whose answer is already obvious from the summary line:

1. **Which plugin?** Options: `funnypenny`, `initiative-creator`, `spruce22-feedback`, or `general` (about the marketplace as a whole). If the summary clearly names one, confirm rather than re-ask.

2. **Issue type?** Options: `bug`, `feature`, `improvement`, `question`. Pick what fits.

3. **Anything else worth including?** Steps to reproduce (if a bug), expected vs. actual behavior, why this matters to you, or related links. Free text — they can say "nothing more."

## Step 3: Preview

Build the issue with this structure:

```
TITLE: [<plugin>] <type>: <one-line summary>

BODY:

**Plugin:** <plugin>
**Type:** <bug | feature | improvement | question>

## What

<one-line summary expanded into a paragraph if needed>

## Detail

<the "anything else" content, or "—" if none>

---
*Filed via `/improve` from spruce22-feedback*
```

Show the user the preview formatted exactly like that. Then ask: **"Submit this issue, or edit first?"** Wait for their response. Accept any of: `submit`, `yes`, `go`, `edit`, `no`, or specific edit instructions.

If they want edits, accept the changes and re-show the preview. Loop until they confirm submission.

## Step 4: Submit

Try `gh` first. If `gh` is installed and authenticated to GitHub, run:

```bash
gh issue create \
  --repo Army0fBobs/spruce22-plugins \
  --title "<title from preview>" \
  --body "<body from preview>"
```

(Use a heredoc for the body to handle multiline content cleanly.)

If `gh issue create` succeeds, capture the issue URL from its stdout and report:

> **Filed:** `<issue URL>`. Bob will see it in the repo's issues. Thanks for the feedback.

If `gh` is missing, unauthenticated, or fails for any reason: **fall back to the browser path**. Build a URL of the form:

```
https://github.com/Army0fBobs/spruce22-plugins/issues/new?title=<urlencoded-title>&body=<urlencoded-body>
```

Print the URL and instruct the user: "I couldn't submit directly via `gh` (reason: <error>). Open this in your browser to file the issue with the content prefilled — you'll need to click 'Submit' yourself:" then output the URL on its own line so it's clickable.

## Rules

- **Never submit without showing the preview and getting explicit confirmation.** No surprise issues.
- **Don't include the user's personal data, environment details, or session content** unless they explicitly typed it into "anything else." This is a feedback channel, not a telemetry beacon.
- **Don't auto-tag, auto-assign, or set milestones.** Bob curates from his end.
- **One issue per `/improve` invocation.** If the user mentions multiple things, ask which to file first and offer to run `/improve` again for the others.
- **If `gh` succeeds**, do not also open the browser URL. One submission, one issue.
