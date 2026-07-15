# AGENTS.md

## Project guidance

This repository contains one Codex skill:

- `education-research-assistant`

Use it for Chinese education research tasks: paper analysis, literature review, research methods, theory and analytical frameworks, quality review, research spaces, proposal design, thesis writing, Obsidian notes, primary mathematics, AI in education, and teacher development.

## Task entry

### Single task

When the user asks for one result, run only the matching mode and stop.

### Complete workflow

Identify one target pipeline:

- `paper-to-note`;
- `literature-review`;
- `proposal-design`;
- `thesis-design`.

Then use the user's requested entry style:

1. `guided`: adaptively collect and validate inputs one question at a time, then execute every stage of the selected pipeline.
2. `direct`: use current materials immediately and execute every stage of the selected pipeline, labeling gaps and assumptions.

Do not run all four pipelines simultaneously unless the user explicitly requests four separate deliverables.

If entry style is unspecified, offer one concise choice. Do not ask again when the user already requested step-by-step guidance or direct execution.

## Adaptive guided entry

Read:

- `templates/guided-intake-template.md`;
- `knowledge/adaptive-guidance-bank.md`;
- `templates/research-decision-log-template.md`;
- `templates/session-checkpoint-template.md`;
- `knowledge/output-profiles.md`.

Rules:

- ask only one main question per turn;
- choose the next question by blocking risk, path impact, conflict, and information gain;
- do not repeat confirmed information;
- do not mechanically ask every question in a list;
- update later questions when research type, data conditions, or research focus changes;
- record consequential decisions and excluded alternatives;
- propagate changes to downstream title, questions, theory, methods, instruments, and outline;
- stop questioning and execute the selected pipeline when minimum inputs are met and the user says `执行`.

Supported commands:

- `查看进度`;
- `修改：字段=内容`;
- `跳过`;
- `不确定`;
- `保存进度`;
- `恢复进度`;
- `直接生成`;
- `重新开始`;
- `结束引导`.

`直接生成` switches to direct entry and runs the same selected pipeline with the current input package.

## Checkpoint rule

`保存进度` outputs a compact YAML checkpoint. `恢复进度` uses the supplied checkpoint without repeating confirmed questions.

Do not claim external background persistence. A checkpoint is a portable structured summary supplied to the user.

## Output profiles

Use one output profile:

- `outline`;
- `standard`;
- `submission-ready`;
- `review-ready`.

Default to `standard`. Downgrade when evidence, research conditions, or required formatting are insufficient, and explain why.

## Evidence rule

For document-grounded tasks:

- distinguish `作者明示`, `文本归纳`, `方法建议`, and `材料不足`;
- locate evidence by page, section, table, or identifiable position when possible;
- never invent authors, years, sources, policies, theories, data, or findings;
- do not convert absence in the provided material into absence in the whole field.

Read `knowledge/evidence-protocol.md`.

## Research design rule

Before proposing methods or an outline:

1. clarify object and boundaries;
2. identify research type;
3. define research questions;
4. align each question with evidence, data, method, analysis, and chapter;
5. revise questions that cannot be answered with available data.

Read `knowledge/research-type-routing.md` and `knowledge/thesis-writing-system.md`.

## Pipeline definitions

### `paper-to-note`

```text
material check
→ paper standard
→ optional quality quick
→ obsidian
→ field completeness check
```

### `literature-review`

```text
inventory and deduplication
→ fact cards
→ screening
→ review matrix
→ thematic synthesis
→ research space
→ citation section
→ evidence coverage check
```

### `proposal-design`

```text
title and conditions
→ evidence base and research space
→ research type
→ theory/analytical framework
→ method and instrument design
→ alignment matrix
→ proposal
→ checklist
```

### `thesis-design`

```text
title
→ concept boundaries
→ research questions
→ research type and outline
→ theory
→ method
→ alignment matrix
→ chapter plan
→ checklist
```

## Scope and token control

- default to `standard`, not `deep`;
- do not repeat source text or earlier stage outputs;
- do not fill unrelated optional sections;
- summarize stage handoffs;
- if a quality gate fails, fix or stop rather than silently continuing.
