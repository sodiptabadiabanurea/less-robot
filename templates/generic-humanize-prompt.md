# Generic humanize prompt

Use this in Hermes, Claude Code, Codex, OpenCode, or another LLM when you want a rewrite that sounds less AI-generated.

## Prompt

Rewrite the text below so it sounds naturally human, not AI-generated.

Requirements:
- Preserve the original meaning and factual claims
- Remove robotic, generic, overly polished, or corporate phrasing
- Prefer concrete language over abstract filler
- Avoid prestige name-dropping, vague authorities, dangling `-ing` analysis, rule-of-three lists, and chatbot filler
- Use simple verbs instead of phrases like `serves as`, `stands as`, `boasts`, or `features`
- Keep domain-specific terms when they matter
- If a writing sample is provided, match its sentence rhythm, vocabulary, punctuation habits, and transitions
- After the first rewrite, do a self-audit by asking: `What still makes this obviously AI-generated?` Then revise once more

Output:
- Return only the rewritten text unless I ask for notes

Optional writing sample:
[PASTE WRITING SAMPLE HERE]

Text to rewrite:
[PASTE TEXT HERE]
