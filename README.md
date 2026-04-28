# Academic-DeAI

Academic-DeAI（学术去AI味）is a Claude Code / OpenCode skill for responsible academic revision of AI-assisted drafts. It improves clarity, precision, scholarly tone, citation discipline, and authorial voice while preserving scientific meaning, technical terms, LaTeX equations, statistical results, references, and manuscript structure.

It is designed for academic papers, grant proposals, review reports, response letters, technical reports, Chinese academic writing, and energy top-journal manuscripts.

## Positioning

Academic-DeAI is not a generic text humanizer. It is an academic writing quality-control skill.

Its purpose is to help researchers convert rough AI-assisted drafts into more rigorous, verifiable, discipline-appropriate scholarly prose. It focuses on:

- removing empty template-like expressions;
- strengthening academic logic;
- preserving facts, citations, equations, variables, and statistical results;
- improving journal-facing style;
- checking claims against evidence;
- supporting transparent and responsible AI-assisted writing.

## Why this project exists

General writing-polish prompts often focus on surface language: inflated wording, generic transitions, repetitive rhythm, rule-of-three structures, and chatbot artifacts. That is useful for ordinary writing, but it is not enough for academic work.

Academic writing has stricter constraints:

- empirical results must not be changed;
- citations must not be fabricated;
- LaTeX equations and BibTeX entries must be protected;
- variables, coefficients, p-values, t-values, tables, and figures must remain intact;
- hedging should be calibrated rather than mechanically deleted;
- passive voice is sometimes appropriate, especially in methods and results sections;
- Chinese academic and policy-facing writing has its own formulaic expressions that need careful handling;
- energy and engineering manuscripts require thermodynamic consistency, system-boundary clarity, fair baselines, validation, and metric completeness.

Academic-DeAI therefore focuses on integrity-preserving academic revision.

## Core capabilities

### 1. Academic naturalization

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

### 2. Protected academic elements

The skill is instructed not to alter:

- LaTeX equations;
- BibTeX entries;
- citation keys such as `\citep{}`, `\citet{}`, `\cite{}`;
- numerical results;
- regression coefficients;
- p-values, t-values, standard errors, confidence intervals;
- variables such as `TFP`, `CCD`, `WND`, `EF`, `ROA`, `ENL`;
- energy and thermal symbols such as `COP`, `EER`, `PUE`, `ERE`, `WUE`, `Q`, `T_in`, `T_out`, `ΔT`, `Δp`, `Nu`, `Re`, `Pr`, `R_th`;
- model names such as `DID`, `DDD`, `PSM`, `IV`, `FE`, `GMM`, `CFD`, `FEM`, `LCA`, `TEA`;
- table and figure labels;
- direct quotations;
- official policy quotations;
- code blocks.

If a protected element appears suspicious, the skill should flag it rather than silently change it.

### 3. Academic revision modes

| Mode | Use case |
|---|---|
| Light academic polish | Minor clarity and flow improvements |
| Journal-style rewrite | Stronger theory, argument, and paragraph logic |
| Reviewer-safe rewrite | Rebuttals, response letters, revision notes |
| Chinese academic style | Chinese journal and policy-facing research writing |
| Bilingual academic translation polish | Chinese-English academic translation and polishing |
| LaTeX-safe revision | Manuscripts containing LaTeX, citations, equations, labels, and references |
| Energy top-journal revision | Energy, Applied Energy, ECM, RSER, ATE, IJHMT and related outlets |
| Data center liquid cooling and waste heat recovery | AI data centers, cold plates, CDU, immersion cooling, heat pumps, absorption systems, waste heat recovery |

### 4. Citation-aware revision

The skill should not invent citations. If a claim requires support but no source is present, it marks the sentence with:

```text
[citation needed]
```

If a claim is too strong for the available evidence, it softens the language.

Example:

**Original**

> Many studies prove that AI improves innovation.

**Revised**

> Prior research has linked AI adoption to changes in innovation processes, although the strength and direction of this relationship depends on data, task context, and organizational capabilities [citation needed].

### 5. Energy top-journal audit

For energy manuscripts, Academic-DeAI checks not only language quality but also reviewer-sensitive technical issues:

- system boundary: chip, component, rack, room, facility, district, or lifecycle level;
- thermodynamic consistency: first-law versus second-law claims, temperature lift, source/sink/output temperature;
- performance metrics: COP, EER, PUE, ERE, WUE, exergy efficiency, pressure drop, pumping power, heat recovery ratio;
- baseline comparison: air cooling, conventional liquid cooling, straight-channel cold plates, heat pumps, existing absorption systems;
- validation: experiment, literature comparison, mesh independence, uncertainty analysis;
- sensitivity and robustness: flow rate, inlet temperature, heat flux, ambient condition, partial-load operation;
- engineering applicability: manufacturability, fouling, corrosion, leakage, redundancy, maintenance, integration;
- economic and environmental relevance: CAPEX, OPEX, payback period, carbon reduction, marginal emission factor.

