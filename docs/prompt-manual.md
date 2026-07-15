# Education Research Assistant v2.6 提示词手册

> 本手册提供可直接复制的调用方式。Codex 已能根据任务自动路由时，不必机械写全模式名称；当需要严格控制范围、深度或连续流程时，再使用完整提示词。

## 一、通用格式

### 单模式

```text
请使用 education-research-assistant Skill，【模式】模式，【深度】深度，完成【具体任务】。
材料范围：【全文/摘要/文献卡/已有论文内容】。
输出范围：【只要哪些部分】。
证据要求：区分作者明示、文本归纳和材料不足；关键判断标注页码、章节、表格或可识别位置；不要补造作者、年份、理论、数据和结论。
```

### 流程模式

```text
请使用 education-research-assistant Skill，workflow 模式，执行【流程名称】。
最终目标：【最终交付物】。
材料范围：【已有材料】。
研究条件：【对象、场域、时间、可获取数据】。
要求：逐阶段执行，每阶段保留结构化中间产物、质量检查和下一阶段交接数据；当前阶段不足以支持下一阶段时停止并列出待补材料。
```

## 二、模式和深度

| 任务 | 模式 | 推荐深度 |
|---|---|---|
| 单篇论文解析 | `paper` | `standard` / `deep` |
| 论文价值筛选 | `quality` | `quick` / `standard` |
| 多篇文献整合 | `review` | `matrix` / `standard` |
| 研究不足与选题 | `gap` | `standard` |
| 综述段落或小节 | `citation` | `paragraph` / `section` / `revise` |
| 方法分析 | `method` | `standard` |
| 方法和工具设计 | `method` | `design` |
| 理论分析 | `theory` | `standard` |
| 理论框架设计 | `theory` | `framework` |
| 开题报告 | `proposal` | `standard` / `revise` / `checklist` |
| 毕业论文设计 | `thesis` | `standard` / `checklist` |
| 文献卡 | `obsidian` | `obsidian` |
| 连续科研任务 | `workflow` | `standard` |

`deep` 沿用标准模板加深证据和逻辑分析；`polish` 已统一为 `revise`。

## 三、单篇论文

### 1. 标准解析

```text
请使用 education-research-assistant Skill，paper 模式，standard 深度，解析这篇中文教育论文。重点提取研究问题、核心概念、理论或分析框架、研究对象、方法、数据、主要发现、贡献、局限和对我研究的可借鉴价值。
请建立研究问题—方法—数据对应表和关键判断证据账本。区分作者明示、文本归纳和材料不足。只完成论文解析，不附加完整质量评分或 Obsidian 文献卡。
```

### 2. 深度精读

```text
请使用 education-research-assistant Skill，paper 模式，deep 深度，深度精读这篇论文。除标准解析外，重点检查研究逻辑链、理论是否真正进入研究设计、方法是否能回答问题、结论是否超出数据，以及哪些内容可借鉴但不宜照搬。关键判断尽量标注页码、章节或表格位置。
```

### 3. 基于摘要分析

```text
请使用 education-research-assistant Skill，paper 模式，standard 深度，仅根据这篇论文摘要进行分析。明确标注“分析基于摘要”，只提取摘要能够支持的研究主题、对象、方法和结论；理论、工具、样本细节和局限如未说明，标注“摘要未说明”，不要推测。
```

## 四、质量筛选

### 4. 快速判断是否值得精读

```text
请使用 education-research-assistant Skill，quality 模式，quick 深度，判断这篇论文是否值得精读，以及适合作为核心文献、综述背景文献、方法参考文献还是不建议使用。给出明确等级、3—5条依据、可借鉴内容和主要风险。不要完整解析论文。
```

### 5. 严格质量评价

```text
请使用 education-research-assistant Skill，quality 模式，standard 深度，从研究问题、理论使用、方法适配、样本与数据、分析深度、结论边界、创新性和与我选题的相关性进行严格评价。每项评分说明依据，不以期刊级别代替论文内容判断。
```

## 五、多篇文献综述

### 6. 先生成事实账本和矩阵

```text
请使用 education-research-assistant Skill，review 模式，matrix 深度，整理这些文献。先清点、去重并说明信息完整度，再生成逐篇事实账本和比较矩阵。字段包括作者年份、研究问题、对象、理论或维度、方法与数据、主要发现、局限和对我研究的价值。无法确认的信息留空，不自行补齐。
```

### 7. 分类综述

```text
请使用 education-research-assistant Skill，review 模式，standard 深度，基于这些已核实的文献卡完成分类综述。按研究问题、对象、场景、理论或方法聚类，不按作者逐篇罗列。输出主题聚类、研究脉络、共识、分歧、理论与方法比较、研究不足和综述写作骨架，并检查每个综合判断由哪些文献支持。
```

