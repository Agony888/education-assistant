# Education Research Assistant v2.6.1 调用示例

## 一、完整任务：先让用户选择

```text
请使用 education-research-assistant Skill，帮我从选题做到开题报告。
```

Skill 应先询问：

```text
你希望怎样完成？

A. 引导式：每次只确认一个关键问题，梳理完成后执行完整工作流。
B. 直接式：根据现有材料立即执行完整工作流，缺失内容明确标注。
```

## 二、引导式完整流程

### 1. 引导式开题设计

```text
请使用 education-research-assistant Skill，workflow 模式，执行 proposal-design 流程，选择 guided。
我目前只有一个方向：乡镇小学数学教师数字化教学资源选择与整合能力。
请每次只问我一个关键问题。等题目、对象、研究问题、数据条件、理论和方法梳理清楚后，再执行完整开题工作流。
```

### 2. 引导式论文设计

```text
请使用 education-research-assistant Skill，workflow 模式，执行 thesis-design 流程，选择 guided。
我想研究生成式 AI 辅助小学数学教师教学反思，但题目和研究方法还不明确。
请一步一步引导，每次只问一个问题；信息齐全后再生成完整论文设计。
```

### 3. 引导式文献综述

```text
请使用 education-research-assistant Skill，workflow 模式，执行 literature-review 流程，选择 guided。
我准备写教师数字素养方面的文献综述，但还不确定综述边界。请逐步帮我确定综述主题、文献范围和最终结构，再执行完整综述工作流。
```

### 4. 引导中切换为直接生成

```text
直接生成
```

Skill 应使用当前已经收集的信息，切换到 `direct`，执行同一目标工作流的全部阶段。

## 三、直接式完整流程

### 1. 直接式开题设计

```text
请使用 education-research-assistant Skill，workflow 模式，执行 proposal-design 流程，选择 direct。

题目：《乡镇小学数学教师数字化教学资源选择与整合能力现状及提升策略研究》
研究对象：H市D县乡镇小学数学教师
可接触对象：约60名教师
可用方法：问卷和访谈

请直接执行全部开题阶段，不再提问。缺失信息、暂定判断和必要假设单独列出。
```

### 2. 直接式论文设计

```text
请使用 education-research-assistant Skill，workflow 模式，执行 thesis-design 流程，选择 direct。
围绕题目《……》，直接完成概念边界、研究问题、研究类型、理论框架、方法、研究对齐表、目录、章节任务和风险检查。
```

### 3. 直接式文献综述

```text
请使用 education-research-assistant Skill，workflow 模式，执行 literature-review 流程，选择 direct。
根据这些文献卡直接完成清点去重、事实卡、筛选、矩阵、主题聚类、研究脉络、研究空间、综述小节和证据覆盖检查。不要新增文献。
```

### 4. 直接式论文入库

```text
请使用 education-research-assistant Skill，workflow 模式，执行 paper-to-note 流程，选择 direct。
直接完成材料检查、论文事实解析、质量筛选、Obsidian 文献卡和字段完整性检查。
```

## 四、引导式控制指令

```text
查看进度
```

```text
修改：研究对象=乡镇小学数学教师
```

```text
跳过
```

```text
不确定
```

```text
重新开始
```

```text
结束引导
```

## 五、单项任务

### 1. 单篇论文解析

```text
请使用 education-research-assistant Skill，paper 模式，standard 深度，解析这篇论文。区分作者明示、文本归纳和材料不足，关键判断标注页码、章节或表格位置。只完成论文解析。
```

### 2. 论文价值筛选

```text
请使用 education-research-assistant Skill，quality 模式，quick 深度，判断这篇论文是否值得精读，适合作为核心文献、背景文献、方法参考还是不建议使用。不要完整解析论文。
```

### 3. Obsidian 文献卡

```text
请使用 education-research-assistant Skill，obsidian 模式，把这篇论文整理成可直接保存的 Markdown 文献卡。只输出文献卡。
```

### 4. 文献矩阵

```text
请使用 education-research-assistant Skill，review 模式，matrix 深度，清点并去重这些文献，建立逐篇事实账本和比较矩阵。无法确认的信息不要补齐。
```

### 5. 文献综述

```text
请使用 education-research-assistant Skill，review 模式，standard 深度，基于已核实文献卡完成主题聚类、研究脉络、共识与分歧、理论方法比较和研究不足。每项综合判断说明支持文献。
```

### 6. 研究空间与选题

```text
请使用 education-research-assistant Skill，gap 模式，standard 深度，区分已有成果、研究不足、进一步研究空间和严格意义上的空白，再结合我的研究条件生成本科可行选题。
```

### 7. 研究方法设计

```text
请使用 education-research-assistant Skill，method 模式，design 深度，为题目《……》设计研究方案。先判断研究类型，再生成研究问题—证据—数据—方法—分析—章节对齐表。
```

### 8. 开题报告单项

```text
请使用 education-research-assistant Skill，proposal 模式，standard 深度，根据题目《……》和现有文献生成开题报告核心内容。没有完成的研究不要写成已有结果。
```

### 9. 毕业论文设计单项

```text
请使用 education-research-assistant Skill，thesis 模式，standard 深度，完成研究边界、核心概念、研究问题、研究类型、理论框架、方法和目录设计。目录不得默认套用“现状—问题—原因—策略”。
```

## 六、专项调用

### AI+教育

```text
优先读取 ai-education-bank.md，重点检查 AI 应用场景、教师二次判断、人机分工、内容准确性、真实教学可行性和伦理边界。
```

### 小学数学

```text
优先读取 primary-math-bank.md 和 math-curriculum-standard-bank.md，重点检查数学本质、核心素养、学段特点、活动思维含量、评价证据和作业质量。
```

### 教师发展

```text
优先读取 teacher-development-bank.md，重点检查教师数字或智能素养、专业发展、教学反思、培训支持和乡村学校条件。
```
