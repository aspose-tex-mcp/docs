---
translation: true
template: /templates/_template-net.md
title: 什么是 TikZ
linktitle: 什么是 TikZ
weight: 21
url: /net/tikz-introduction/
keywords: 什么是 TikZ, TikZ 介绍, TikZ 基础
description: TikZ 介绍，强大的扩展，用于在 LaTeX 文档中创建高质量图形。
lastmod: "2026-02-26"
aliases: /net/what-is-tikz/
---

{{<section overview>}}

## 什么是 TikZ？

TikZ（发音为“tik-zee”）全称是 “TikZ ist kein Zeichenprogramm”（德语），意为 “TikZ 不是绘图程序”。它是一个强大的扩展，用于在 TeX 和 LaTeX 文档中直接创建高质量的矢量图形。由 Till Tantau 设计，TikZ 允许用户使用直观、可读的代码嵌入复杂的图表、绘图以及其它可视化内容。

## 为什么使用 TikZ？

- **集成**：无缝地将图形集成到 TeX 文档中，保持一致的字体、样式和对齐。  
- **可扩展性**：生成高质量、可扩展的矢量图形，适用于专业出版物。  
- **灵活性**：支持多种图形元素，从基本几何形状到复杂的数学图示。  
- **社区与扩展**：庞大的库和活跃的社区提供大量预制组件和样式。

## 入门 TikZ

要开始使用 TikZ，请确保它已随您的 TeX 发行版一起安装（通常在标准安装如 TeX Live 或 MiKTeX 中已包含）。下面是一个简单的 “Hello, World” 示例，展示基本的 TikZ 语法：

```tex  
\\documentclass{article}  
\\usepackage{tikz}  

\\begin{document}

\\begin{tikzpicture}  
\\draw (0,0) -- (1,1) -- (1,0) -- cycle;  
\\end{tikzpicture}

\\end{document}  
```

此示例生成一个连接三个点的简单三角形。

## 内容

下面是本系列关于 TikZ 主题的概览：

1. [Installation and Basic Configuration](/tex/net/tikz-installation-and-basic-configuration/)  
2. [Fundamentals of Using TikZ](/tex/net/tikz-fundamentals-of-using-tikz/)  
3. [Advanced Features](/tex/net/tikz-advanced-features)  
4. [TikZ for Scientific Publications](/tex/net/tikz-for-scientific-publications/)  
5. [TikZ for Presentations and Infographics](/tex/net/tikz-for-presentations-and-infographics/)  
6. [Best Practices and Tips](/tex/net/tikz-best-practices-and-tips/)  

浏览这些文章，掌握使用 TikZ 创建专业质量图形的技巧。

**此外，探索我们的免费 [web app](https://products.aspose.app/tex/conversion/latex/)（基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/)），以实现快速简便的 TeX 转换。**
