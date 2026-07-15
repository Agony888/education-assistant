# Codex 教育科研 Skill 提示词使用手册

> 适用于 `education-research-assistant` Skill。  
> 用途：中文教育论文解析、文献综述、研究方法、理论框架、研究空白、开题报告、毕业论文写作、Obsidian 文献库整理。

---

## 一、通用使用格式

```text
请使用 education-research-assistant Skill，【模式】模式，【深度】深度，完成【具体任务】。要求：【限制条件】。
```

建议结尾追加：

```text
只输出我要求的部分，不要调用其他模式，不要完整复述论文。原文未说明的内容请标注“原文未说明”，不要推测。
```

---

## 二、模式选择表

| 任务 | 模式 | 推荐深度 |
|---|---|---|
| 解析一篇论文 | `paper` | `standard` |
| 判断论文值不值得读 | `quality` | `quick` |
| 整合多篇文献 | `review` | `standard` |
| 找研究空白、论文选题 | `gap` | `standard` |
| 写文献综述段落 | `citation` | `paragraph` |
| 分析研究方法 | `method` | `standard` |
| 设计研究方法 | `method` | `design` |
| 分析理论基础 | `theory` | `standard` |
| 设计理论框架 | `theory` | `framework` |
| 写开题报告 | `proposal` | `standard` |
| 修改开题报告 | `proposal` | `revise` |
| 优化论文题目/目录/摘要 | `thesis` | `standard` |
| 生成 Obsidian 文献卡 | `obsidian` | `obsidian` |

---

## 三、论文解析提示词

### 1. 标准解析论文

```text
请使用 education-research-assistant Skill，paper 模式，standard 深度，解析这篇中文教育论文，并生成 Obsidian 简版文献卡。重点分析研究背景、研究问题、理论基础、研究方法、主要结论、创新点、不足，以及对我毕业论文写作的启示。关键判断请标注依据，原文未说明的内容请标注“原文未说明”，不要推测。
```

### 2. 快速读懂论文

```text
请使用 education-research-assistant Skill，paper 模式，quick 深度，快速解析这篇论文。请输出论文主题、研究问题、研究方法、主要结论、创新点、不足，以及是否值得继续精读。
```

### 3. 深度精读核心文献

```text
请使用 education-research-assistant Skill，paper 模式，deep 深度，深度解析这篇中文教育论文。请重点拆解论文的研究逻辑、理论基础、研究设计、分析框架、主要发现、创新点、局限性，并说明这篇论文可以如何服务我的毕业论文选题、文献综述、研究方法和理论框架。
```

---

## 四、论文质量评价提示词

### 4. 快速判断是否值得读

```text
请使用 education-research-assistant Skill，quality 模式，quick 深度，判断这篇论文是否值得精读，是否适合作为核心文献。请给出质量等级、判断理由、可借鉴之处和不宜照搬之处。不要完整解析论文。
```

### 5. 严格评价论文质量

```text
请使用 education-research-assistant Skill，quality 模式，standard 深度，从研究问题、理论支撑、方法适切性、数据/材料充分性、分析深度、创新性、实践价值、与我研究方向的关联等维度评价这篇论文。请评价严格一些，不要泛泛说“有一定价值”，要明确它适合作为核心文献、背景文献、方法参考文献，还是不建议使用。
```

---

## 五、多篇文献综述提示词

### 6. 整合多篇文献卡

```text
请使用 education-research-assistant Skill，review 模式，standard 深度，整合这些文献卡。不要逐篇重复总结，重点输出主题聚类、文献矩阵、研究脉络、研究共识、研究不足、研究空白和可直接使用的文献综述段落。
```

### 7. 生成文献矩阵

```text
请使用 education-research-assistant Skill，review 模式，matrix 深度，根据这些文献卡生成文献矩阵。字段包括作者年份、研究主题、研究对象、理论基础、研究方法、主要结论、研究不足、对我论文的价值。
```

### 8. 写国内外研究现状框架

```text
请使用 education-research-assistant Skill，review 模式，standard 深度，根据这些文献卡生成“国内外研究现状”写作框架。请按主题分类，不要按作者逐篇罗列。每一类都要包括研究重点、代表性观点、已有贡献和不足。没有真实文献支撑的内容不要编造。
```

---

## 六、研究空白与选题提示词

### 9. 提炼研究空白

```text
请使用 education-research-assistant Skill，gap 模式，standard 深度，根据这些文献卡提炼研究空白。请区分研究不足、研究空白和研究切口，并标注每个研究空白的可信度。不要凭空说“国内外研究较少”，必须基于材料判断。
```

### 10. 生成本科论文选题

```text
请使用 education-research-assistant Skill，gap 模式，standard 深度，根据这些文献卡和我的研究条件，生成适合本科小学教育论文的选题切口。请重点关注 AI+教育、小学数学、教师数字素养、教学反思、作业设计、课堂评价等方向。每个选题都要说明研究对象、研究问题、可用方法、创新点、可行性和风险。
```

### 11. 判断选题是否可行

