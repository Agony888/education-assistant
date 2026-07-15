# Education Research Assistant v2.6.1 提示词手册

> 本手册提供可直接复制的单项任务、引导式完整流程和直接式完整流程提示词。

## 一、先选择任务类型

### 1. 单项任务

```text
请使用 education-research-assistant Skill，【模式】模式，【深度】深度，完成【具体任务】。
材料范围：【全文/摘要/文献卡/已有论文内容】。
输出范围：【只要哪些部分】。
证据要求：区分作者明示、文本归纳和材料不足；关键判断标注页码、章节、表格或可识别位置；不要补造作者、年份、理论、数据和结论。
```

### 2. 完整任务：引导式

```text
请使用 education-research-assistant Skill，workflow 模式，执行【流程名称】，选择 guided 引导式。
最终目标：【最终交付物】。
我目前已有的信息：【已有方向、材料或条件】。
请每次只问我一个最关键的问题，记录并校验我的回答。达到最低输入条件后，先提示我确认；我回复“执行”后，再运行完整工作流的全部阶段并生成最终成果。
```

### 3. 完整任务：直接式

```text
请使用 education-research-assistant Skill，workflow 模式，执行【流程名称】，选择 direct 直接式。
最终目标：【最终交付物】。
已有材料：【题目、文献、对象、场域、数据条件】。
请直接执行完整工作流的全部阶段，不再提问。先列出已确认输入、暂定输入、缺失信息和必要假设；无法由材料支持的内容标注为待确认，不要编造。
```

### 4. 未选择执行方式

```text
请使用 education-research-assistant Skill，帮我完成【完整任务】。
```

此时 Skill 应先让用户选择：

```text
A. 引导式：逐步梳理后执行完整工作流。
B. 直接式：使用现有材料立即执行完整工作流。
```

## 二、模式和参数

| 任务 | 模式/流程 | 推荐参数 |
|---|---|---|
| 单篇论文解析 | `paper` | `standard/deep` |
| 论文价值筛选 | `quality` | `quick/standard` |
| 多篇文献整合 | `review` | `matrix/standard` |
| 研究不足与选题 | `gap` | `standard` |
| 综述段落或小节 | `citation` | `paragraph/section/revise` |
| 方法分析 | `method` | `standard` |
| 方法和工具设计 | `method` | `design` |
| 理论分析 | `theory` | `standard` |
| 理论框架设计 | `theory` | `framework` |
| 开题报告单项 | `proposal` | `standard/revise/checklist` |
| 毕业论文单项 | `thesis` | `standard/revise/checklist` |
| 文献卡 | `obsidian` | `obsidian` |
| 论文解析到入库 | `paper-to-note` | `guided/direct` |
| 多篇文献综述全流程 | `literature-review` | `guided/direct` |
| 开题报告全流程 | `proposal-design` | `guided/direct` |
| 毕业论文设计全流程 | `thesis-design` | `guided/direct` |

`deep` 沿用标准模板加深证据和逻辑；`polish` 已统一为 `revise`。

## 三、引导式控制指令

引导过程中可以输入：

| 指令 | 作用 |
|---|---|
| `查看进度` | 查看已确认、待确认、冲突和完成度 |
| `修改：字段=内容` | 修改之前记录的信息 |
| `跳过` | 暂时跳过当前问题 |
| `不确定` | 将当前信息标记为暂定 |
| `直接生成` | 切换到直接式，使用现有输入执行同一完整工作流 |
| `重新开始` | 清空当前引导状态 |
| `结束引导` | 只总结当前信息，不执行工作流 |

## 四、引导式完整流程提示词

### 1. 引导式开题设计

```text
请使用 education-research-assistant Skill，workflow 模式，执行 proposal-design 流程，选择 guided。

我目前只有一个大致方向：【……】。
请每次只问我一个关键问题，优先确认研究对象、研究边界、真实问题、可获取数据、研究类型、理论或分析维度、方法和学校开题要求。
已经回答过的信息不要重复询问；发现矛盾时一次只核对一个矛盾点。
信息基本齐全后，请提示我回复“执行”；收到“执行”后，再完成题目诊断、研究空间、理论框架、方法设计、研究对齐表、开题报告和质量检查。
```

### 2. 引导式论文设计

