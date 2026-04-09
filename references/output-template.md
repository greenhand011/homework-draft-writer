# Output Template

Use the source file's parent folder name for both the output filename and the top-level title.

- Example source: `C:\course\PS-7\assignment.pdf`
- Output file: `C:\course\PS-7\PS-7.md`
- Top-level title: `# PS-7`

Use this structure and replace every placeholder with real content:

```markdown
# <folder-name>

## Question 1

### Problem
<Quote the prompt directly, or provide a reliable condensed restatement>

### Approach
<Explain how to solve it and why this approach fits>

### Key Steps
1. <List derivation, decomposition, program, or experiment steps>
2. <Do not skip essential transitions>
3. <Map subparts clearly when the question has parts>

### Draft Answer
<Write the answer body as a student draft; include derivation, code, explanation, run output, or analysis as needed>

### What I Still Need to Fill In
- <Write None. when the question is complete>

## Question 2

### Problem
<...>

### Approach
<...>

### Key Steps
1. <...>

### Draft Answer
<...>

### What I Still Need to Fill In
- <...>
```

## Optional Expansion for Labs, Experiments, and Plots

When a question requires empirical output, add these sections after `### Draft Answer` and fill them with observed results whenever possible:

```markdown
### Result
<Observed run output, table summary, image takeaway, or experiment observation>

### Analysis
<Explain the result, error source, or notable behavior>

### Conclusion
<State the final conclusion and tie it back to the prompt>
```

## Formula Formatting Rules

- Keep each formula on one Markdown line.
- Use inline math like `$a^2 + b^2 = c^2$` for short expressions.
- Use display math on a single line like `$$\sum_{i=1}^{n} i = \frac{n(n+1)}{2}$$` for longer expressions.
- Do not break one equation across multiple Markdown lines.

## Reliability Rules

- If a question is not reliably readable, say so explicitly in `### Problem` or `### What I Still Need to Fill In`.
- Do not invent missing constants, labels, table entries, or figure content.
- If code or experiments cannot be run, record the exact blocker instead of pretending the result exists.
