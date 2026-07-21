---
name: create-research-group-ppt
description: Create evidence-traceable, editable Chinese research group meeting presentations from user-selected Codex project conversations and explicitly referenced local project artifacts. Use for biweekly research updates, method and experiment plans, reviewer-response presentations, milestone summaries, multi-project group meetings, or revisions to an existing group-meeting deck when Codex must select tasks by project and time range, distinguish verified progress from plans, explain workflow or formula changes before versus after, obtain outline approval, disclose and use an appropriate presentation-production path, and deliver a default PPTX or explicitly requested offline HTML with an evidence map and QA report.
---

# Create Research Group Meeting PPT

Create a defensible presentation from selected Codex task history. Keep content approval separate from visual production. Do not treat plans, hypotheses, or unverified agent claims as completed research.

## Non-negotiable boundaries

- Use only user-approved Codex tasks and local artifacts explicitly referenced by those tasks.
- Do not browse for supplementary claims or introduce external evidence without explicit permission.
- Never silently broaden the project, task, or date scope.
- Never overwrite an existing deck unless the user explicitly requests it.
- Require user approval of the evidence summary and slide-by-slide outline before producing the deck.
- Explicitly disclose the final presentation-production path before using it. It may be a `ppt-agent`, built-in presentation tooling, `oil-ppt`, or a clearly described custom workflow.
- Deliver an editable `.pptx` by default, or an offline editable `.html` when the user explicitly requests HTML, plus a page-to-evidence map and a QA report. Keep previews and source projects as internal artifacts unless requested.

## Workflow

### 1. Establish the run contract

Ask one compact set of startup questions covering only decisions that cannot be discovered:

1. Select one or more Codex projects.
2. Select the time range: since the previous report cutoff, the latest 14 days, or custom dates.
3. Select the report type:
   - 双周研究进展
   - 论文方法与实验方案
   - 审稿意见与返修计划
   - 阶段成果总结与下一步安排
   - 自定义类型
4. State the expected speaking duration.
5. Confirm a report name and output directory when they cannot be safely inferred from context. Use editable `.pptx` by default; accept offline editable `.html` when explicitly requested.

List candidate Codex tasks within the selected projects and dates. Let the user confirm which tasks to include before reading their full content. For multiple projects, preserve each project as a separate top-level chapter; do not explain relationships or rank priorities unless requested.

Then recommend a design tendency based on the chosen report type and ask the user to confirm or adjust it. Treat a design tendency explicitly supplied in the user's request as already confirmed; do not ask again.

- 严谨学术型
- 视觉讲解型
- 决策讨论型
- 自定义

Read [references/conversation-evidence.md](references/conversation-evidence.md) before collecting or reconciling evidence.

### 2. Build the evidence ledger

Read only the confirmed tasks. Follow explicit references from those tasks to local formulas, figures, experiment outputs, source files, or prior decks when required for fidelity.

For every candidate claim, record:

- project and task identity;
- message date or stable locator;
- status: `已验证`, `已实现但未验证`, `计划中`, `受阻`, `已否决`, or `待确认`;
- supporting artifact or validation result;
- whether it changes a workflow, objective function, formula, method, or experiment plan.

Prefer newer verified evidence over older state, but never silently discard conflicts. Surface material conflicts and ask the user to resolve any conflict that changes the central narrative.

### 3. Prepare content for approval

Read [references/content-architecture.md](references/content-architecture.md). Produce:

1. a concise fact and evidence summary;
2. missing, conflicting, or unverified items;
3. a slide-by-slide outline;
4. a proposed design tendency and estimated slide count.

Estimate length from speaking time rather than filling a fixed page quota. Use roughly one slide per minute only as a starting point; allocate more time and fewer slides for formulas, mechanism diagrams, and before-after explanations.

For research-progress and milestone presentations, keep the evidence ledger as an internal verification layer. Translate it into an audience-facing research narrative centered on:

`研究方向 → 方法或流程如何调整 → 实验如何组织 → 当前观察与认识 → 下一阶段工作`

Do not place developer-facing state in the main deck by default, including commit hashes, branch names, review verdict codes, implementation candidates, development Gates, CI details, or exhaustive test counts. Include such material only when the user asks for it, when the report type is explicitly about review or engineering governance, or when omitting it would materially misrepresent the research.