```text
请使用 education-research-assistant Skill，gap 模式，standard 深度，判断这个选题是否适合作为本科毕业论文。请从研究对象、研究问题、资料可得性、方法可操作性、创新点、风险和修改方向几个方面评价，并给出更稳妥的题目版本。
```

---

## 七、文献综述表达提示词

### 12. 写综述段落

```text
请使用 education-research-assistant Skill，citation 模式，paragraph 深度，将以下文献观点整合成一段文献综述。不要逐篇罗列作者观点，要形成“总起—代表研究—归纳评价—不足过渡—引出本研究”的结构。语言要像本科论文文献综述，不要过度 AI 化。
```

### 13. 写综述小节

```text
请使用 education-research-assistant Skill，citation 模式，section 深度，根据这些文献卡生成一个文献综述小节。请包括研究总体现状、主要研究方向、已有研究贡献、研究不足以及与本研究的关系。不要编造作者、年份和文献。
```

### 14. 润色已有综述

```text
请使用 education-research-assistant Skill，citation 模式，polish 深度，润色下面这段文献综述。请保留原意，删除重复和空话，调整逻辑，让表达更像本科论文文献综述。不要新增不存在的作者、年份和文献。
```

---

## 八、研究方法提示词

### 15. 分析论文研究方法

```text
请使用 education-research-assistant Skill，method 模式，standard 深度，分析这篇论文的研究方法。请说明作者使用了哪些方法、这些方法分别解决什么问题、是否能回答研究问题、数据来源是否充分、方法设计有什么优点和不足，以及我可以借鉴什么。
```

### 16. 设计自己的研究方法

```text
请使用 education-research-assistant Skill，method 模式，design 深度，帮我为这个选题设计本科毕业论文研究方法。要求方法可操作，适合小学教育专业和乡镇小学实习场域。请输出研究对象、样本建议、方法组合、问卷维度、访谈提纲、课堂观察维度或文本分析维度，并生成开题报告中可直接使用的研究方法表述。
```

### 17. 设计访谈提纲

```text
请使用 education-research-assistant Skill，method 模式，design 深度，围绕我的选题设计半结构式访谈提纲。请分别设计教师访谈问题，必要时设计学生访谈或管理者访谈问题。问题要具体、自然、可回答，不要过于理论化。
```

### 18. 设计问卷维度

```text
请使用 education-research-assistant Skill，method 模式，design 深度，围绕我的选题设计问卷维度。请输出一级维度、二级维度、题项方向和设计理由。问卷应适合小学教师或小学数学教师填写。
```

---

## 九、理论基础提示词

### 19. 分析论文理论基础

```text
请使用 education-research-assistant Skill，theory 模式，standard 深度，分析这篇论文的理论基础。请区分显性理论、隐含分析逻辑、分析框架和变量模型，并判断这些理论是否真正支撑了研究。原文没有使用的理论不要编造。
```

### 20. 设计理论框架

```text
请使用 education-research-assistant Skill，theory 模式，framework 深度，帮我为这个选题设计理论框架。要求理论不要堆砌，要能支撑研究问题、研究方法和论文分析。请说明推荐理论、适用理由、使用位置、分析维度，并给出一个简单的理论关系图。
```

---

## 十、开题报告提示词

### 21. 生成开题报告核心内容

```text
请使用 education-research-assistant Skill，proposal 模式，standard 深度，根据我的选题《……》生成开题报告核心内容。请包括选题依据、研究意义、国内外研究现状框架、研究目标与研究问题、研究内容、研究方法、创新点、可行性分析和研究进度安排。没有真实文献支撑的地方，请写成“研究现状框架”，不要编造文献。
```

### 22. 修改开题报告

```text
请使用 education-research-assistant Skill，proposal 模式，revise 深度，检查并修改我的开题报告。重点看选题依据是否充分、文献综述是否有逻辑、研究问题是否具体、研究内容和研究问题是否对应、方法是否可行、创新点是否稳健。请先指出问题，再给出修改建议和重点段落改写。
```

### 23. 只检查开题报告问题

```text
请使用 education-research-assistant Skill，proposal 模式，checklist 深度，检查我的开题报告还有哪些问题。请从选题、文献综述、研究问题、研究方法、创新点、可行性和进度安排几个方面逐项判断，只检查问题，不重写全文。
```

---

## 十一、毕业论文写作提示词

### 24. 优化毕业论文题目

```text
请使用 education-research-assistant Skill，thesis 模式，帮我优化这个毕业论文题目。请从研究对象、研究范围、核心概念、方法可行性和题目规范性几个方面判断，并给出稳妥版、学术版、实践版三个题目版本。
```

### 25. 生成论文研究思路

```text
请使用 education-research-assistant Skill，thesis 模式，standard 深度，基于这个选题帮我生成毕业论文研究思路。请包括研究对象、研究问题、研究内容、理论基础建议、研究方法建议、论文目录框架和写作风险。
```

### 26. 生成论文目录

