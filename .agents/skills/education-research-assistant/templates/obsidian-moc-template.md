# {{主题}} MOC

## 一、主题说明

本 MOC 用于整理与“{{主题}}”相关的文献、概念、理论和写作材料。

## 二、核心文献

```dataview
TABLE author, year, source, rating, usefulness
FROM #文献笔记
WHERE contains(related_topics, "{{主题}}") OR review_section = "{{主题}}"
SORT year DESC
```

## 三、按研究主题分类

### 1. 理论与概念研究

### 2. 现状调查研究

### 3. 实践应用研究

### 4. 问题与策略研究

## 四、可用于文献综述的观点

## 五、研究空白

## 六、可转化选题
