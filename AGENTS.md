# AGENTS.md

## Project guidance

This repository contains one Codex skill:

- `education-research-assistant`

Use it for Chinese education research tasks, including Chinese education paper analysis, literature review, research methods, theory framework, quality review, research gaps, citation-style writing, proposal writing, thesis writing, and Obsidian literature notes.

## Preferred workflow

For one paper:

1. Use `paper standard`.
2. Use `quality quick` only if the user asks whether the paper is worth reading.
3. Use `obsidian` only when the user wants a note card.

For multiple papers:

1. Prefer literature cards over raw full PDFs.
2. Use `review standard`.
3. Use `gap standard`.
4. Use `citation paragraph`.

For thesis work:

1. Use `thesis` for title, research questions, outline, abstract, introduction, conclusion, and revision checks.
2. Use `proposal` only for opening report tasks.

## Token control

Do not run every mode by default. If information is missing, write “原文未说明” or “材料未说明”; do not infer.