```text
请使用 education-research-assistant Skill，workflow 模式，执行 thesis-design 流程，选择 guided。

我的研究方向是：【……】。
请一步一步帮助我明确研究中心、核心概念、对象和范围、研究问题、可获得数据、研究类型、理论或分析框架、方法和目录。每次只问一个问题。
达到完整论文设计的最低条件后，再执行 thesis-design 的全部阶段，生成题目建议、概念边界、研究问题、方法、对齐表、目录、章节任务和风险检查。
```

### 3. 引导式文献综述

```text
请使用 education-research-assistant Skill，workflow 模式，执行 literature-review 流程，选择 guided。

我需要围绕【主题】形成文献综述，但目前还不确定综述边界和结构。
请每次只确认一个问题，逐步明确综述服务的论文题目、主题范围、文献材料、作者年份信息完整度、国内外呈现方式和最终输出形式。
信息确认后，再执行文献清点、去重、事实卡、筛选、矩阵、聚类、研究脉络、研究空间、综述小节和证据覆盖检查。
```

### 4. 引导式论文入库

```text
请使用 education-research-assistant Skill，workflow 模式，执行 paper-to-note 流程，选择 guided。
请先逐步确认材料是否完整、是否需要质量筛选、Obsidian 字段和笔记规范。每次只问一个问题。确认后再执行论文解析、可选筛选、文献卡生成和字段完整性检查。
```

## 五、直接式完整流程提示词

### 1. 直接式开题设计

```text
请使用 education-research-assistant Skill，workflow 模式，执行 proposal-design 流程，选择 direct。

题目或方向：【……】
研究对象和场域：【……】
可获取的数据：【……】
可实施方法：【……】
已有文献或理论：【……】
学校要求：【……】

请直接执行题目与条件检查、研究空间、研究类型、理论或分析框架、方法与工具、研究对齐表、开题报告和质量检查。不要再提问；缺失信息、暂定判断和必要假设单独列出。
```

### 2. 直接式论文设计

```text
请使用 education-research-assistant Skill，workflow 模式，执行 thesis-design 流程，选择 direct。

题目：【……】
研究对象：【……】
研究场域：【……】
可接触样本或材料：【……】
可实施方法：【……】

请直接完成题目诊断、概念边界、研究问题、研究类型、理论或分析框架、方法和工具、研究对齐表、论文目录、章节任务与风险检查。不能确认的内容标注“待确认”。
```

### 3. 直接式文献综述

```text
请使用 education-research-assistant Skill，workflow 模式，执行 literature-review 流程，选择 direct。
根据我提供的全部文献或文献卡，直接完成清点去重、逐篇事实卡、相关性筛选、矩阵、主题聚类、研究脉络、共识分歧、研究空间、综述小节和证据覆盖检查。不要新增不存在的作者、年份和观点。
```

### 4. 直接式论文入库

```text
请使用 education-research-assistant Skill，workflow 模式，执行 paper-to-note 流程，选择 direct。
直接完成材料检查、论文事实解析、质量筛选、Obsidian 文献卡和字段完整性检查。若只有摘要或信息不完整，明确限制，不推测全文细节。
```

## 六、单篇论文提示词

### 1. 标准解析

```text
请使用 education-research-assistant Skill，paper 模式，standard 深度，解析这篇中文教育论文。重点提取研究问题、核心概念、理论或分析框架、研究对象、方法、数据、主要发现、贡献、局限和可借鉴价值。
建立研究问题—方法—数据对应表和证据账本。区分作者明示、文本归纳和材料不足。只完成论文解析。
```

### 2. 深度精读

```text
请使用 education-research-assistant Skill，paper 模式，deep 深度，深度精读这篇论文。除标准解析外，重点检查研究逻辑链、理论是否真正进入研究设计、方法是否能回答问题、结论是否超出数据，以及哪些内容可借鉴但不宜照搬。
```

### 3. 摘要分析

```text
请使用 education-research-assistant Skill，paper 模式，standard 深度，仅根据摘要分析。明确标注“分析基于摘要”；理论、工具、样本细节和局限如未说明，标注“摘要未说明”。
```

## 七、质量评价提示词

### 1. 快速筛选

```text
请使用 education-research-assistant Skill，quality 模式，quick 深度，判断论文是否值得精读，以及适合作为核心文献、背景文献、方法参考还是不建议使用。给出明确等级、依据、可借鉴内容和风险，不要完整解析。
```

### 2. 严格评价

```text
请使用 education-research-assistant Skill，quality 模式，standard 深度，从研究问题、理论使用、方法适配、样本与数据、分析深度、结论边界、创新性和与我选题的相关性进行严格评价。每项评分说明依据。
```

## 八、多篇文献提示词

