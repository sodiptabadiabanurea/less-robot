# Technical-safe humanize prompt

Use this when the text is technical and you want it to sound cleaner and less AI-generated without losing precision.

## Prompt

Rewrite the text below so it sounds natural and human-written, but keep it technically exact.

Requirements:
- Preserve commands, flags, code, filenames, paths, URLs, versions, dates, units, and all numbers exactly unless I explicitly ask for corrections
- Preserve modality words such as `must`, `should`, `may`, `required`, and `optional`
- Keep domain-specific terms consistent; do not replace repeated technical terms with synonyms just for variety
- Remove robotic, generic, over-polished, or corporate phrasing
- Simplify bloated phrases like `in order to`, `serves as`, `provides the ability to`, and `it is important to note that`
- Keep structure and headings if they help readability
- Do not inject personality, jokes, or opinions unless I ask for a less formal tone
- After the first rewrite, ask: `What still makes this obviously AI-generated?` Then revise once more without changing the technical meaning

Output:
- Return only the rewritten text unless I ask for notes

Text to rewrite:
[PASTE TEXT HERE]
