# ERA v2.5 Math Curriculum Standard：Education Research Assistant

这是一个面向 Codex 的中文教育科研 Skill。

## 一、目录结构

```text
.agents/
└── skills/
    └── education-research-assistant/
        ├── SKILL.md
        ├── templates/
        └── knowledge/
```

## 二、v2.3 精修重点

1. `SKILL.md` 精简为主控规则；
2. 详细模板移动到 `templates/`；
3. 教育理论、研究方法、综述表达、毕业论文、Obsidian 规则移动到 `knowledge/`；
4. 强化 `thesis` 毕业论文写作模式；
5. 强化 `obsidian` 文献知识库模式；
6. 增加 token 控制文件，避免过度输出。

## 三、可用模式

```text
paper      单篇论文解析
review     多篇文献综述整合
method     研究方法分析与设计
theory     理论基础与分析框架
quality    论文质量评价
gap        研究空白与选题切口
citation   文献综述表达生成
proposal   开题报告专项生成与修改
thesis     毕业论文写作辅助
obsidian   Obsidian 文献知识库
```

## 四、推荐使用

```text
请使用 education-research-assistant Skill，paper 模式，standard 深度，解析这篇中文教育论文。
```

```text
请使用 education-research-assistant Skill，thesis 模式，帮我优化这个毕业论文题目并生成论文框架。
```

```text
请使用 education-research-assistant Skill，obsidian 模式，把这篇论文整理成 Obsidian 文献卡。
```


## 五、v2.4 新增专项知识库

本版新增三个专项知识库：

```text
knowledge/
├── ai-education-bank.md
├── primary-math-bank.md
└── teacher-development-bank.md
```

### 1. AI+教育专项知识库

支持：

- 生成式 AI 辅助教学；
- AI 辅助备课；
- AI 辅助作业设计；
- AI 辅助教学反思；
- 教师 AI 素养；
- AI 教育伦理；
- AI+教育文献综述；
- AI+教育选题与开题报告。

### 2. 小学数学专项知识库

支持：

- 小学数学核心素养；
- 小学数学教学设计；
- 小学数学作业设计；
- 小学数学课堂评价；
- 小学数学教学反思；
- AI 辅助小学数学教学；
- 小学数学方向毕业论文选题。

### 3. 教师发展专项知识库

支持：

- 教师数字素养；
- 教师智能素养；
- 教师数据素养；
- 教师专业发展；
- 乡村教师发展；
- 教师教学反思；
- 教师培训；
- 职前教师培养。


## 六、v2.5 新增：小学数学课程标准专项知识库

新增：

```text
knowledge/math-curriculum-standard-bank.md
```

该文件用于深化小学数学课标相关任务，支持：

- 小学数学核心素养分析；
- 第一、第二、第三学段目标分析；
- 数与代数、图形与几何、统计与概率、综合与实践内容分析；
- 教学目标、教学重难点、学习活动设计；
- 作业设计评价；
- 课堂评价与表现性评价；
- AI 生成小学数学教学设计质量判断；
- 小学数学开题报告和文献综述中的课标化表达。


## 文档目录

```text
docs/
└── prompt-manual.md
```

`docs/prompt-manual.md` 是完整提示词使用手册，包含论文解析、文献综述、研究方法、理论基础、开题报告、毕业论文写作和 Obsidian 文献库等常用调用提示词。