### 1. 事实账本和矩阵

```text
请使用 education-research-assistant Skill，review 模式，matrix 深度，清点和去重这些文献，再生成逐篇事实账本和比较矩阵。字段包括作者年份、研究问题、对象、理论或维度、方法与数据、主要发现、局限和对我研究的价值。无法确认的信息留空。
```

### 2. 分类综述

```text
请使用 education-research-assistant Skill，review 模式，standard 深度，基于已核实文献卡完成分类综述。按研究问题、对象、场景、理论或方法聚类，不按作者逐篇罗列。输出主题聚类、研究脉络、共识、分歧、理论与方法比较、研究不足和综述骨架。
```

### 3. 综述段落

```text
请使用 education-research-assistant Skill，citation 模式，paragraph 深度，把文献观点整合成一个可直接使用的综述段落。结构为“主题判断—综合代表研究—比较与归纳—贡献或不足—过渡”。只使用已提供的作者、年份和观点。
```

### 4. 修改综述

```text
请使用 education-research-assistant Skill，citation 模式，revise 深度，修改下面的文献综述。保留有效观点和原有语气，重点修复主题分类、段落逻辑、观点重复、证据不足和研究述评不清。不要新增文献。
```

## 九、研究不足与选题提示词

### 1. 提炼研究空间

```text
请使用 education-research-assistant Skill，gap 模式，standard 深度，根据文献卡区分已有成果、研究不足、进一步研究空间和严格意义上的研究空白。每项判断标注支持材料、反例或不确定性和可信度。
```

### 2. 生成本科选题

```text
请使用 education-research-assistant Skill，gap 模式，standard 深度，结合文献研究空间和我的实际条件生成3个本科论文选题。说明研究对象、核心问题、研究类型、数据来源、方法、有限创新和风险，推荐最稳妥的一项。
```

### 3. 评价题目

```text
请使用 education-research-assistant Skill，thesis 模式，只执行题目诊断。评价题目《……》的研究对象、核心问题、概念边界、研究中心、范围、数据可得性和是否预设结论。给出稳妥版、学术版和实践版题目。
```

## 十、方法和工具提示词

### 1. 方法设计

```text
请使用 education-research-assistant Skill，method 模式，design 深度，为题目《……》设计本科可实施的研究方案。先判断研究类型，再生成研究问题—证据—数据—方法—分析—章节对齐表。只保留必要方法。
```

### 2. 问卷维度

```text
请使用 education-research-assistant Skill，method 模式，design 深度，为题目《……》设计问卷维度。先说明核心概念和维度来源，再输出一级维度、二级维度、操作性定义、题项方向、依据和对应研究问题。不能先定维度再倒找依据。
```

### 3. 访谈提纲

```text
请使用 education-research-assistant Skill，method 模式，design 深度，为题目《……》设计半结构式访谈提纲。先列访谈主题与对应研究问题，再给出自然、单一、可回答的核心问题和追问。
```

### 4. 文本分析框架

```text
请使用 education-research-assistant Skill，method 模式，design 深度，为【教案/作业/反思文本/政策/教材】设计文本分析框架。输出样本规则、维度定义、来源、正反例、编码步骤、一致性处理和对应研究问题。
```

## 十一、理论框架提示词

### 1. 分析论文理论

```text
请使用 education-research-assistant Skill，theory 模式，standard 深度，分析论文的理论使用。区分背景性提及、概念解释、分析维度、工具设计、变量关系和结果解释，判断理论是否贯穿研究。
```

### 2. 设计自己的框架

```text
请使用 education-research-assistant Skill，theory 模式，framework 深度，为题目《……》设计理论或分析框架。先判断是否确实需要核心理论；如不需要，采用有来源的文献归纳框架。输出理论角色、概念关系、分析维度、来源、对应问题、数据和使用章节。
```

## 十二、Obsidian 提示词

```text
请使用 education-research-assistant Skill，obsidian 模式，把这篇论文整理成可直接保存的 Markdown 文献卡。只输出 YAML 和文献卡正文，包括研究问题、理论、方法、发现、可引用观点、综述位置、rating 和双链建议。
```

## 十三、使用提醒

- 引导式只增加前置梳理，最终仍执行完整工作流；
- 直接式只减少前置提问，不省略工作流阶段；
- 用户在引导中输入“直接生成”时，切换到同一工作流的直接式；
- 单项任务不应强制启动完整工作流；
- 缺失信息不等于可以编造；
- 结论强度不得超过样本、方法和证据。
