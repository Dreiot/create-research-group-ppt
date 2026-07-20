# Content architecture and change explanation

## Report-type emphasis

### 双周研究进展

Emphasize completed work, direct evidence, changes since the last report, blockers, and the next two-week plan.

### 论文方法与实验方案

Emphasize research question, method mechanism, objective function, optimization or implementation flow, experiment design, expected evidence, and unresolved assumptions.

### 审稿意见与返修计划

Map each reviewer concern to the underlying issue, planned or completed response, evidence, manuscript location, risk, and next action. Never state that a concern is resolved without evidence.

### 阶段成果总结与下一步安排

Emphasize milestone goals, accumulated verified outcomes, remaining gaps, decision points, and the next-stage plan.

### 自定义类型

Derive a structure from the user's stated purpose while preserving evidence states and change explanations.

## Mandatory change analysis

Check every report for material changes to:

- research or engineering workflow;
- objective function or its core representation;
- key formula, constraint, or optimization step;
- method architecture or mechanism;
- experiment protocol, dataset processing, metric, or validation gate.

If a material change exists, show:

1. 修改前：the previous workflow, representation, or formula;
2. 修改后：the current version;
3. 修改依据：the observed problem, theoretical reason, experimental evidence, review feedback, or implementation constraint;
4. 核心区别：what was added, removed, replaced, relaxed, constrained, or reordered;
5. 影响：what the change enables, fixes, risks, or still leaves unverified.

If no material change exists, explicitly state `本期无流程或核心表示变更` in the evidence summary. Do not force a comparison slide when it adds no value.

## Formula presentation

- Reconstruct core equations clearly; do not use blurry screenshots.
- Preserve notation from the source. Never invent missing terms or silently normalize inconsistent symbols.
- Compare before and after side by side or through a progressive reveal.
- Highlight only the changed terms using restrained color and annotations.
- Explain every changed term and symbol in Chinese.
- Split long derivations into `总体目标 → 关键子项 → 优化影响`.
- Prefer editable equations. Use high-resolution vector output only when editable rendering is unreliable.
- Pair a formula with a mechanism diagram or plain-Chinese interpretation when the audience needs intuition.

## Chinese terminology

Use Chinese in the body. On first occurrence, write `中文名称（English Full Name，ABBR）`; afterwards use Chinese or the established abbreviation. Keep official method names, algorithm names, dataset names, journal names, and product names unchanged when translation would reduce precision.

Give every formula symbol a Chinese meaning. Avoid untranslated process labels such as `pipeline`, `baseline`, or `ablation` when established Chinese terms exist; use `流程`, `基线方法`, and `消融实验`.

## Speaker notes

Add concise notes to every substantive slide when the approved presentation format supports speaker notes:

- one-sentence takeaway;
- recommended speaking order;
- change rationale or evidence that must be emphasized;
- likely advisor question or caveat;
- suggested time allocation when useful.

Do not hide essential evidence only in notes.

If the approved format cannot store speaker notes, disclose the limitation before production, obtain the user's approval, and record the agreed substitute in the QA report. Do not silently omit notes.