### 8. 综述段落

```text
请使用 education-research-assistant Skill，citation 模式，paragraph 深度，把以下文献观点整合成一个可直接用于本科论文的综述段落。结构为“主题判断—综合代表研究—比较与归纳—贡献或不足—过渡”。只使用已提供的作者、年份和观点，不新增文献。
```

### 9. 综述小节

```text
请使用 education-research-assistant Skill，citation 模式，section 深度，根据已核实的文献卡撰写“【小节题目】”。先给出小节逻辑骨架，再形成正文。每段围绕一个中心判断，避免张三说、李四说式罗列；结尾说明该板块与本研究的关系。
```

### 10. 修改综述

```text
请使用 education-research-assistant Skill，citation 模式，revise 深度，修改下面的文献综述。保留有效观点和原有语气，重点修复主题分类、段落逻辑、观点重复、证据不足和研究述评不清的问题。不要新增不存在的文献、作者和年份。先指出结构性问题，再给出完整修改稿。
```

## 六、研究不足与选题

### 11. 提炼研究空间

```text
请使用 education-research-assistant Skill，gap 模式，standard 深度，根据这些文献卡区分已有成果、研究不足、进一步研究空间和严格意义上的研究空白。每项判断标注支持材料、反例或不确定性和可信度。证据不足时明确写“只能确认研究空间，不能确认严格空白”。
```

### 12. 生成本科选题

```text
请使用 education-research-assistant Skill，gap 模式，standard 深度，结合文献中的研究空间和我的实际条件生成3个本科论文选题。我的条件是：【实习学校、可接触教师或学生、可用时间、可获取材料】。每个选题说明研究对象、核心问题、研究类型、数据来源、方法、有限创新和主要风险。优先推荐最稳妥的一项。
```

### 13. 评价现有题目

```text
请使用 education-research-assistant Skill，thesis 模式，只执行题目诊断。评价题目《……》的研究对象、核心问题、概念边界、研究中心、范围、数据可得性和是否预设结论。给出稳妥版、学术版和实践版题目，并说明最推荐哪一个。不要生成完整目录。
```

## 七、研究方法与工具

### 14. 方法设计

```text
请使用 education-research-assistant Skill，method 模式，design 深度，为题目《……》设计本科可实施的研究方案。先判断研究类型，再生成研究问题—所需证据—数据来源—方法/工具—分析方式—对应章节对齐表。只保留必要方法，不为显得复杂而堆叠问卷、访谈和观察。
```

### 15. 问卷维度

```text
请使用 education-research-assistant Skill，method 模式，design 深度，为题目《……》设计问卷维度。先说明核心概念及维度来源，再输出一级维度、二级维度、操作性定义、题项方向、依据和对应研究问题。区分概念界定、理论维度与问卷操作化，不能先定维度再倒找依据。
```

### 16. 访谈提纲

```text
请使用 education-research-assistant Skill，method 模式，design 深度，为题目《……》设计半结构式访谈提纲。先列访谈主题与对应研究问题，再给出自然、单一、可回答的核心问题和追问。避免诱导性、抽象理论化和一次提问多个问题。
```

### 17. 文本分析框架

```text
请使用 education-research-assistant Skill，method 模式，design 深度，为【教案/作业/反思文本/政策/教材】设计文本分析框架。输出样本规则、一级和二级维度、维度定义、来源、正例与反例、编码步骤、一致性处理和对应研究问题。
```

## 八、理论与分析框架

### 18. 分析论文理论

```text
请使用 education-research-assistant Skill，theory 模式，standard 深度，分析这篇论文的理论使用。区分背景性提及、概念解释、分析维度、工具设计、变量关系和结果解释，判断理论是否贯穿研究。原文未使用的理论不要补充。
```

### 19. 为自己的论文设计框架

```text
请使用 education-research-assistant Skill，theory 模式，framework 深度，为题目《……》设计理论或分析框架。先判断是否确实需要核心理论；如不需要，采用有来源的文献归纳框架。输出理论角色、概念关系、分析维度、维度来源、对应研究问题、数据和使用章节，避免理论堆砌。
```

## 九、开题报告

### 20. 生成开题核心内容

```text
请使用 education-research-assistant Skill，proposal 模式，standard 深度，根据题目《……》和现有文献材料生成开题报告核心内容。先诊断题目和研究条件，再判断研究类型，形成概念—问题—理论—方法—数据—章节对齐表。计划内容使用将来时，缺少文献或数据时列为待补材料，不编造研究发现。
```

