# Juken English Visual Explainer / 受験英語ビジュアル解説

大学受験英語の問題を、問題に最適な形式で解説するCodexスキルです。短い問題はチャットで簡潔に解説し、英文構造・長文の根拠対応・英作文の答案差分などを可視化すると理解が深まる場合は、単一HTML教材を生成します。

This Codex skill explains Japanese university entrance-exam English tasks in the clearest format for each case. Simple tasks can be answered directly in chat, while complex sentence structure, passage evidence, or composition revisions can be turned into self-contained interactive HTML lessons.

## Features / 特徴

- 英作文、和文英訳、要約英作文、英文解釈、長文読解、文法・語法、リスニング関連問題に対応
- 英作文では、修正前後の比較、修正理由、採点目安、再利用表現を表示
- 大学公式の採点基準がある場合は優先し、ない場合は推定評価として扱う
- HTMLが有効な場合だけ、構文ハイライト、根拠マッピング、答案差分UIを生成
- LLMプロジェクト用の汎用システムプロンプトも同梱

- Supports composition, Japanese-to-English translation, summary writing, reading, sentence interpretation, grammar, usage, and listening-related tasks.
- For composition, shows before/after revisions, revision rationale, scoring diagnostics, and reusable expressions.
- Prioritizes official university rubrics when available; otherwise labels evaluations as estimates.
- Generates HTML only when visualization improves understanding.
- Includes a general-purpose system prompt for non-Codex LLM projects.

## How to Use with Codex / Codexでの使い方

Copy this folder into your Codex skills directory, then ask Codex to use the skill.

```text
Use $juken-english-visual-explainer to fully explain this entrance-exam English task in the clearest format.
```

Example prompts are available in [examples/prompts.md](examples/prompts.md).

## How to Use with Other LLMs / 他のLLMでの使い方

Paste the full system prompt into your LLM project's system prompt area:

[references/system-prompt-full.md](references/system-prompt-full.md)

For composition scoring guidance, see:

[references/scoring-rubric.md](references/scoring-rubric.md)

## Repository Structure / 構成

```text
.
├── SKILL.md
├── agents/openai.yaml
├── assets/single-html-template.html
├── references/system-prompt-full.md
├── references/composition.md
├── references/scoring-rubric.md
├── references/reading.md
├── references/grammar.md
├── references/listening.md
├── references/common-ui-patterns.md
└── examples/prompts.md
```

## Notes / 注意

- This repository does not include real entrance-exam passages, copyrighted problem text, or generated answer samples.
- Use original or fictional prompts for public examples unless you have permission to quote the source.
- Scoring guidance is educational. It should not be presented as an official score unless it follows a provided official rubric.

- このリポジトリには、実在する入試長文・問題本文・生成済み答案例は含めていません。
- 公開例には自作・架空プロンプトを使い、実在問題を転載する場合は許諾や引用条件を確認してください。
- 採点は学習用の目安です。大学公式基準に基づく場合を除き、公式得点として扱わないでください。

## License / ライセンス

MIT License. See [LICENSE](LICENSE).
