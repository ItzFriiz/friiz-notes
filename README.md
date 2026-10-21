# friiz-notes

[English](#english) · [中文](#中文)

## English

A Pi skill for turning course materials, transcripts, papers, and research notes into Markdown notes that can be understood on their own. It emphasizes the reader's learning sequence, defined notation, complete derivations, accurate sources, and explanations matched to the reader's needs.

The instructions were developed through Friiz's study workflow. The skill files are primarily in Chinese; the requested output language can be changed for a task.

### Personal conventions: adapt before use

This skill is specialized for Friiz's Obsidian vault, **Study**, and personal project layout. Review and adjust these conventions for your own workspace:

| Convention | Current setting | Where to adapt it |
|---|---|---|
| Obsidian formatting | Wiki links, callouts, `$...$` / `$$...$$`, an opening abstract, numbered level-two headings, and no duplicate page title | `references/obsidian.md` |
| Course materials | Course folders containing `slides/`, `source/rec/`, `hw/`, and `notes/`; course-specific rules in `NOTE_RULES.md` | Your course's `NOTE_RULES.md` and `references/course-notes.md` |
| Image attachments | `/Users/friiz/Personal/Study/Attachment/<topic>/`; editable diagram sources in its `src/` subfolder | `references/obsidian.md` |
| Shared research notes | `/Users/friiz/Personal/Study/project/notes` | `references/research-notes.md` |
| Project notes | A project's own `notes/` directory | `references/research-notes.md` |
| Diagram rendering | TeX Live and LuaLaTeX produce white-background PNGs with English labels; images are visually checked before use | `references/obsidian.md` |
| Agent workflow | Luna extracts and compresses materials; the main agent writes and revises; an independent agent reviews | `references/workflow.md` |
| Personal preferences | The name Friiz, Chinese prose, explanation depth, and permission to maintain personal rules | `SKILL.md` and `references/topic-rules.md` |

Replace absolute paths, personal names, model choices, and permission conventions with your own. Check that internal links resolve within your vault. The separate `stop-slop` skill is used for editing prose: install it if following the instructions as written, or replace that reference with your own editing guidance.

The intended Study layout is approximately:

```text
Study/
├── cs/<course>/
│   ├── slides/
│   ├── source/rec/
│   ├── hw/
│   └── notes/
│       └── NOTE_RULES.md
├── project/
│   ├── notes/                 # Shared research knowledge
│   └── <project>/notes/       # Project-specific records
└── Attachment/<topic>/
    ├── figure-01.png
    └── src/figure-01.tex
```

Supply your own course and research materials. Keep local course requirements and project differences in `NOTE_RULES.md` rather than adding them to the shared skill.

### Installation and use

For Pi, clone into a new skill directory:

```sh
git clone https://github.com/ItzFriiz/friiz-notes.git ~/.pi/agent/skills/friiz-notes
```

Adapt the conventions above, then invoke `/skill:friiz-notes` with the relevant materials and output location. See the [Pi skills documentation](https://github.com/earendil-works/pi/blob/main/docs/skills.md) for platform-specific setup.

For a full chapter, the default workflow is material extraction → main-agent writing → independent review → main-agent revision. Small edits stay with the main agent. Review prioritizes cognitive order: concepts appear when needed, their purpose is clear, and derivations follow the question being answered. Explanations expand difficult steps without restating substitutions already clear from the formulas.

### Adaptive explanations and a learner model

The [learner model](references/learner-model.md) guides whether to define a term, explain an operation, fill a reasoning step, compare formulas, or remove repetition. The writer and independent reviewer read it with the current topic's `NOTE_RULES.md`; current feedback and knowledge already established in the note take priority over older records. The model is updated only when explicitly requested after review.

### Repository structure

```text
friiz-notes/
├── SKILL.md                       # Entry point and shared writing principles
├── agents/openai.yaml             # Codex display metadata
├── references/
│   ├── workflow.md                # Delegation, handoff, and review
│   ├── obsidian.md                # Note layout, math, diagrams, and attachments
│   ├── course-notes.md            # Course materials and assessment evidence
│   ├── research-notes.md          # Research scope, filing, and citations
│   ├── topic-rules.md             # Local NOTE_RULES.md maintenance
│   └── learner-model.md           # Reading preferences and explanation decisions
├── README.md
└── LICENSE
```

### Contributing

Issues and pull requests are welcome. Describe the reading or workflow problem, include a short shareable example when useful, and explain the proposed change. Keep general rules in the skill and personal project differences in local rules. Preserve cognitive order, source accuracy, and user edits; check related references when moving a rule.

### License

[MIT](LICENSE). Copyright © 2026 Friiz.

## 中文

这是一个 Pi skill，用于把课程材料、录音转录、论文和科研记录整理成可独立读懂的 Markdown 笔记。重点是符合读者的认知顺序、解释必要符号、保留完整推导和可靠来源，并根据读者的理解调整解释深度。

这些规范来自 Friiz 的实际学习流程。skill 文件主要使用中文，任务中可以指定其他输出语言。

### 个人约定：使用前请调整

这个 skill 适配 Friiz 的 Obsidian 仓库 **Study** 和个人项目结构。使用者需要根据自己的工作区调整：

| 约定 | 当前设置 | 修改位置 |
|---|---|---|
| Obsidian 格式 | 双向链接、callout、`$...$`／`$$...$$`，开头 abstract，二级标题编号，正文不重复页面标题 | `references/obsidian.md` |
| 课程材料 | 课程目录包含 `slides/`、`source/rec/`、`hw/`、`notes/`；专用要求放 `NOTE_RULES.md` | 课程的 `NOTE_RULES.md` 和 `references/course-notes.md` |
| 图片附件 | `/Users/friiz/Personal/Study/Attachment/<主题>/`，可编辑绘图源码放其 `src/` 子目录 | `references/obsidian.md` |
| 通用科研笔记 | `/Users/friiz/Personal/Study/project/notes` | `references/research-notes.md` |
| 项目笔记 | 各项目自身的 `notes/` 目录 | `references/research-notes.md` |
| 绘图环境 | TeX Live／LuaLaTeX 输出白底 PNG，图中文字默认英文，插入前目视检查 | `references/obsidian.md` |
| Agent 分工 | Luna 提取压缩材料，主 agent 写作修改，独立 agent 审查 | `references/workflow.md` |
| 个人偏好 | Friiz 称呼、中文行文、解释深度和维护个人规则的授权 | `SKILL.md` 和 `references/topic-rules.md` |

请替换绝对路径、个人称呼、模型选择和授权约定，并确认库内链接适用于你的 Obsidian 仓库。行文编辑依赖单独的 `stop-slop` skill；沿用原流程时需安装它，也可以替换为自己的编辑规范。

Study 的参考目录结构见上方英文部分。课程和科研材料由使用者提供；课程考核、项目差异等放在当地 `NOTE_RULES.md`，不累积进通用 skill。

### 安装与使用

在 Pi 的新 skill 目录中克隆：

```sh
git clone https://github.com/ItzFriiz/friiz-notes.git ~/.pi/agent/skills/friiz-notes
```

调整上述约定后，使用 `/skill:friiz-notes`，并提供相关材料和输出位置。平台设置参考 [Pi skills 文档](https://github.com/earendil-works/pi/blob/main/docs/skills.md)。

整章笔记默认按“材料提取 → 主 agent 写作 → 独立审查 → 主 agent 修改”推进，局部修改由主 agent 直接处理。审查首先看认知顺序：概念在需要时出现、用途及时交代，推导围绕当前问题展开。费解的地方展开解释，公式已经说明的代入不再复述。

### 用认知文档调整解释深度

[认知文档](references/learner-model.md) 用于决定是否定义术语、说明操作、补推理、并列公式或删除重复解释。写作者和独立审查者结合当前主题的 `NOTE_RULES.md` 读取它，当前反馈和正文已建立的知识优先于旧记录。审查后仅在明确要求时更新认知记录。

### 仓库结构

文件树见上方英文部分。`SKILL.md` 是入口和通用写作原则；`references/` 分别存放工作流、Obsidian、课程、科研和专用规范维护规则；`agents/openai.yaml` 保存 Codex 展示信息。

### 参与贡献与维护

欢迎提交 issue 或 pull request。请说明遇到的阅读或工作流问题，必要时提供可公开的短例子，并解释改动。通用规则留在 skill，个人项目差异放当地规范；修改时保留认知顺序、来源准确性和用户删改，移动规则时同步检查相关引用。

### 许可证

[MIT](LICENSE)。Copyright © 2026 Friiz。
