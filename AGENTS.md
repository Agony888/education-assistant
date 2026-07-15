# AGENTS.md

## Project guidance

This repository contains one Codex skill:

- `education-research-assistant`

Use it for Chinese education research tasks: paper analysis, literature review, research methods, theory and analytical frameworks, quality review, research gaps, proposal design, thesis writing, Obsidian notes, primary mathematics, AI in education, and teacher development.

## Operating rule

Choose between two execution styles:

1. **Single mode**: the user asks for one result. Run only the requested mode and stop.
2. **Workflow mode**: the user explicitly asks for a complete process, continuous execution, or a workflow. Use `workflow` and preserve stage outputs with `templates/workflow-state-template.md`.

Do not automatically chain modes for a simple request.

## Evidence rule

For document-grounded tasks:

- distinguish `作者明示`, `文本归纳`, `方法建议`, and `材料不足`;
- locate evidence by page, section, table, or identifiable text position when possible;
- never invent authors, years, sources, policies, theories, data, or findings;
- do not convert absence in the provided material into absence in the whole field.

Read `knowledge/evidence-protocol.md` for detailed rules.

## Research design rule

Before proposing methods or a thesis outline:

1. clarify the research object and boundaries;
2. identify the research type;
3. define research questions;
4. align each question with evidence, data source, method, analysis, and chapter;
5. remove questions that cannot be answered with available data.

Read `knowledge/research-type-routing.md` and `knowledge/thesis-writing-system.md`.

## Preferred workflows

### One paper

- Use `paper standard` for analysis.
- Use `quality quick` only when the user asks whether it is worth reading.
- Use `obsidian` only when the user asks for a note card.

### Multiple papers

- Establish a fact card for each paper.
- Deduplicate and screen relevance before synthesis.
- Use `review matrix`, then thematic synthesis.
- Use `gap` only after the evidence base is clear.
- Use `citation section` only with verified author/year information.

### Proposal design

```text
title and conditions
→ gap
→ research type
→ theory framework
→ method design
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
- Do not fill every optional template section when it is unrelated to the request.
- In workflow mode, summarize earlier stages instead of reproducing them.
- If a stage fails its quality gate, fix or stop; do not silently continue.
