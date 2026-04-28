# Humanizer-Academic

Humanizer-Academic is a Claude Code / OpenCode skill for revising academic drafts. It improves clarity, precision, scholarly tone, citation discipline, and authorial voice while preserving scientific meaning, technical terms, LaTeX equations, statistical results, references, and manuscript structure.

It is designed for academic papers, grant proposals, review reports, response letters, technical reports, and policy-facing research writing.

## Why this fork exists

General writing-polish prompts often focus on removing surface-level template language: inflated wording, generic transitions, repetitive rhythm, rule-of-three structures, and chatbot artifacts. That is useful for ordinary writing, but it is not enough for academic work.

Academic writing has stricter constraints:

- empirical results must not be changed;
- citations must not be fabricated;
- LaTeX equations and BibTeX entries must be protected;
- variables, coefficients, p-values, t-values, tables, and figures must remain intact;
- hedging should be calibrated rather than mechanically deleted;
- passive voice is sometimes appropriate, especially in methods and results sections;
- Chinese academic and policy-facing writing has its own formulaic expressions that need careful handling.

Humanizer-Academic therefore focuses on integrity-preserving academic revision.

## Core capabilities

### Academic naturalization

The skill reduces common template-like academic patterns, including:

- inflated significance claims;
- vague attribution;
- empty contrast such as “not only...but also...”;
- generic rule-of-three phrasing;
- overused abstract vocabulary such as “pivotal,” “landscape,” “underscore,” and “testament”;
- over-hedging or under-hedging;
- chatbot artifacts;
- formulaic paragraph openers;
- excessive smoothness and promotional tone.

### Protected academic elements

The skill is instructed not to alter:

- LaTeX equations;
- BibTeX entries;
- citation keys such as `\citep{}`, `\citet{}`, `\cite{}`;
- numerical results;
- regression coefficients;
- p-values, t-values, standard errors, confidence intervals;
- variables such as `TFP`, `CCD`, `WND`, `EF`, `ROA`, `ENL`;
- model names such as `DID`, `DDD`, `PSM`, `IV`, `FE`, `GMM`;
- table and figure labels;
- direct quotations;
- official policy quotations;
- code blocks.

If a protected element appears suspicious, the skill should flag it rather than silently change it.

### Academic revision modes

| Mode | Use case |
|---|---|
| Light academic polish | Minor clarity and flow improvements |
| Journal-style rewrite | Stronger theory, argument, and paragraph logic |
| Reviewer-safe rewrite | Rebuttals, response letters, revision notes |
| Chinese academic style | Chinese journal and policy-facing research writing |
| Bilingual academic translation polish | Chinese-English academic translation and polishing |
| LaTeX-safe revision | Manuscripts containing LaTeX, citations, equations, labels, and references |

### Citation-aware revision

The skill should not invent citations. If a claim requires support but no source is present, it marks the sentence with:

```text
[citation needed]
```

If a claim is too strong for the available evidence, it softens the language.

Example:

**Original**

> Many studies prove that AI improves innovation.

**Revised**

> Prior research has linked AI adoption to changes in innovation processes, although the strength and direction of this relationship depend on data, task context, and organizational capabilities [citation needed].

### Voice calibration

If you provide samples of your own writing, the skill can approximate your academic voice by analyzing:

- sentence length;
- transition habits;
- theoretical vocabulary;
- citation density;
- degree of hedging;
- paragraph structure;
- Chinese or English rhetorical style.

It should preserve your scholarly rhythm without copying distinctive sentences or inventing private claims.

## Installation

