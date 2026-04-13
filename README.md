<p align="center">
  <img src="./assets/less-robot-hero.svg" alt="less-robot hero illustration" width="360" />
</p>

<p align="center">
  <a href="https://github.com/sodiptabadiabanurea/less-robot/releases/tag/v1.1.0">
    <img src="https://img.shields.io/badge/release-v1.1.0-EA580C?style=for-the-badge" alt="Release v1.1.0" />
  </a>
  <a href="https://x.com/sodiptabb23?s=21">
    <img src="https://img.shields.io/badge/twitter-@sodiptabb23-1DA1F2?style=for-the-badge&logo=x&logoColor=white" alt="X profile @sodiptabb23" />
  </a>
  <a href="./LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-2563EB?style=for-the-badge" alt="MIT License" />
  </a>
</p>

<h1 align="center">less-robot</h1>

<p align="center">
  <strong>Make AI writing sound human without losing meaning or technical precision.</strong>
</p>

<p align="center">
  A small prompt pack and Hermes skill for cleaning up robotic prose, matching voice when it helps, and staying conservative with technical docs.
</p>

## What this repo includes

- `SKILL.md`
  - the Hermes-native humanizer skill
- `templates/generic-humanize-prompt.md`
  - a reusable prompt for Claude, Codex, OpenCode, or other LLMs
- `templates/technical-humanize-prompt.md`
  - a safer prompt for technical writing
- `references/pattern-cheatsheet.md`
  - a fast checklist of common AI-writing tells
- `references/technical-checklist.md`
  - a verification checklist for technical rewrites
- `references/source-notes.md`
  - adaptation notes and attribution

## When to use it

Good fit for:
- blog drafts
- product copy that feels too corporate
- emails and internal writeups that sound too polished or synthetic
- technical docs, API docs, runbooks, postmortems, changelogs, and setup guides that need cleanup without changing commands, flags, numbers, or requirements

## Quick start

### Option 1: Use it in Hermes

Copy the files into a Hermes skill directory:

```text
~/.hermes/skills/productivity/humanizer/
  SKILL.md
  templates/
  references/
```

Then invoke it when you want to humanize text, reduce robotic tone, or clean up technical writing without losing precision.

### Option 2: Use it with any AI tool

Start with one of these prompt templates:
- `templates/generic-humanize-prompt.md`
- `templates/technical-humanize-prompt.md`

If the text contains commands, paths, versions, thresholds, or RFC-style words like `must`, `should`, and `may`, use the technical template first.

## What makes this different

A lot of AI-cleanup prompts overcorrect. They make text shorter, but also flatter, vaguer, or less accurate.

This repo tries to do the opposite:
- reduce the obvious AI smell
- keep specificity
- preserve technical meaning
- avoid forced slang or fake personality
- use voice matching only when it actually helps

## Before / after

### Before

> AI-assisted documentation serves as a crucial foundation for modern engineering workflows, enabling teams to streamline collaboration, enhance clarity, and ensure alignment across stakeholders.

### After

> AI can help teams write docs faster, especially for repetitive stuff. The problem is that the output often sounds polished without saying much. You still need someone to cut the filler and make the meaning clear.

That is the point of this repo: less brochure language, less fake polish, more real signal.

## Technical-safe mode

The technical flow is conservative by default.

It is designed to preserve:
- commands and flags
- code, config keys, filenames, paths, and URLs
- versions, dates, units, thresholds, and numbers
- modality words such as `must`, `should`, `may`, `required`, and `optional`
- repeated technical terms that should stay consistent

It still removes fluff, hype, and generic corporate padding. The point is to make technical writing cleaner, not warmer at the cost of accuracy.

## Suggested workflow

1. Classify the text: technical, business, or casual
2. If available, use a writing sample for voice matching
3. Remove obvious AI patterns and filler
4. Rewrite with simpler, more concrete phrasing
5. Run a final anti-AI pass
6. For technical text, verify that meaning and requirements did not change

## Example use cases

### Humanize a generic draft
Use `templates/generic-humanize-prompt.md` when the text is too polished, repetitive, or obviously machine-written.

### Clean up technical docs safely
Use `templates/technical-humanize-prompt.md` when the text contains:
- shell commands
- config examples
- API requirements
- incident notes
- setup instructions
- postmortem findings

Then verify the result with `references/technical-checklist.md`.

## Attribution

This repo adapts ideas from:
- blader/humanizer: https://github.com/blader/humanizer
- Wikipedia: Signs of AI writing / WikiProject AI Cleanup

The source repo is MIT-licensed.
This adaptation is also distributed under MIT. See `LICENSE`.