### 21. 修改开题报告

```text
请使用 education-research-assistant Skill，proposal 模式，revise 深度，修改下面的开题报告。先按一级问题、二级问题和语言问题排序诊断，再修复题目、概念、研究问题、理论、方法、技术路线和创新点之间的不一致。保留有效内容，不从头生成无关章节。
```

### 22. 开题检查

```text
请使用 education-research-assistant Skill，proposal 模式，checklist 深度，检查这份开题报告是否可以进入正式研究。重点看每个研究问题是否有数据、每个维度是否有来源、方法是否可实施、研究类型与目录是否一致、创新是否夸大。给出“通过/有条件通过/不通过”和最优先修改事项。
```

## 十、毕业论文

### 23. 题目—问题—目录设计

```text
请使用 education-research-assistant Skill，thesis 模式，standard 深度，围绕题目《……》完成研究边界、核心概念、研究问题、研究类型和论文目录设计。目录必须根据调查研究、案例研究、文本分析、实践探索或行动研究分流，不默认套用“现状—问题—原因—策略”。
```

### 24. 章节修改

```text
请使用 education-research-assistant Skill，thesis 模式，revise 深度，修改论文的【章节名称】。先说明该章节应回答什么问题、与前后章节的关系和当前结构问题，再给出修改后的完整内容。保留作者原意，不新增未经核实的数据和引用。
```

### 25. 全文结构检查

```text
请使用 education-research-assistant Skill，thesis 模式，checklist 深度，检查这篇论文的题目—概念—研究问题—理论—方法—数据—结果—建议是否一致。按严重程度列出问题、证据和修改动作，优先解决结构与证据问题，不先做表面语言润色。
```

## 十一、Obsidian

### 26. 文献卡

```text
请使用 education-research-assistant Skill，obsidian 模式，把这篇论文整理成可直接保存的 Markdown 文献卡。使用统一 YAML 字段，正文包括核心摘要、研究问题、理论、方法、发现、贡献、局限、可引用观点、综述位置、双链建议和后续任务。只输出文献卡。
```

## 十二、四条流程提示词

### 27. 单篇论文入库流程

```text
请使用 education-research-assistant Skill，workflow 模式，执行 paper-to-note 流程。先检查材料完整度，生成论文事实卡；再根据我的要求判断是否需要质量筛选；最后生成 Obsidian 文献卡并检查字段完整性。每阶段保留确认事实、材料不足和交接数据。
```

### 28. 多篇综述流程

```text
请使用 education-research-assistant Skill，workflow 模式，执行 literature-review 流程。对这些文献先清点、去重和建立逐篇事实卡，再进行相关性筛选、文献矩阵、主题聚类、研究脉络、共识与分歧、研究空间和综述小节写作。最终检查每个综述判断的证据覆盖。材料不足时降低结论强度。
```

### 29. 开题设计流程

```text
请使用 education-research-assistant Skill，workflow 模式，执行 proposal-design 流程。题目为《……》，我的实际条件是【……】。依次完成题目诊断、文献研究空间、研究类型、概念和理论框架、研究问题、方法与工具、研究对齐表、开题报告和质量检查。某阶段不成立时先修复或停止，不强行继续。
```

### 30. 毕业论文设计流程

```text
请使用 education-research-assistant Skill，workflow 模式，执行 thesis-design 流程。围绕题目《……》，连续完成研究边界、概念界定、研究问题、研究类型、理论/分析框架、方法、目录、章节任务和全文检查。每阶段输出可传递产物，最终给出完整研究对齐表。
```

## 十三、专项增强

### AI+教育

```text
在上述任务基础上，优先读取 ai-education-bank.md，重点检查 AI 应用场景、教师二次判断、人机分工、内容准确性、伦理和真实教学可行性。
```

### 小学数学

```text
优先读取 primary-math-bank.md 和 math-curriculum-standard-bank.md，重点检查数学本质、核心素养、学段特点、活动的数学思维含量、评价证据和作业质量。
```

### 教师发展

```text
优先读取 teacher-development-bank.md，重点检查教师数字/智能素养、专业发展、教学反思、培训支持、学校条件和乡村场域限制。
```

## 十四、常用限制句

按需追加，不必每次全部使用：

```text
只完成我要求的部分，不自动附加其他模式。
```

```text
原文没有明确说明的内容标注“材料未说明”，不要推测。
```

```text
每个关键判断标注证据位置，并区分作者明示与文本归纳。
```

```text
不要新增作者、年份、政策、理论和数据。
```

```text
先修复研究逻辑和证据问题，再处理语言。
```

```text
建议必须适合本科研究时间、样本和场域条件。
```
