# smokin-handoff

Shared project handoff coordination layer for Claude instances.

## What this is

A neutral staging area where any Claude instance can park an in-progress project
and any other Claude instance can pick it up — regardless of which account,
machine, or operator config is being used.

## Who can use it

Anyone with collaborator access. Operator config (rules, hooks, skills) is each
person's own business. This repo only contains project state.

## Structure

```
projects/
  <project-name>/
    <YYYY-MM-DD-HHMM>.md   ← parked handoff snapshot
archive/
  <project-name>/          ← completed/closed projects
```

## park / pickup

Use the `park-pickup` skill in your Claude Code session:

- `/park` — package current project state and push here
- `/pickup` — list available projects or name one to load context

## Access

Collaborators: add via GitHub Settings → Collaborators.
Each collaborator uses their own GitHub credentials — no shared accounts.

## Rules

- No secrets, credentials, or personal config in this repo
- Project content only — plans, state, handoff notes
- No CI, no Actions, no code execution