```text
请使用 education-research-assistant Skill，thesis 模式，standard 深度，根据这个选题生成本科毕业论文目录。目录要符合教育类论文写作逻辑，一级标题和二级标题要清楚，研究内容、问题分析和策略建议之间要有对应关系。
```

### 27. 写摘要

```text
请使用 education-research-assistant Skill，thesis 模式，帮我根据这个论文题目和研究内容生成中文摘要。摘要应包括研究背景、研究目的、研究方法、主要发现和结论建议。语言要规范，不要空泛。
```

### 28. 写引言

```text
请使用 education-research-assistant Skill，thesis 模式，帮我写论文引言部分。请按照“研究背景—现实问题—已有研究基础—研究不足—本研究切入”的逻辑展开，语言适合本科教育类论文。
```

### 29. 写结论

```text
请使用 education-research-assistant Skill，thesis 模式，帮我写论文结论部分。请回答研究问题，概括主要发现，提出实践建议，并说明研究不足。不要夸大结论。
```

### 30. 检查论文初稿

```text
请使用 education-research-assistant Skill，thesis 模式，checklist 深度，检查我的论文初稿。请重点看题目是否清楚、研究问题是否贯穿全文、文献综述是否有逻辑、方法是否能回答问题、分析是否有证据、策略是否与问题对应、结论是否回应研究问题。
```

---

## 十二、Obsidian 文献库提示词

### 31. 生成 Obsidian 文献卡

```text
请使用 education-research-assistant Skill，obsidian 模式，把这篇论文整理成 Obsidian 文献卡。请使用统一 Frontmatter 字段，包含 title、author、year、source、paper_type、research_topic、method、theory、review_section、rating、status 等信息。只输出 Markdown 文献卡，不要输出长篇分析。
```

### 32. 生成 MOC 主题索引

```text
请使用 education-research-assistant Skill，obsidian 模式，为“AI辅助小学数学教学”生成一个 Obsidian MOC 主题索引。请包括主题说明、核心文献 Dataview 查询、研究主题分类、可用于文献综述的观点、研究空白和可转化选题。
```

### 33. 生成 Dataview 查询

```text
请使用 education-research-assistant Skill，obsidian 模式，帮我生成 Obsidian Dataview 查询语句，用于管理中文教育论文文献库。请包括查看全部文献、查看某一综述板块文献、查看核心文献、查看待精读文献几类查询。
```

---

## 十三、专项知识库提示词

### 34. AI+教育专项

```text
请使用 education-research-assistant Skill，并优先参考 ai-education-bank.md，分析这篇 AI+教育论文。请重点关注生成式 AI 的应用场景、教师角色、教学环节、研究方法、伦理边界和对我论文选题的启示。
```

### 35. 小学数学专项

```text
请使用 education-research-assistant Skill，并优先参考 primary-math-bank.md，分析这篇小学数学教育论文。请重点关注数学核心素养、教学目标、教学活动、作业设计、课堂评价、数学思维含量和学科特征。
```

### 36. 教师发展专项

```text
请使用 education-research-assistant Skill，并优先参考 teacher-development-bank.md，分析这篇教师发展相关论文。请重点关注教师数字素养、智能素养、专业发展、教学反思、培训支持和乡村教师现实条件。
```

### 37. 小学数学课标专项

```text
请使用 education-research-assistant Skill，并优先参考 math-curriculum-standard-bank.md，分析这篇小学数学论文。重点关注课程标准依据、核心素养、学段特点、内容领域、教学活动、作业设计或课堂评价是否合理。
```

### 38. 交叉方向分析

```text
请使用 education-research-assistant Skill，同时参考 ai-education-bank.md、primary-math-bank.md、math-curriculum-standard-bank.md 和 teacher-development-bank.md，围绕“生成式 AI 辅助小学数学教师教学反思”这一方向，分析已有研究基础、研究空白、可行选题、研究方法和开题报告写作思路。
```

---

## 十四、推荐工作流

### 1. 整理单篇文献

```text
paper standard
↓
quality quick
↓
obsidian
```

### 2. 写文献综述

```text
review standard
↓
gap standard
↓
citation paragraph
```

### 3. 写开题报告

```text
gap standard
↓
method design
↓
theory framework
↓
proposal standard
↓
proposal revise
```

### 4. 写毕业论文

```text
thesis title
↓
thesis standard
↓
method design
↓
citation section
↓
thesis checklist
```

---

## 十五、日常最推荐 8 条

1. `paper standard`：解析论文。
2. `quality quick`：筛选论文。
3. `review standard`：整合文献。
4. `gap standard`：找研究空白。
5. `citation paragraph`：写综述段落。
6. `method design`：设计研究方法。
7. `proposal standard`：写开题报告。
8. `thesis standard`：优化论文题目、研究问题和目录。

---

## 十六、使用建议

不要一次上传 20 篇论文让 Codex 全部精读。建议：

```text
逐篇 paper standard
↓
生成文献卡
↓
5—10 篇文献卡一起 review
```

最适合毕业论文的流程：

```text
选题
↓
查文献
↓
文献卡
↓
文献综述
↓
研究空白
↓
开题报告
↓
论文初稿
```