### Claude Code

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/syq-cmdi/humanizer.git ~/.claude/skills/humanizer-academic
```

Or copy the skill file manually if you already have this repository cloned:

```bash
mkdir -p ~/.claude/skills/humanizer-academic
cp SKILL.md ~/.claude/skills/humanizer-academic/
```

### OpenCode

```bash
mkdir -p ~/.config/opencode/skills
git clone https://github.com/syq-cmdi/humanizer.git ~/.config/opencode/skills/humanizer-academic
```

Or copy the skill file manually:

```bash
mkdir -p ~/.config/opencode/skills/humanizer-academic
cp SKILL.md ~/.config/opencode/skills/humanizer-academic/
```

OpenCode also scans `~/.claude/skills/` for compatibility, so one clone into `~/.claude/skills/humanizer-academic/` can work for both tools.

## Usage

### Basic academic polish

```text
/humanizer-academic

Please polish the following paragraph in a journal-appropriate academic style:
[paste text]
```

### Reviewer-safe rewrite

```text
/humanizer-academic

Mode: Reviewer-safe rewrite.
Please revise the following response to reviewers. Keep the tone respectful, precise, and concise:
[paste response]
```

### LaTeX-safe revision

```text
/humanizer-academic

Mode: LaTeX-safe revision.
Please polish the prose but do not alter citations, equations, labels, references, or numerical results:
[paste LaTeX text]
```

### Chinese academic style

```text
/humanizer-academic

Mode: Chinese academic style.
请压缩空泛表述，增强理论逻辑和机制链条，保持正式学术语气：
[粘贴中文文本]
```

### Voice calibration

```text
/humanizer-academic

Here is a sample of my published writing for voice calibration:
[paste 2-3 paragraphs]

Now revise the following text in a similar academic voice:
[paste target text]
```

## Before / after example

**Original**

> This study underscores the pivotal role of large language models in advancing natural language processing, marking a significant milestone in the evolving landscape of artificial intelligence. Previous studies have shown that LLMs greatly enhance research productivity and foster innovation across multiple domains.

**Revised**

> This study examines how large language models affect natural language processing tasks and research workflows. Existing work links LLMs to gains in text generation, coding assistance, and information retrieval, but the size and reliability of these gains vary across task settings [citation needed].

**What changed**

- Inflated claims were replaced with specific academic claims.
- Vague attribution was marked for citation support.
- Promotional language was removed.
- The tone became more cautious and journal-appropriate.

## Recommended workflow

For long manuscripts, revise in sections rather than all at once:

1. Abstract
2. Introduction
3. Theory and hypotheses
4. Methods
5. Results
6. Discussion
7. Response letter or cover letter

For LaTeX manuscripts, use LaTeX-safe mode and review the output with `git diff` before replacing the original file.

## Responsible use

Responsible use means:

- the author remains accountable for all claims, data, citations, and interpretations;
- AI-assisted revisions should not fabricate evidence;
- journal or institutional AI-use disclosure rules should be followed;
- the tool should improve clarity, accuracy, and scholarly quality.

A concise disclosure statement, when needed, may look like:

> The authors used AI-assisted language editing tools to improve clarity and grammar. All conceptual development, data analysis, interpretation, and final manuscript decisions were made and verified by the authors.

## Project roadmap

Potential future extensions:

- CLI batch processing for `.tex`, `.md`, and `.docx` files;
- LaTeX guard for citations, equations, labels, and references;
- citation-risk scanner;
- Chinese academic template-expression library;
- author voice profile module;
- Overleaf / VS Code integration;
- reviewer-perspective audit checklist;
- optional local-model support through Ollama.

## Reference

This project is adapted from general work on template-like AI-assisted writing patterns, including Wikipedia's `Signs of AI writing`, but is redesigned for academic and technical writing. Surface-level polishing is not enough for scholarly work; academic revision must protect evidence, structure, citations, and meaning.

## Version history

- **3.0.0** - Refocused as Humanizer-Academic; added integrity-preserving revision, protected academic elements, academic modes, LaTeX-safe revision, citation-aware rules, Chinese academic mode, and responsible-use framing.
- **2.5.1** - Original upstream version: added a passive-voice / subjectless-fragment rule, raising the total to 29 patterns.

## License

MIT