Preserve scientifically meaningful uncertainty even when development metadata is omitted. Use concise research-facing wording such as `单数据集阶段性观察`, `尚未开展正式实验`, `仍需更多种子验证`, or `当前结果不足以支持优越性结论` when supported by the evidence.

Every project chapter should default to:

`研究方向 → 流程/公式改动前后及依据 → 实验组织 → 当前结论与适用边界 → 下一步计划`

For multiple projects, use:

`封面 → 目录 → 项目 A 章节过渡 → 项目 A → 项目 B 章节过渡 → 项目 B → … → 本期总结与待讨论问题`

Use concise, natural topic titles for ordinary group-meeting slides. Prefer titles such as `研究动机`, `实验设置`, `阶段性结果`, or a precise method name. Move presenter-like summary sentences, rhetorical framing, and generated-sounding phrases into the slide body or speaker notes. Avoid titles such as `用三条主线回答……`, `三条主线采用同一套研究叙事`, or other complete sentences that describe how the deck was constructed.

Do not start PPT production until the user approves both the fact/evidence summary and the slide-by-slide outline.

### 4. Select and disclose the production path

Recommend a production path after considering formula editability, visual complexity, available tools, and the user's requested output. State the selected path and why it fits before starting production. Treat a path explicitly selected by the user as confirmed. Otherwise let the user adjust the recommendation.

Allowed paths include:

- `ppt-agent` for specialized planning, visual design, production, rendering, and verification;
- built-in presentation tooling for direct editable PowerPoint creation or modification;
- `oil-ppt` alone for an explicitly requested offline HTML deliverable, or combined with an explicitly disclosed PPTX conversion or reconstruction tool and post-conversion QA for a PPTX deliverable;
- a custom workflow whose tools, editable source, conversion path, and QA method are named explicitly.

Do not switch production paths silently. If the selected path is unavailable or fails, report the problem and ask the user to approve the proposed alternative.

### 5. Produce the presentation

After approval, give the selected production path the following source packet without adding unsupported conclusions:

- approved slide outline;
- approved fact/evidence summary;
- evidence ledger and conflict resolutions;
- selected design tendency and user customizations;
- speaking duration and target slide count;
- local artifact paths needed for figures or formulas;
- the rules in [references/design-and-qa.md](references/design-and-qa.md);
- the required output paths.

Require a fully editable 16:9 presentation in the approved format, Chinese academic terminology, full-slide rendering, full-size visual inspection, and revision of visual defects before delivery. Require concise speaker notes on every substantive slide when the selected format supports notes. If it does not, disclose that limitation and obtain approval before production; do not silently omit the notes.

For multiple projects, require a brief chapter divider or an equally explicit visual transition before each new project. Keep the divider simple: project name plus one neutral research-focus subtitle is usually enough.

Render mathematical expressions as mathematics, not programmer-style text. Prefer editable equation objects when the production path supports them reliably. Otherwise use high-resolution LaTeX/MathJax vector output and retain the source expression in the production files or notes. Never present core equations with raw underscores, improvised Unicode spacing, or flattened superscripts when correct subscripts, fractions, norms, traces, transposes, and Greek symbols are available.

Keep internal provenance, review, and validation details in the evidence map or QA report unless they are explicitly part of the approved slide outline. Do not let implementation bookkeeping displace the research question, experiment design, observations, or next-stage plan.

The design must vary with content. Keep the approved white, dark-gray, restrained-deep-blue baseline, but do not repeat one table/card layout across the deck. Prefer diagrams, plots, experimental figures, and formula explanations when they communicate the evidence better. Do not retain third-party template branding such as `Made with GAMMA`.

### 6. Audit and deliver

Independently verify the production outputs against the approved outline and evidence ledger. Require all checks in [references/design-and-qa.md](references/design-and-qa.md).

Deliver exactly these default artifacts:

- `<report-name>.pptx`
- `<report-name>-evidence-map.md`
- `<report-name>-qa.md`

When the user explicitly selects offline HTML, replace only the first artifact with `<report-name>.html` and adapt format-specific QA accordingly.

Report any check that did not run and the substitute evidence used. Never describe a skipped check as passed.
