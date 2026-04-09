# Assignment Draft Skill / 作业草稿生成 Skill

A reusable skill for reading assignment files and generating structured Markdown working drafts for study, revision, and completion.

一个可复用的 skill，用于读取作业文件并生成结构化的 Markdown 作答草稿，方便学习、整理、补全与最终修改。

---

## English

### Overview

Assignment Draft Skill helps turn an assignment file into an editable Markdown draft.

Instead of only dumping raw extracted text, it organizes the assignment into a clean working structure so the user can continue solving, revising, verifying, and polishing the content in a more systematic way.

This skill is designed as a **study and drafting assistant**, not as a blind answer generator.

### What It Does

Given an assignment file path, this skill will:

1. Read and understand the assignment file and identify all questions and requirements.
2. Briefly report:
   - how many questions were detected
   - whether there are images, tables, or formulas that may be hard to parse reliably
   - where the generated Markdown file was saved
3. Create a Markdown file in the same folder as the source assignment file.
4. Organize the output into a structured, editable format.
5. For each question, provide:
   - the problem statement or a concise restatement
   - an approach
   - key steps
   - a draft answer
   - a section showing what still needs manual review or completion
6. Preserve mathematical expressions in Markdown math format when possible.
7. Explicitly say when some content cannot be reliably recognized instead of guessing.
8. Avoid modifying the original source file.

### Output Format

The generated Markdown follows this structure:

- `# PS-7`
- `## Question 1`, `## Question 2`, ...
- `### Problem`
- `### Approach`
- `### Key Steps`
- `### Draft Answer`
- `### What I Still Need to Fill In`

### Typical Use Case

This skill is useful when you want to:

- turn a PDF assignment into an editable Markdown draft
- organize multi-question coursework into a clean structure
- prepare a first-pass working document before final revision
- separate reliable extracted content from uncertain or user-dependent content

### Design Principles

This skill is built around the following principles:

- **structure first**: produce something organized and editable
- **no blind guessing**: uncertain content should be marked explicitly
- **student workflow friendly**: help the user work through the assignment question by question
- **source-preserving**: do not modify the original PDF or source document
- **verification-aware**: code results, calculations, and analysis should be grounded when possible

### Files

- `SKILL.md` — main skill instructions
- `agents/openai.yaml` — agent metadata
- `references/output-template.md` — Markdown output scaffold

### Example Invocation

```text
$assignment-draft-skill Please process this assignment file:
C:\path\to\assignment.pdf
```

If your local skill name is different, replace `$assignment-draft-skill` with your actual skill name.

### Important Note

This skill is intended to help with **drafting, structuring, and study support**.

Users should still review, verify, revise, and finalize the content themselves before submission.

---

## 中文版

### 项目简介

Assignment Draft Skill 用来把作业文件转换成一个**可编辑的 Markdown 草稿**。

它不是简单把原文件文本粗暴抽出来，而是会按题目结构整理成清晰的工作文档，方便你继续解题、修改、核对、补全和润色。

这个 skill 的定位是**学习辅助与草稿生成工具**，不是无脑答案生成器。

### 功能说明

给定一个作业文件路径后，这个 skill 会：

1. 读取并理解作业文件，识别其中的题目与要求。
2. 先做一段简短汇报，说明：
   - 一共识别到多少道题
   - 是否存在图片、表格、公式等难以可靠解析的内容
   - 生成的 Markdown 文件保存到了哪里
3. 在原作业文件所在目录下创建一个 Markdown 文件。
4. 将输出整理为结构清晰、可继续编辑的格式。
5. 对每一道题生成以下内容：
   - 题目原文或精炼后的要求
   - 解题思路
   - 关键步骤
   - 草稿答案
   - 仍需人工补充或复核的部分
6. 如果能识别公式，则尽量用 Markdown 数学公式格式整理。
7. 对无法可靠识别的内容明确标注，而不是乱猜。
8. 不修改原始作业文件。

### 输出格式

生成的 Markdown 采用如下结构：

- `# PS-7`
- `## Question 1`, `## Question 2`, ...
- `### Problem`
- `### Approach`
- `### Key Steps`
- `### Draft Answer`
- `### What I Still Need to Fill In`

### 适用场景

这个 skill 适合下面这些场景：

- 把 PDF 作业转成可编辑的 Markdown 草稿
- 把多道题作业整理成结构清晰的文档
- 在最终提交前，先快速搭出一版可修改的工作稿
- 把“可靠识别的内容”和“不确定、需人工处理的内容”分开

### 设计原则

这个 skill 的核心原则是：

- **先结构化，再补内容**
- **不确定就标注，不乱猜**
- **贴合学生做题流程**
- **保护原文件，不直接改源文档**
- **代码、计算、分析尽量基于可验证结果**

### 文件结构

- `SKILL.md` —— 主 skill 说明文件
- `agents/openai.yaml` —— agent 元数据
- `references/output-template.md` —— Markdown 输出模板

### 调用示例

```text
$assignment-draft-skill 请处理这个作业文件：
C:\path\to\assignment.pdf
```

如果你本地 skill 名称不是 `assignment-draft-skill`，把命令里的名字替换成你自己的 skill 名称即可。

### 重要说明

这个 skill 的目标是帮助你完成：

- 读题
- 结构化整理
- 草稿搭建
- 思路展开
- 可编辑初稿生成

最终提交前，用户仍应自行完成检查、核对、修改与定稿。

---

## License

MIT License
