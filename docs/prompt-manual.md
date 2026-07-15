# Education Research Assistant v2.7 提示词手册

## 一、单项任务

```text
请使用 education-research-assistant Skill，【模式】模式，【参数】完成【任务】。
材料范围：【全文/摘要/文献卡/已有内容】。
输出范围：【只要哪些部分】。
证据要求：区分作者明示、文本归纳、方法建议和材料不足；不要补造作者、年份、理论、数据和结论。
```

## 二、完整工作流：引导式

```text
请使用 education-research-assistant Skill，workflow 模式，执行【目标工作流】，选择 guided。

最终目标：【……】
现有信息：【……】
成果档位：【outline/standard/submission-ready/review-ready】

请根据我的回答自适应选择下一问题，每次只问一个关键问题。已经确认的信息不要重复询问；关键决定发生变化时，同步检查题目、问题、理论、方法、工具和目录。达到最低条件后提示我回复“执行”，再运行所选工作流全部阶段。
```

## 三、完整工作流：直接式

```text
请使用 education-research-assistant Skill，workflow 模式，执行【目标工作流】，选择 direct。

已有材料：【题目、对象、场域、数据、文献、方法】
成果档位：【outline/standard/submission-ready/review-ready】

请直接执行所选工作流全部阶段，不再提问。先列出已确认、暂定、缺失、冲突和必要假设；无法支持的内容明确标注，不要编造。
```

## 四、四条工作流

| 目标 | 工作流 |
|---|---|
| 论文解析、筛选与入库 | `paper-to-note` |
| 多篇文献整理与综述 | `literature-review` |
| 从方向到开题报告 | `proposal-design` |
| 从题目到完整论文方案 | `thesis-design` |

## 五、成果档位

| 档位 | 说明 |
|---|---|
| `outline` | 框架、对齐表和待确认项 |
| `standard` | 默认完整方案 |
| `submission-ready` | 材料充分时生成可直接修改提交的正式稿 |
| `review-ready` | 正式成果加严格评审和修改动作 |

## 六、引导式控制指令

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
保存进度
```

```text
恢复进度
```

```text
直接生成
```

```text
重新开始
```

```text
结束引导
```

## 七、引导式开题设计

```text
请使用 education-research-assistant Skill，workflow 模式，执行 proposal-design，选择 guided，成果档位为 standard。

我目前只有一个方向：【……】。
请优先确认研究对象、研究边界、真实问题、可获取数据、研究类型、理论或分析维度、方法和学校开题要求。每次只问一个问题；关键决定发生变化时同步修正下游内容。信息基本齐全后，再执行完整开题工作流。
```

## 八、引导式论文设计

```text
请使用 education-research-assistant Skill，workflow 模式，执行 thesis-design，选择 guided，成果档位为 review-ready。

我的研究方向是：【……】。
请自适应帮助我明确研究中心、核心概念、对象和范围、研究问题、数据来源、研究类型、理论框架、方法和目录。每次只问一个关键问题。完成后生成完整方案，并从导师或评委视角指出风险与修改动作。
```

## 九、引导式文献综述

```text
请使用 education-research-assistant Skill，workflow 模式，执行 literature-review，选择 guided。

主题为：【……】。
请逐步明确综述服务的论文题目、文献边界、材料类型、作者年份完整度、国内外呈现方式和最终输出形式。确认后再完成清点、事实卡、筛选、矩阵、聚类、研究脉络、研究空间和综述小节。
```

## 十、直接式开题设计

```text
请使用 education-research-assistant Skill，workflow 模式，执行 proposal-design，选择 direct，成果档位为 submission-ready。

题目：【……】
研究对象和场域：【……】
可获取数据：【……】
可实施方法：【……】
已有文献或理论：【……】
学校格式：【……】

请直接执行全部阶段。材料不足以达到 submission-ready 时，降级为 standard 并说明原因。
```

## 十一、直接式论文设计

```text
请使用 education-research-assistant Skill，workflow 模式，执行 thesis-design，选择 direct。

题目：【……】
研究对象：【……】
样本或材料：【……】
可用方法：【……】

请直接完成题目诊断、概念边界、研究问题、研究类型、理论或分析框架、方法、研究对齐表、目录、章节任务和风险检查。
```

## 十二、保存与恢复

保存：

```text
保存进度
```

恢复时粘贴检查点并输入：

```text
恢复进度
```

恢复后不得重复询问已确认内容。

## 十三、单篇论文解析

```text
请使用 education-research-assistant Skill，paper 模式，standard 深度，解析这篇论文。提取研究问题、概念与理论、对象、方法、数据、主要发现、贡献、局限和可借鉴价值。建立问题—方法—数据对应表和证据账本。只完成论文解析。
```

## 十四、论文质量评价

```text
请使用 education-research-assistant Skill，quality 模式，standard 深度，从研究问题、理论使用、方法适配、样本与数据、分析深度、结论边界、创新性和与我选题的相关性进行严格评价。每项判断说明依据。
```

## 十五、文献矩阵

```text
请使用 education-research-assistant Skill，review 模式，matrix 深度，清点和去重这些文献，生成逐篇事实账本和比较矩阵。无法确认的信息留空，不自行补齐。
```

## 十六、分类综述

```text
请使用 education-research-assistant Skill，review 模式，standard 深度，基于已核实文献卡完成主题聚类、研究脉络、共识、分歧、理论与方法比较、研究不足和综述骨架。每项综合判断说明支持文献。
```

## 十七、研究空间与选题

```text
请使用 education-research-assistant Skill，gap 模式，standard 深度，区分已有成果、研究不足、进一步研究空间和严格意义上的研究空白。结合我的研究条件生成3个本科可行选题，并说明数据、方法、有限创新和风险。
```

## 十八、研究方法设计

```text
请使用 education-research-assistant Skill，method 模式，design 深度，为题目《……》设计研究方案。先判断研究类型，再生成研究问题—证据—数据—方法—分析—章节对齐表。只保留必要方法。
```

## 十九、问卷维度

```text
请使用 education-research-assistant Skill，method 模式，design 深度，为题目《……》设计问卷维度。先说明核心概念和维度来源，再输出一级维度、二级维度、操作性定义、题项方向、依据和对应研究问题。不能先定维度再倒找依据。
```

## 二十、理论框架

```text
请使用 education-research-assistant Skill，theory 模式，framework 深度，为题目《……》设计理论或分析框架。先判断是否确实需要核心理论；如不需要，采用有来源的文献归纳框架。说明理论如何进入概念、维度、工具、分析和章节。
```

## 二十一、使用提醒

- 引导式自适应选择下一问，不机械问清单；
- 修改关键决定后检查下游影响；
- 检查点是可复制摘要，不是后台永久保存；
- 直接式不省略所选工作流阶段；
- `submission-ready` 不能掩盖材料不足；
- 结论强度不得超过样本、方法和证据。
