# AGENTS.md

## Project guidance

This repository contains one Codex skill:

- `education-research-assistant`

Use it for Chinese education research tasks: paper analysis, literature review, research methods, theory and analytical frameworks, quality review, research spaces, proposal design, thesis writing, Obsidian notes, primary mathematics, AI in education, and teacher development.

## Entry selection

Choose the task entry before execution.

### Single task

When the user asks for one result, run only the matching mode and stop.

Examples: one paper analysis, one questionnaire design, one title revision, one review paragraph.

### Complete workflow

When the user wants a complete research process, identify one target pipeline:

- `paper-to-note`;
- `literature-review`;
- `proposal-design`;
- `thesis-design`.

Then use the user's requested entry style:

1. **Guided entry (`guided`)**: ask one key question per turn, build a verified workflow input package, and then execute every stage of the selected pipeline.
2. **Direct entry (`direct`)**: use the available material immediately and execute every stage of the selected pipeline; label missing information, tentative inputs, and necessary assumptions.

“Execute all stages directly” means all stages of the selected pipeline. Do not run all four pipelines simultaneously unless a user explicitly requests four separate deliverables.

If the user has not chosen an entry style, show this choice:

```text
A. 引导式：每次只确认一个关键问题，梳理完成后执行完整工作流。
B. 直接式：根据现有材料立即执行所选工作流的全部阶段，缺失内容明确标注。
```

Do not ask again when the user already said “一步一步引导” or “直接完成，不要提问”.

The two entry styles must use the same selected-pipeline stages, quality gates, and final deliverables. Guided entry is not a separate simplified product.

Read `templates/guided-intake-template.md` for guided intake and `templates/workflow-state-template.md` for workflow execution.

## Guided entry rules

- Ask only one main question per turn.
- Do not repeat information already confirmed in the current conversation.
- Ask the most consequential missing question first.
- Allow `查看进度`, `修改：字段=内容`, `跳过`, `不确定`, `直接生成`, `重新开始`, and `结束引导`.
- `直接生成` switches to direct entry and runs the same selected pipeline with the current input package.
- Once minimum inputs are met and the user says `执行`, stop asking isolated questions and run the full selected pipeline.

## Direct entry rules

- List available inputs, missing inputs, tentative inputs, and necessary assumptions.
- Do not reduce the number of stages in the selected pipeline merely because the user chose direct entry.
- Complete all supported stages in the current response.
- A critical failure can stop the affected stage, but unrelated deliverables should still be completed where possible.

## Evidence rule

For document-grounded tasks:

- distinguish `作者明示`, `文本归纳`, `方法建议`, and `材料不足`;
- locate evidence by page, section, table, or identifiable text position when possible;
- never invent authors, years, sources, policies, theories, data, or findings;
- do not convert absence in the provided material into absence in the whole field.

Read `knowledge/evidence-protocol.md`.

## Research design rule

Before proposing methods or a thesis outline:

1. clarify the research object and boundaries;
2. identify the research type;
3. define research questions;
4. align each question with evidence, data source, method, analysis, and chapter;
5. remove or revise questions that cannot be answered with available data.

Read `knowledge/research-type-routing.md` and `knowledge/thesis-writing-system.md`.

## Pipeline definitions

### One paper

```text
material check
→ paper standard
→ quality quick when requested
→ obsidian
→ field completeness check
```

### Multiple papers

```text
inventory and deduplication
→ fact card for each paper
→ relevance/quality screening
→ review matrix
→ thematic synthesis and research development
→ gap
→ citation section
→ evidence coverage check
```

### Proposal design

```text
title and research conditions
→ evidence base and research space
→ research type
→ theory/analytical framework
→ method and instrument design
→ alignment matrix
→ proposal
→ checklist
```

### Thesis design

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

- Default to `standard`, not `deep`.
- Do not repeat the source text.
- Do not fill optional template sections unrelated to the request.
- In workflow execution, summarize earlier stages instead of reproducing them.
- If a stage fails its quality gate, fix or stop; do not silently continue.
