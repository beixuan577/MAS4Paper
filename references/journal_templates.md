# 期刊格式模板

## 国内核心期刊

### 1. 《经济研究》

**投稿要求:**
- 论文篇幅: 8000-15000字
- 摘要: 300-500字
- 关键词: 3-5个
- 参考文献: GB/T 7714格式

**格式模板:**
```
标题（黑体，三号，居中）
作者姓名（楷体，小四，居中）
（单位名称，城市 邮编）（宋体，小五）

摘要：（黑体）摘要内容……（宋体，五号）
关键词：（黑体）关键词1；关键词2；关键词3（宋体，五号）

一、一级标题（黑体，四号）
（正文，宋体，五号，1.5倍行距）

（一）二级标题（楷体，五号，加粗）

参考文献：
[1] 作者. 文献标题[J]. 期刊名, 年份, 卷(期): 页码.
```

---

### 2. 《管理世界》

**投稿要求:**
- 论文篇幅: 10000-20000字
- 摘要: 中英文各300字
- 图表: 中英文对照

---

### 3. 《经济学（季刊）》

**投稿要求:**
- 论文篇幅: 不限
- 格式: 参照《美国经济评论》
- 参考文献: 作者-年份制

---

## 国际顶刊

### 1. American Economic Review (AER)

**投稿要求:**
- 论文篇幅: 不超过12500词
- 摘要: 不超过100词
- 参考文献: Chicago格式

**LaTeX模板:**
```latex
\documentclass[aer]{article}
\usepackage{natbib}

\begin{document}

\title{Paper Title}
\author{Author Name}
\date{\today}

\maketitle

\begin{abstract}
Abstract text (max 100 words)...
\end{abstract}

\section{Introduction}
...

\bibliographystyle{aer}
\bibliography{references}

\end{document}
```

---

### 2. Journal of Political Economy (JPE)

**投稿要求:**
- 论文篇幅: 不限
- 摘要: 不超过150词
- 参考文献: 作者-年份制

---

### 3. Quarterly Journal of Economics (QJE)

**投稿要求:**
- 论文篇幅: 不限
- 摘要: 不超过100词
- 强调政策启示

---

## 参考文献格式

### APA格式（常用）

```
期刊文章:
Author, A. A., & Author, B. B. (Year). Title of article. Title of Periodical, volume(issue), pages.

书籍:
Author, A. A. (Year). Title of work. Publisher.

网络资源:
Author, A. A. (Year, Month Day). Title. Website. URL
```

### GB/T 7714格式（中文期刊）

```
期刊文章:
[序号] 作者. 文献题名[J]. 刊名, 出版年, 卷(期): 起止页码.

书籍:
[序号] 作者. 书名[M]. 出版地: 出版者, 出版年.

学位论文:
[序号] 作者. 题名[D]. 保存地: 保存者, 年份.
```

---

## 图表规范

### 表格规范

```
表1  描述性统计

变量        观测值    均值    标准差    最小值    最大值
GDP增长率    1000     0.05    0.02     -0.02     0.15
FDI占比      1000     0.03    0.01      0.00     0.12

注：数据来源于国家统计局；时间范围2000-2020年。
```

### 图表规范

```python
# 出版级图表设置
plt.rcParams.update({
    'font.family': 'Times New Roman',
    'font.size': 10,
    'axes.labelsize': 11,
    'axes.titlesize': 12,
    'legend.fontsize': 9,
    'figure.figsize': (7, 5),  # 单栏宽度
    'figure.dpi': 300,
})

# 双栏图表
fig, (ax1, ax2) = plt.subplots(1, 2, figsize=(14, 5))
```
