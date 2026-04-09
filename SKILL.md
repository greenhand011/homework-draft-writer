---
name: homework-draft-writer
description: Read homework, assignment, problem set, worksheet, lab, coursework, or lab report files and create a structured Markdown draft in the same folder. Use when a user provides a PDF, DOCX, image, notebook, code file, text file, or assignment folder path and wants every question extracted, solved or scaffolded with student-style working, formulas rewritten as Markdown math, code or experiments run when needed, uncertainty called out explicitly, and the result saved as one editable `.md` file instead of a fabricated polished final submission.
---

# Homework Draft Writer

## Overview

Turn one homework artifact into one editable Markdown draft saved beside the source file. Solve as much as possible, but present the work as a student's submission draft with reasoning, derivations, code, results, and clearly marked gaps instead of pretending every uncertain detail is known.

## Quick Start

1. Resolve the user-provided path.
2. Read the entire assignment before drafting any answer.
3. Count the questions and note any parsing risk.
4. Print the required 3-line brief report.
5. Write or update the Markdown file in the same folder using the folder name.
6. Keep only the source file and the final Markdown unless temporary parsing artifacts are strictly necessary, then delete them before finishing.

## Input Handling

- Prefer a direct file path. Accept a folder path only when one assignment source is obvious inside it; otherwise ask one short clarifying question.
- Support PDF, DOCX, images, Markdown, plain text, notebooks, source files, spreadsheet exports, and mixed assignment folders when tools allow.
- Never modify the original assignment file.
- Prefer direct text extraction first. Use OCR only when the source is scanned or image-based.
- If formulas, tables, or figures are partially unreadable, stop short of guessing and record the exact question or subquestion affected.

## Extraction Workflow

### 1. Read Everything

- Read the entire assignment before writing `Question 1`.
- Preserve numbering, subparts, constraints, grading cues, dataset names, and submission rules that affect the answers.
- If appendix pages or rubric pages change how questions should be answered, incorporate them.

### 2. Build a Question Map

- Identify the total number of main questions.
- Track subparts under the relevant main question.
- Separate actual questions from instructions such as formatting rules or submission notes.

### 3. Assess Reliability

- Report the total recognized question count.
- Report whether images, tables, or formulas were difficult to parse.
- Report the output Markdown path.
- If any part is not reliable, explicitly say which question cannot be reliably recognized.
- Do not fill missing content by guesswork unless the missing detail is trivial and you label it as an inference.

## Output File Rule

- Save the output Markdown in the same directory as the source file.
- Derive the filename from the source file's parent folder name.
- Example: `C:\course\PS-7\assignment.pdf` -> `C:\course\PS-7\PS-7.md`.
- Use the same folder name as the top-level heading: `# PS-7`.
- If the target Markdown already exists, update it in place instead of creating duplicates unless the user asks for a second file.

## Writing Rules

- Match the language of the assignment unless the user asks for another language.
- Use the exact question order from the source.
- Read [references/output-template.md](references/output-template.md) before writing the final Markdown.
- For each main question, include at least:
  - `### Problem`
  - `### Approach`
  - `### Key Steps`
  - `### Draft Answer`
  - `### What I Still Need to Fill In`
- Keep the work editable. Write like a strong student draft, not like an omniscient solution manual.
- Quote the original question text when short and reliable. Otherwise provide a careful condensed restatement.

## Content Rules by Question Type

### Math and Derivation Questions

- Reformat formulas as Markdown math.
- Keep each formula on one Markdown line. Do not split a single equation across multiple lines.
- Show the derivation structure step by step. Do not jump from setup to final result without intermediate transformations.
- If arithmetic or algebra is lengthy, summarize only after the key steps are explicit.

### Programming Questions

- Put code blocks inside the Markdown unless the user explicitly asks for separate source files.
- Provide the implementation idea, core code, important comments, and the actual run result when execution is possible.
- If code execution fails because the environment is missing a package, compiler, dataset, or interpreter, say so precisely and leave the missing piece in `### What I Still Need to Fill In`.

### Experiment, Plotting, or Data Analysis Questions

- Actually run the relevant code or computation when possible.
- Add `### Result`, `### Analysis`, and `### Conclusion` for that question when the task calls for them.
- Fill these sections with observed outputs rather than placeholders whenever execution is possible.
- Avoid creating extra artifact files unless the assignment truly requires them. If temporary files are needed for parsing or plotting, clean them up before finishing unless the user asked to keep them.

## Required Brief Report

Before closing out, print a concise summary like this:

```text
Recognized questions: 4
Parsing issues: Figure in Question 3 is blurry; everything else is readable
Generated file: C:\course\PS-7\PS-7.md
```

Use the user's language for this report. If nothing is hard to parse, say so plainly.

## Failure Handling

- If the assignment cannot be read reliably, do not fabricate.
- State exactly which file, page, question, or region failed.
- Still create the Markdown if enough of the assignment is readable to be useful, and put the unresolved parts in `### What I Still Need to Fill In`.
- If almost nothing is readable, stop after explaining the blocker instead of producing a misleading draft.

## Reference

- Read [references/output-template.md](references/output-template.md) before writing the final Markdown.
- Keep format scaffolding in the reference file instead of duplicating large templates here.
