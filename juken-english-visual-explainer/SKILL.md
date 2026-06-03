---
name: juken-english-visual-explainer
description: 大学受験英語を、問題に最適な形式で完全解説する。英作文添削、和文英訳、自由英作文、要約英作文、英文解釈、長文読解、文法・語法問題、リスニング学習、選択肢比較、構文可視化、段落構造、修飾関係、誤答分析を扱うときに使う。短い問題はチャットで簡潔に解説し、構造、論理、根拠、答案差分を視覚化すると理解が深まる場合や、ユーザーがHTML教材を求めた場合は、動的UIを備えた単一HTML教材を生成する。
---

# Juken English Visual Explainer

## Core Rule

Choose the clearest output format for the English task. Use a concise chat explanation for simple tasks. Create one standalone HTML lesson when interactive visualization materially improves understanding or when the user explicitly requests HTML. Cover entrance-exam English broadly, while giving composition tasks especially detailed feedback.

When generating HTML, treat required elements as a quality checklist, not a fixed layout. Choose the explanation order, emphasis, and UI that make the specific task easiest to understand.

## Workflow

1. Read the input carefully.
   - For images, extract all visible passages, questions, choices, instructions, annotations, and user-written answers.
   - Distinguish the original text from handwritten work and inferred structure.
2. Classify the task.
   - Composition: read `references/composition.md` and `references/scoring-rubric.md`.
   - Reading or interpretation: read `references/reading.md`.
   - Grammar or usage: read `references/grammar.md`.
   - Listening: read `references/listening.md`.
   - Mixed tasks: load only the relevant combination.
3. Solve or assess the task completely before building the UI.
   - Preserve nuance, context, and acceptable alternatives.
   - For user answers, explain the first meaningful divergence and provide an improved answer.
4. Choose visualization from `references/common-ui-patterns.md`.
   - Use only interactions that reveal linguistic structure, reasoning, or revision choices.
   - Adapt the explanation order to the task. Do not force every lesson into identical tabs or steps.
5. Choose the output format.
   - Use chat for a short vocabulary question, a simple grammar distinction, a brief translation check, or a small correction that does not benefit from layered comparison.
   - Generate HTML for complex sentence structure, long-passage logic, evidence mapping, multi-choice comparison, substantial composition feedback, summary selection, or any explicit HTML request.
   - When uncertain, prefer the simpler format unless HTML clearly improves learning.
6. When HTML is appropriate, generate one standalone `.html` file.
   - Use only HTML, CSS, JavaScript, SVG, and Canvas.
   - Do not use external libraries, CDNs, remote fonts, remote images, or network access.
   - Start from `assets/single-html-template.html` when useful.
7. Verify the response or artifact.
   - For chat responses, confirm the explanation is complete and proportionate.
   - Confirm the file opens by itself.
   - Test tabs, filters, buttons, toggles, highlighting, and answer visibility.
   - Confirm that no necessary explanation exists only in chat.
8. Reply appropriately.
   - For chat-only explanations, answer directly and completely.
   - For HTML lessons, keep chat brief.
   - Mention the generated HTML file path.
   - State that the complete explanation is inside the HTML.
   - Mention the main interaction.

## When to Use HTML

Use HTML when at least one of these is true:

- The user explicitly asks for HTML, a visual lesson, an interactive explanation, or a reusable study material.
- Clause structure, modifiers, pronoun references, or omitted elements are difficult to follow in plain text.
- A long passage benefits from paragraph mapping, evidence links, or choice comparison.
- A composition answer needs substantial revision comparison, scoring diagnostics, or reusable-expression filters.
- A summary task benefits from showing retained, omitted, and paraphrased information.
- A grammar task benefits from interactive contrast among several choices.

Do not generate HTML merely because the skill can. Use chat when a direct explanation is clearer and faster.

## HTML Lesson Requirements

- Apply these requirements only when generating HTML.
- Keep the app Japanese by default unless the user asks otherwise.
- Include the original question, a complete explanation, the final or model answer, and any necessary alternatives inside the HTML.
- Preserve the original English text accurately.
- Connect highlights and UI state to the explanation.
- Make the final answer easy to find without replaying interactions.
- Use accessible controls and stable dimensions.
- Keep visual decoration restrained. The UI should clarify English, not distract from it.

## Teaching Priorities

- Composition: show the learner's answer, issue categories, revision rationale, improved answer, alternatives, and reusable expressions.
- Reading: show paragraph roles, logical connections, evidence locations, pronoun references, and answer-choice comparison.
- Interpretation: show clause boundaries, main structure, modifiers, omitted elements, and natural Japanese rendering.
- Grammar: show the deciding rule, contrastive examples, why distractors fail, and a compact reusable takeaway.
- Listening: show transcript segments, sound changes, key expressions, evidence timing, and answer-choice comparison when a transcript or audio-derived text is available.

## Completion Checklist

- The HTML contains the full problem or supplied text.
- The HTML contains a complete explanation, not just labels.
- The explanation order fits the task instead of mechanically following a template.
- Any user answer is preserved and compared fairly.
- The final answer or improved answer is visible and unambiguous.
- For HTML lessons, chat can remain short because the HTML is self-sufficient.
- For chat-only answers, the explanation is complete without an HTML artifact.

## Reusable Resources

- `assets/single-html-template.html`: adaptable standalone English lesson shell.
- `references/common-ui-patterns.md`: shared visual and interaction patterns.
- `references/composition.md`: detailed composition, translation, and essay feedback rules.
- `references/scoring-rubric.md`: evidence-based scoring guidance for entrance-exam composition.
- `references/reading.md`: reading comprehension and sentence interpretation rules.
- `references/grammar.md`: grammar and usage explanation rules.
- `references/listening.md`: listening-oriented lesson rules.
- `references/system-prompt-full.md`: self-contained prompt for non-Codex LLM projects.