### 6. Voice calibration

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
git clone https://github.com/syq-cmdi/humanizer.git ~/.claude/skills/academic-deai
```

Or copy the skill file manually if you already have this repository cloned:

```bash
mkdir -p ~/.claude/skills/academic-deai
cp SKILL.md ~/.claude/skills/academic-deai/
```

### OpenCode

```bash
mkdir -p ~/.config/opencode/skills
git clone https://github.com/syq-cmdi/humanizer.git ~/.config/opencode/skills/academic-deai
```

Or copy the skill file manually:

```bash
mkdir -p ~/.config/opencode/skills/academic-deai
cp SKILL.md ~/.config/opencode/skills/academic-deai/
```

OpenCode also scans `~/.claude/skills/` for compatibility, so one clone into `~/.claude/skills/academic-deai/` can work for both tools.

## Usage

### Basic academic polish

```text
/academic-deai

Please polish the following paragraph in a journal-appropriate academic style:
[paste text]
```

### Reviewer-safe rewrite

```text
/academic-deai

Mode: Reviewer-safe rewrite.
Please revise the following response to reviewers. Keep the tone respectful, precise, and concise:
[paste response]
```

### LaTeX-safe revision

```text
/academic-deai

Mode: LaTeX-safe revision.
Please polish the prose but do not alter citations, equations, labels, references, or numerical results:
[paste LaTeX text]
```

### Chinese academic style

```text
/academic-deai

Mode: Chinese academic style.
请压缩空泛表述，增强理论逻辑和机制链条，保持正式学术语气：
[粘贴中文文本]
```

### Energy top-journal revision

```text
/academic-deai

Mode: Energy top-journal revision.
Target journal: Applied Energy.
Please revise the following section. Check system boundary, thermodynamic consistency, performance metrics, baseline comparison, validation, and engineering applicability:
[paste text]
```

### Data center liquid cooling and waste heat recovery

```text
/academic-deai

Mode: Data center liquid cooling and waste heat recovery.
Please revise this section for an energy top journal. Pay special attention to heat flux, coolant temperature, pressure drop, pumping power, PUE/ERE, exergy value, temperature lift, and useful heat demand:
[paste text]
```

### Voice calibration

```text
/academic-deai

Here is a sample of my published writing for voice calibration:
[paste 2-3 paragraphs]

Now revise the following text in a similar academic voice:
[paste target text]
```

## Before / after examples

### General academic writing

**Original**

> This study underscores the pivotal role of large language models in advancing natural language processing, marking a significant milestone in the evolving landscape of artificial intelligence. Previous studies have shown that LLMs greatly enhance research productivity and foster innovation across multiple domains.

**Revised**

> This study examines how large language models affect natural language processing tasks and research workflows. Existing work links LLMs to gains in text generation, coding assistance, and information retrieval, but the size and reliability of these gains vary across task settings [citation needed].

### Energy manuscript writing

**Original**

> The proposed liquid cooling system significantly enhances heat dissipation and provides a promising solution for future AI data centers.

**Revised**

> The proposed liquid-cooling system reduces the maximum chip temperature by X K under a heat flux of Y W/cm² and an inlet coolant temperature of Z °C. Its system-level benefit depends on additional pumping power, CDU efficiency, and integration with facility-side heat rejection.

### Waste heat recovery

**Original**

> Data center waste heat has great potential for sustainable energy utilization.

**Revised**

> Data center waste heat is abundant but usually available at low to medium temperature levels. Its practical recovery value depends on outlet coolant temperature, exergy content, distance to heat demand, and the match between hourly heat supply and local heating loads.

## Recommended workflow

For long manuscripts, revise in sections rather than all at once:

1. Abstract
2. Introduction
3. Theory or literature review
4. Methods / model / experiment
5. Results
6. Discussion
7. Conclusion
8. Response letter or cover letter

For LaTeX manuscripts, use LaTeX-safe mode and review the output with `git diff` before replacing the original file.

For energy manuscripts, revise results and discussion with the energy top-journal checklist before revising the abstract and conclusion.

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
- numeric-diff checker for statistical and engineering values;
- citation-risk scanner;
- Chinese academic template-expression library;
- author voice profile module;
- energy top-journal profile library;
- Overleaf / VS Code integration;
- reviewer-perspective audit checklist;
- optional local-model support through Ollama.

## Suggested repository name

Recommended GitHub repository names:

- `academic-deai`
- `academic-deai-skill`
- `scholar-deai`
- `scholarly-polish`
- `academic-writing-qc`

The current repository URL remains `https://github.com/syq-cmdi/humanizer` unless renamed manually in GitHub settings.

## Version history

- **3.1.0** - Renamed project identity to Academic-DeAI; added Energy Top Journal mode and Data Center Liquid Cooling / Waste Heat Recovery mode.
- **3.0.0** - Refocused as Humanizer-Academic; added integrity-preserving revision, protected academic elements, academic modes, LaTeX-safe revision, citation-aware rules, Chinese academic mode, and responsible-use framing.
- **2.5.1** - Original upstream version: added a passive-voice / subjectless-fragment rule, raising the total to 29 patterns.

## License

MIT
