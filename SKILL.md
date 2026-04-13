---
name: humanizer
description: Rewrite text so it sounds less AI-generated and more naturally human while preserving meaning. Use when the user asks to humanize text, reduce robotic/corporate tone, match a provided writing sample, or clean up technical writing without losing precision. Adapted for Hermes from blader/humanizer and Wikipedia's Signs of AI writing guidance.
version: 1.1.0
author: Hermes Agent + adapted from blader/humanizer
license: MIT
metadata:
  hermes:
    tags: [Writing, Editing, Voice, Style, Humanization, Anti-AI]
    related_skills: []
---

# Humanizer

Use this skill when the user asks to:
- humanize text
- make writing sound less AI-generated, less robotic, less generic, or less corporate
- match their own writing style from a sample
- rewrite polished-but-dead prose so it has a more natural voice

This skill is Hermes-native but the method is general and works for any AI writing workflow.

## Goals

1. Preserve meaning and factual accuracy
2. Remove obvious AI-writing markers
3. Match the requested tone or the user's sample
4. Keep specificity; do not replace detail with vaguer prose
5. End with a second-pass anti-AI audit

## Workflow

1. Classify the text first:
   - technical docs/specs/runbooks/incidents/changelogs/API docs
   - business/professional writing
   - casual/personal writing
   Use the least invasive mode that still removes AI markers.
2. If the user gave a writing sample, extract:
   - sentence length and rhythm
   - vocabulary level
   - punctuation habits
   - paragraph openings and transitions
   - recurring phrases or tics
3. Scan the target text for common AI markers:
   - inflated significance or sweeping claims
   - prestige name-dropping or vague authorities
   - dangling `-ing` pseudo-analysis
   - promotional adjectives and brochure language
   - stock AI words like `additionally`, `crucial`, `pivotal`, `landscape`, `showcase`, `underscore`, `vibrant`, `testament`
   - copula avoidance: `serves as`, `stands as`, `boasts`, `features`
   - `not just X, but Y`, tailing negations, rule-of-three lists
   - synonym cycling
   - passive or actorless fragments when the actor matters
   - em-dash, bold, emoji, and signposting overuse
   - chatbot filler like `great question`, `I hope this helps`, `let me know if...`
   - filler and hedging like `in order to`, `due to the fact that`, `could potentially`
   - generic endings and empty optimism
4. Rewrite with these preferences:
   - concrete facts over abstraction
   - simple verbs over inflated phrasing
   - natural repetition over forced synonym swaps
   - varied rhythm instead of uniform sentence shape
   - mild personality or opinion when appropriate
   - specificity over polish
5. If the text is technical, switch to Technical-safe mode before finalizing.
6. Run a final self-audit:
   - `What still makes this obviously AI-generated?`
   - `Now make it not obviously AI-generated.`
   Revise once more.

## Technical-safe mode

Use this by default for technical content.

### Preserve exactly
- commands, flags, code, config keys, filenames, paths, URLs, versions, units, dates, and numbers
- RFC-style modality and certainty words like `must`, `should`, `may`, `required`, `optional`
- domain terms that need consistent repetition

### Change carefully
- remove fluff, hype, and generic corporate padding
- simplify bloated phrasing without changing operational meaning
- keep headings and structure when they improve scanability
- keep passive voice if it is standard and clearer in technical context
- do not inject personality, jokes, or opinion into specs, runbooks, postmortems, or compliance text unless explicitly asked

### Preferred edits for technical text
- `in order to` -> `to`
- `serves as` -> `is`
- `provides the ability to` -> `lets you` or `allows`
- remove empty openers like `it is important to note that`
- replace vague claims with exact behavior

## Rules

- Do not over-humanize technical, legal, or compliance text into something less accurate
- Do not inject opinions into factual documents unless the tone clearly allows it
- When voice-matching, imitate writing patterns, not private life details
- Keep the original meaning, claims, and level of certainty intact
- If the source is already strong, do a light edit instead of an unnecessary rewrite
- For technical text, optimize for precision first and warmth second

## Output modes

- Default: return only the rewritten text
- For technical content: prefer a conservative rewrite by default
- If the user asks for explanation: add a short bullet list of the main AI markers removed
- If helpful: provide 2 versions, one safer and one more voicey

## Pitfalls

- Swapping AI-sounding prose for sterile prose
- Making text shorter but also vaguer
- Overusing slang to prove the text is human
- Removing domain-specific terms that should stay
- Leaving polished intros or outros that still feel machine-written
- Rephrasing commands, version numbers, thresholds, or requirements in technical text
- Accidentally changing `must/should/may` semantics

## Cross-AI use

For reusable prompts in other tools, see:
- `templates/generic-humanize-prompt.md`
- `references/source-notes.md`
- `references/pattern-cheatsheet.md`

## Attribution

Adapted for Hermes from:
- blader/humanizer (MIT): https://github.com/blader/humanizer
- Wikipedia: Signs of AI writing / WikiProject AI Cleanup
