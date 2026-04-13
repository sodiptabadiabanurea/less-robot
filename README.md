# less-robot

A small prompt pack and Hermes skill for making writing sound less robotic without wrecking the meaning.

This repo is built around one practical goal:
- remove obvious AI-writing patterns
- keep the original point intact
- support voice matching when a writing sample exists
- stay conservative for technical docs so precision does not get lost

## What is inside

- `SKILL.md`
  - Hermes-native humanizer skill
- `templates/generic-humanize-prompt.md`
  - reusable prompt for Claude, Codex, OpenCode, or other LLMs
- `templates/technical-humanize-prompt.md`
  - safer prompt for technical writing
- `references/pattern-cheatsheet.md`
  - fast checklist of common AI-writing tells
- `references/technical-checklist.md`
  - verification checklist for technical rewrites
- `references/source-notes.md`
  - adaptation notes and attribution

## Good fit for

- blog drafts
- product copy that feels too corporate
- emails and writeups that sound too polished or synthetic
- technical docs, API docs, runbooks, postmortems, and changelogs that need cleanup without changing commands, flags, numbers, or requirements

## Hermes usage

Copy this repo's contents into a Hermes skill directory, or use the included files as reference material.

Suggested layout:

```text
~/.hermes/skills/productivity/humanizer/
  SKILL.md
  templates/
  references/
```

## Generic AI usage

Use one of the prompt templates:
- `templates/generic-humanize-prompt.md`
- `templates/technical-humanize-prompt.md`

The technical template is the safer default for docs that contain commands, paths, versions, thresholds, or RFC-style wording like `must`, `should`, and `may`.

## Why this exists

A lot of AI-cleanup prompts overcorrect. They make text shorter, but also flatter, vaguer, or less accurate. This pack tries to do the opposite: reduce the obvious AI smell while keeping meaning, specificity, and technical precision.

## Attribution

This repo adapts ideas from:
- blader/humanizer: https://github.com/blader/humanizer
- Wikipedia: Signs of AI writing / WikiProject AI Cleanup

Source repo license: MIT.
This adaptation is also distributed under MIT. See `LICENSE`.
