# Education Research Assistant v2.6.1

面向 Codex 的中文教育科研 Skill，适用于论文阅读、文献综述、研究方法与理论框架、开题报告、毕业论文写作、Obsidian 文献库，以及小学数学、AI+教育和教师发展等方向。

v2.6.1 的核心变化是：用户需要完整任务时，可以自行选择“引导式”或“直接式”。两种方式最后都执行同一条完整工作流。

## 一、它是什么

本项目包含：

```text
任务入口与模式路由
+ 单项任务模板
+ 完整工作流
+ 引导式信息梳理
+ 流程状态和阶段交接
+ 证据协议
+ 研究类型分流
+ 教育科研知识库
```

它仍然是 Codex Skill，不是独立部署的 Coze、Dify 或 n8n 工作流引擎。但在一次对话中，它可以逐步收集信息，也可以直接连续执行完整科研流程。

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
            │   ├── guided-intake-template.md
            │   ├── workflow-state-template.md
            │   ├── paper-standard-template.md
            │   ├── review-standard-template.md
            │   ├── method-design-template.md
            │   ├── proposal-standard-template.md
            │   ├── thesis-master-template.md
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

## 三、两类任务入口

### 1. 单项任务

用户只需要一个明确结果时，直接调用对应模式：

```text
paper      单篇论文解析
review     多篇文献整合
method     研究方法分析与设计
theory     理论基础与分析框架
quality    论文质量评价
gap        研究不足、研究空间与选题
citation   文献综述段落、小节与修改
proposal   开题报告生成、修改与检查
thesis     论文题目、问题、目录与章节
obsidian   Obsidian 文献卡和知识库
```

例如：

```text
请使用 education-research-assistant Skill，method 模式，design 深度，为题目《……》设计问卷维度。只完成问卷设计。
```

单项任务完成后停止，不自动调用其他模式。

### 2. 完整任务

完整任务先确定目标工作流：

```text
paper-to-note        单篇论文解析、筛选与入库
literature-review    多篇文献整理到综述初稿
proposal-design      从研究方向到完整开题报告
thesis-design        从题目到研究方案、目录与写作计划
```

然后由用户选择执行方式：

```text
A. 引导式：每次只确认一个关键问题，全部梳理清楚后执行完整工作流。
B. 直接式：根据现有材料立即执行完整工作流，缺失信息明确标注。
```

## 四、引导式和直接式的关系

两者不是两套工作流。

```text
引导式
→ 逐轮收集信息
→ 校验研究边界、数据条件和方法关系
→ 形成工作流输入包
→ 执行完整工作流全部阶段
→ 输出最终成果

直接式
→ 读取用户已有材料
→ 标记缺失、暂定信息和必要假设
→ 执行完整工作流全部阶段
→ 输出最终成果
```

两种方式的以下内容必须相同：

- 工作流阶段；
- 质量检查标准；
- 中间产物；
- 研究对齐要求；
- 最终交付物。

引导式只增加前置梳理，不是一个简化版本；直接式只减少前置提问，不得省略工作流阶段。

## 五、引导式如何使用

例如，想从选题梳理到开题报告：

```text
请使用 education-research-assistant Skill，workflow 模式，执行 proposal-design 流程，选择 guided 引导式。请每次只问我一个关键问题，等信息梳理完成后，再执行完整开题工作流。
```

Skill 会依次确认最关键的信息，例如：

```text
最终交付物
→ 研究对象与范围
→ 核心现实问题
→ 可获得的数据
→ 研究类型
→ 理论或分析框架
→ 方法和工具
→ 学校格式与限制
```

每轮只问一个主问题。用户可以随时输入：

- `查看进度`；
- `修改：字段=内容`；
- `跳过`；
- `不确定`；
- `直接生成`；
- `重新开始`；
- `结束引导`。

`直接生成` 会结束引导，并使用当前已经收集的信息执行同一条完整工作流。

## 六、直接式如何使用

例如，已有题目和研究条件，希望立即生成完整开题方案：

```text
请使用 education-research-assistant Skill，workflow 模式，执行 proposal-design 流程，选择 direct 直接式。

题目：《……》
研究对象：……
研究条件：……
现有文献：……

请直接执行全部阶段，不再提问。缺失内容标注为待确认，不要编造。
```

直接式会先整理：

- 已确认输入；
- 暂定输入；
- 缺失信息；
- 必要假设；
- 对流程的影响。

然后执行完整工作流。

## 七、四条完整工作流

### 1. `paper-to-note`

```text
材料检查
→ paper standard
→ quality quick（按需）
→ obsidian
→ 字段完整性检查
```

### 2. `literature-review`

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

### 3. `proposal-design`

```text
题目与研究条件检查
→ 文献基础与研究空间
→ 研究类型判断
→ 理论或分析框架
→ 方法与工具设计
→ 研究对齐表
→ 开题报告
→ 开题质量检查
```

### 4. `thesis-design`

```text
题目优化
→ 核心概念与边界
→ 研究问题
→ 研究类型与目录
→ 理论或分析框架
→ 方法设计
→ 问题—数据—方法—章节对齐
→ 章节写作计划
→ 论文检查
```

## 八、关键质量规则

### 1. 证据协议

关键判断区分：

- 作者明示；
- 文本归纳；
- 方法建议；
- 材料不足。

优先标记页码、章节、表格或可识别位置。不得把“当前材料没有找到”写成“整个研究领域没有”。

### 2. 研究对齐

研究设计必须形成：

```text
题目
→ 核心概念
→ 研究问题
→ 理论或分析维度
→ 数据来源
→ 方法与工具
→ 分析方式
→ 对应章节
→ 结论与建议
```

没有数据支持的研究问题必须修改、删除或标记为待解决。

### 3. 研究类型分流

支持：

- 调查研究；
- 案例研究；
- 文本分析；
- 实践探索；
- 行动研究；
- 理论或政策分析；
- 混合研究。

论文目录不会默认套用“现状—问题—原因—策略”。

## 九、专项知识库

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

## 十、推荐调用

### 引导式开题设计

```text
请使用 education-research-assistant Skill，workflow 模式，执行 proposal-design 流程，选择 guided。每次只问一个关键问题；题目、对象、数据条件、理论和方法梳理清楚后，再执行完整开题工作流。
```

### 直接式开题设计

```text
请使用 education-research-assistant Skill，workflow 模式，执行 proposal-design 流程，选择 direct。根据我已经提供的材料直接执行全部阶段，不再提问；缺失信息、暂定判断和必要假设单独列出。
```

### 未指定执行方式

```text
请使用 education-research-assistant Skill 帮我从选题做到开题报告。
```

此时 Skill 应先让用户选择：引导式或直接式。

## 十一、文档

- `使用说明.md`：日常使用方法；
- `docs/prompt-manual.md`：完整提示词手册；
- `examples/call-examples.md`：调用示例；
- `CHANGELOG.md`：版本更新记录。
