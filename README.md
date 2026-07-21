# create-research-group-ppt

从用户确认的 Codex 项目对话中提取可追溯证据，制作中文科研组会汇报。适用于双周研究进展、论文方法与实验方案、审稿意见与返修计划、阶段成果总结，以及多项目组会汇报。

## 核心能力

- 按 Codex 项目、时间范围和任务清单控制材料边界。
- 在后台证据台账中区分已验证、已实现但未验证、计划中、受阻、已否决和待确认状态，确保结论边界可追溯。
- 普通研究进展汇报的正文默认围绕研究方向、实验组织、当前认识和下一阶段工作展开，不堆叠提交号、审查代码、开发门控或测试流水线细节。
- 组会页标题默认采用简洁自然的主题型表达；完整判断、讲述句和汇报组织说明放入正文或演讲者备注。
- 多项目分别形成独立大章节，不自动解释项目关系或排列优先级。
- 多项目汇报在每个项目开始前加入简洁章节过渡，避免技术内容直接跳转。
- 强制解释流程、目标函数、关键公式、方法或实验方案的修改前后、依据、核心区别与影响。
- 公式优先使用可编辑数学对象；能力受限时使用 LaTeX/MathJax 矢量公式，不以代码式下划线文本替代数学排版。
- 正文使用中文术语，首次出现时可附英文全称和缩写。
- 先确认事实摘要和逐页大纲，再进入视觉制作。
- 每次明确披露制作路径，可使用 `ppt-agent`、内置演示文稿工具、`oil-ppt` 组合流程或自定义流程。
- 默认交付可编辑 PPTX；用户明确选择时可交付离线可编辑 HTML。
- 输出页面证据清单和逐项质量检查报告。

## 安装

将 skill 目录复制到 Codex skills 目录：

```text
skills/create-research-group-ppt
  -> C:/Users/<username>/.codex/skills/create-research-group-ppt
```

也可以从仓库根目录复制：

```powershell
Copy-Item -Recurse -Force `
  '.\skills\create-research-group-ppt' `
  "$env:USERPROFILE\.codex\skills\create-research-group-ppt"
```

重新打开相关 Codex 任务后即可显式调用：

```text
$create-research-group-ppt
```

## 使用示例

```text
使用 $create-research-group-ppt，根据 TFS TSK-Ising 与 UC-FCM+ACSLL
两个 Codex 项目最近 14 天的对话，制作一份 20 分钟双周研究进展汇报。
重点说明目标函数和关键公式修改前后、修改依据与影响，采用视觉讲解型。
```

skill 会先列出候选 Codex 任务供用户确认，不会直接读取未批准的任务全文。之后依次完成证据整理、冲突标注、事实摘要、逐页大纲确认、制作路径披露、演示文稿生成和质量验收。证据状态主要服务于后台核验；幻灯片正文会将其转化为自然的研究语言，例如“单数据集阶段性观察”“正式实验尚未开展”或“现有结果不足以支持优越性结论”。

## 默认工作流

1. 指定一个或多个 Codex 项目。
2. 选择上次汇报后、最近 14 天或自定义时间范围。
3. 确认候选任务、汇报类型、汇报时长和设计倾向。
4. 审核事实与证据摘要、冲突项和逐页大纲。
5. 确认制作路径与交付格式。
6. 生成并审查演示文稿。
7. 交付演示文件、页面证据清单和 QA 报告。

## 默认交付物

```text
<report-name>.pptx
<report-name>-evidence-map.md
<report-name>-qa.md
```

显式选择离线 HTML 时，仅将第一项替换为 `<report-name>.html`。

## 目录结构

```text
skills/create-research-group-ppt/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── conversation-evidence.md
    ├── content-architecture.md
    └── design-and-qa.md
```

## 设计原则

默认采用 16:9、白底、深灰文字和克制深蓝强调色。它是一套可调整的设计语言，不是固定模板：公式修改适合前后对照与变化项标注，工作流程适合机制图或流程图，实验结果适合真实图表，决策讨论适合问题—证据—下一步结构。

页面不得保留第三方模板品牌标记，也不得使用装饰性虚构数据。所有实质结论必须能回溯到已确认的 Codex 对话或其中明确引用的本地项目文件。
