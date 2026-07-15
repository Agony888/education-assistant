# Obsidian Dataview 查询模板

## 1. 查看所有中文教育论文

```dataview
TABLE author, year, source, paper_type, rating
FROM #文献笔记
WHERE type = "中文教育论文"
SORT year DESC
```

## 2. 查看某一综述板块文献

```dataview
TABLE author, year, method, theory, usefulness
FROM #文献笔记
WHERE review_section = "教师数字素养研究"
SORT year DESC
```

## 3. 查看核心文献

```dataview
TABLE author, year, source, review_section
FROM #文献笔记
WHERE rating = "核心文献" OR rating = "A"
SORT year DESC
```

## 4. 查看待精读文献

```dataview
TASK
FROM #文献笔记
WHERE !completed AND contains(text, "是否精读")
```
