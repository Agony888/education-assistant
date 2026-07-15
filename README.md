# Education Research Assistant v2.6

面向 Codex 的中文教育科研 Skill，适用于中文教育论文阅读、文献综述、研究方法与理论框架设计、开题报告、毕业论文写作和 Obsidian 文献库整理。

v2.6 不再只提供一组提示词模板，而是在保留单模式调用的基础上，增加可连续执行的流程模式、阶段中间产物、证据协议、研究类型分流和研究对齐检查。

## 一、它是什么

本项目包含：

```text
任务路由与执行规则
+ 输出模板
+ 教育科研知识库
+ 专项学科知识库
+ 流程状态与阶段交接规范
```

它仍然是 Codex Skill，而不是独立的外部工作流引擎；但当用户要求“完整流程”时，Skill 能在当前任务内按阶段连续执行，并用结构化中间产物连接各阶段。

## 二、目录结构

```text
education-assistant/
├── AGENTS.md
├── README.md
├── manifest.json
├── 使用说明.md
├── docs/
│   └── prompt-manual.md
└── .agents/
    └── skills/
        └── education-research-assistant/
            ├── SKILL.md
            ├── templates/
            │   ├── paper-standard-template.md
            │   ├── review-standard-template.md
            │   ├── method-design-template.md
            │   ├── proposal-standard-template.md
            │   ├── thesis-master-template.md
            │   ├── workflow-state-template.md
            │   └── ...
            └── knowledge/
                ├── evidence-protocol.md
                ├── research-type-routing.md
                ├── thesis-writing-system.md
                ├── ai-education-bank.md
                ├── primary-math-bank.md
                ├── teacher-development-bank.md
                ├── math-curriculum-standard-bank.md
                └── ...
```

## 三、两种运行方式

### 单模式

用户只要求一个结果时，只执行一个模式。

```text
paper      单篇论文解析
review     多篇文献综述整合
method     研究方法分析与设计
theory     理论基础与分析框架
quality    论文质量评价
gap        研究不足、研究空间与选题切口
citation   文献综述段落、小节与修改
proposal   开题报告生成、修改与检查
thesis     毕业论文题目、问题、目录与章节
obsidian   Obsidian 文献卡和知识库
```

例如：

```text
请使用 education-research-assistant Skill，paper 模式，standard 深度，解析这篇论文。只做论文解析，不附加质量评分和 Obsidian 文献卡。
```

### 流程模式

用户明确要求完整连续处理时，使用 `workflow`。

```text
workflow paper-to-note
workflow literature-review
workflow proposal-design
workflow thesis-design
```

流程模式会记录：

- 每阶段输入；
- 结构化输出；
- 已确认事实；
- 文本归纳；
- 未解决问题；
- 质量检查；
- 下一阶段交接数据。

前一阶段不能支持后一阶段时，流程停止并说明缺少什么，不强行生成。

## 四、四条核心流程

### 1. 单篇论文入库

```text
材料检查
→ paper standard
→ quality quick（可选）
→ obsidian
→ 字段完整性检查
```

### 2. 多篇文献综述

```text
文献清点与去重
→ 逐篇事实卡
→ 相关性与质量筛选
→ 文献矩阵
→ 主题聚类与研究脉络
→ 研究不足和研究空间
→ 综述小节
→ 证据覆盖检查
```

### 3. 开题报告设计

```text
题目与研究条件检查
→ 文献与研究空间
→ 研究类型判断
→ 理论/分析框架
→ 方法与工具设计
→ 研究对齐表
→ 开题报告
→ 开题检查
```

### 4. 毕业论文设计

```text
题目优化
→ 核心概念与边界
→ 研究问题
→ 研究类型与目录
→ 理论框架
→ 方法设计
→ 问题—数据—方法—章节对齐
→ 写作计划
→ 论文检查
```

## 五、v2.6 重点改进

### 1. 模式边界

`paper` 不再默认附加完整质量评价和 Obsidian 卡；`quality`、`obsidian` 只有用户明确要求时才调用。

### 2. 证据协议

关键判断区分：

- 作者明示；
- 文本归纳；
- 方法建议；
- 材料不足。

优先标记页码、章节、表格或原文位置，避免把推断写成作者观点。

### 3. 研究对齐

研究设计必须形成：

```text
研究问题
→ 所需证据
→ 数据来源
→ 方法/工具
→ 分析方式
→ 对应章节
```

没有数据支持的问题必须修改或删除。

### 4. 研究类型分流

支持调查研究、案例研究、文本分析、实践探索、行动研究、理论/政策分析和混合研究。论文目录不再默认套用“现状—问题—原因—策略”。

### 5. 文献综述证据覆盖

多篇综述先建立文献事实账本，再进行聚类、比较、空白判断和写作；单篇观点不得写成学界共识。

### 6. 本科可行性控制

优先考虑对象是否可接触、样本是否可获得、工具是否能完成、数据是否能分析以及研究时间是否充足。

## 六、专项知识库

| 方向 | 文件 |
|---|---|
| AI+教育、生成式 AI | `knowledge/ai-education-bank.md` |
| 小学数学 | `knowledge/primary-math-bank.md` |
| 小学数学课程标准 | `knowledge/math-curriculum-standard-bank.md` |
| 教师数字素养与专业发展 | `knowledge/teacher-development-bank.md` |
| 教育理论 | `knowledge/education-theory-bank.md` |
| 研究方法 | `knowledge/research-method-bank.md` |
| 论文结构 | `knowledge/thesis-writing-system.md` |
| 证据规范 | `knowledge/evidence-protocol.md` |
| 研究类型 | `knowledge/research-type-routing.md` |

交叉任务会组合读取对应知识库。

## 七、推荐调用

### 单篇论文

```text
请使用 education-research-assistant Skill，paper 模式，standard 深度，解析这篇论文。区分作者明示、文本归纳和材料不足，关键判断标注页码或章节位置。只完成论文解析。
```

### 多篇综述流程

```text
请使用 education-research-assistant Skill，workflow 模式，执行 literature-review 流程。先清点、去重并建立逐篇事实卡，再完成筛选、矩阵、主题聚类、研究脉络、研究空间和综述小节。每个阶段保留交接数据，不能由材料支持的判断不要生成。
```

### 开题报告流程

```text
请使用 education-research-assistant Skill，workflow 模式，执行 proposal-design 流程。围绕我的题目，依次完成题目诊断、研究空间、研究类型、理论框架、方法设计、研究对齐表和开题报告检查。研究条件不足时明确列出待补材料。
```

## 八、文档

- `使用说明.md`：日常使用方法；
- `docs/prompt-manual.md`：完整提示词手册；
- `examples/call-examples.md`：调用示例；
- `CHANGELOG.md`：版本更新记录。
