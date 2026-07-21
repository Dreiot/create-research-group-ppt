# Content architecture and change explanation

## Report-type emphasis

### 双周研究进展

Emphasize the research direction, why the method or workflow changed, how experiments were organized, what can currently be concluded, what remains scientifically uncertain, and the next two-week plan. Keep routine development bookkeeping out of the main narrative unless it changes the scientific interpretation.

### 论文方法与实验方案

Emphasize research question, method mechanism, objective function, optimization or implementation flow, experiment design, expected evidence, and unresolved assumptions.

### 审稿意见与返修计划

Map each reviewer concern to the underlying issue, planned or completed response, evidence, manuscript location, risk, and next action. Never state that a concern is resolved without evidence.

### 阶段成果总结与下一步安排

Emphasize milestone goals, accumulated verified outcomes, remaining gaps, decision points, and the next-stage plan.

### 自定义类型

Derive a structure from the user's stated purpose while preserving evidence states and change explanations.

## Audience-facing research narrative

Maintain a detailed evidence ledger during preparation, but do not reproduce it mechanically on slides. For ordinary research updates, translate provenance and implementation state into a concise narrative:

`研究方向 → 修改内容与依据 → 实验组织 → 当前观察与认识 → 适用边界 → 下一阶段工作`

By default, omit developer-facing details from the main deck:

- commit hashes, branch names, and exact diff ranges;
- review-verdict codes and implementation-candidate labels;
- development Gates, internal stage identifiers, and workflow bookkeeping;
- CI logs and exhaustive test-count inventories.

Retain these details in the evidence map or QA report. Show them on slides only when the user requests them, the presentation is specifically about review or engineering governance, or the detail is essential to explain why a result can or cannot be trusted.

Do not confuse simplification with overclaiming. Replace internal status labels with research-facing boundary statements supported by evidence, for example:

- `当前为单数据集、单种子的阶段性观察`;
- `正式外部实验尚未开展`;
- `现有结果用于验证流程一致性，不用于证明性能优越性`;
- `该结论仍需更多数据集、随机种子或对照实验验证`.

For multi-project progress reports, keep each project as a separate top-level chapter and give each chapter the same four audience questions:

1. 当前研究方向是什么？
2. 实验或方法为什么这样调整，具体如何组织？
3. 目前观察到了什么，能够和不能够得出什么结论？
4. 下一阶段准备做什么？

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
