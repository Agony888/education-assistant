# Education Research Assistant v2.7 调用示例

## 1. 未指定入口

```text
请使用 education-research-assistant Skill，帮我从研究方向做到完整开题报告。
```

Skill 应先让用户选择：

```text
A. 引导式
B. 直接式
```

## 2. 自适应引导式论文设计

```text
请使用 education-research-assistant Skill，workflow 模式，执行 thesis-design，选择 guided，成果档位为 standard。

我的方向是：乡镇小学数学教师数字化教学资源选择与整合能力。
请根据我的回答动态选择下一问题，每次只问一个关键问题。已经确认的内容不要重复询问；修改关键决定时同步检查研究问题、方法、问卷维度和目录。
```

## 3. 引导式严格评审版

```text
请执行 proposal-design，选择 guided，成果档位为 review-ready。
请逐步梳理题目、对象、数据、理论和方法，最后生成完整开题方案，并从导师或评委视角列出风险和修改动作。
```

## 4. 直接式完整论文设计

```text
请使用 education-research-assistant Skill，workflow 模式，执行 thesis-design，选择 direct，成果档位为 standard。

题目：《乡镇小学数学教师数字化教学资源选择与整合能力现状及提升策略研究》
研究对象：H市D县乡镇小学数学教师
可接触对象：约60名教师
可用方法：问卷、访谈

请直接执行 thesis-design 的全部阶段，不再提问。缺失信息和必要假设单独列出。
```

## 5. 修改关键决定

```text
修改：研究对象=乡镇小学数学教师
```

Skill 应同步检查：

```text
题目
样本范围
问卷和访谈对象
研究问题
数据来源
论文目录
```

## 6. 查看进度

```text
查看进度
```

应显示：完成度、已确认、暂定、冲突、缺失和下一问题。

## 7. 保存进度

```text
保存进度
```

Skill 输出可复制 YAML 检查点。

## 8. 恢复进度

```text
恢复进度
```

同时粘贴检查点。恢复后不重复询问已确认信息。

## 9. 中途直接生成

```text
直接生成
```

Skill 使用当前输入包切换为 `direct`，执行同一目标工作流全部阶段。

## 10. 正式稿档位

```text
请执行 proposal-design，选择 direct，成果档位为 submission-ready。
材料不足以形成正式稿时，请降级为 standard 并说明缺少什么。
```

## 11. 论文解析

```text
请使用 education-research-assistant Skill，paper 模式，standard 深度，解析这篇论文。区分作者明示、文本归纳和材料不足，关键判断标注页码、章节或表格位置。只完成论文解析。
```

## 12. 文献矩阵

```text
请使用 education-research-assistant Skill，review 模式，matrix 深度，清点并去重这些文献，建立逐篇事实账本和比较矩阵。无法确认的信息不要补齐。
```

## 13. 文献综述完整流程

```text
请使用 education-research-assistant Skill，workflow 模式，执行 literature-review，选择 direct。
根据这些文献卡完成清点、去重、事实卡、筛选、矩阵、聚类、研究脉络、研究空间、综述小节和证据覆盖检查。
```

## 14. 问卷维度设计

```text
请使用 education-research-assistant Skill，method 模式，design 深度，为题目《……》设计问卷维度。先说明核心概念和维度来源，再输出操作性定义、题项方向、依据和对应研究问题。
```

## 15. 理论框架设计

```text
请使用 education-research-assistant Skill，theory 模式，framework 深度，为题目《……》设计理论或分析框架。说明理论如何进入概念、维度、工具、分析和章节。
```

## 16. 专项知识库

### AI+教育

```text
优先读取 ai-education-bank.md，检查应用场景、人机分工、内容准确性、教师二次判断和伦理边界。
```

### 小学数学

```text
优先读取 primary-math-bank.md 和 math-curriculum-standard-bank.md，检查数学本质、核心素养、学段特点、活动、评价和作业。
```

### 教师发展

```text
优先读取 teacher-development-bank.md，检查教师数字或智能素养、专业发展、培训和乡村学校条件。
```
