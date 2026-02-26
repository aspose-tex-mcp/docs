---
translation: true
template: /templates/_template-net.md
title: LaTeX 模板 - 快速入门指南
linktitle: LaTeX 模板
type: docs
weight: 100
url: /net/latex-templates/
description: 了解 LaTeX 模板是什么，如何使用和创建它们，在哪里下载最流行的模板，以及使用可直接复制的代码片段的快速工作流。
keywords: LaTeX, 模板, 类, 样式, Overleaf, CTAN, 参考文献, Beamer, 论文, 简历
lastmod: "2026-02-26"
---

{{<section overview>}}

# LaTeX 模板指南

## 什么是 LaTeX 模板？

LaTeX 模板包含一个**类**（`.cls`）、**样式**（`.sty`）、示例 `.tex` 文件和支持资源（徽标、参考文献文件等），用于定义特定文档类型（期刊文章、论文、简历、海报、幻灯片等）的布局、排版和结构。

## 如何使用 LaTeX 模板

1. **下载**压缩文件或克隆仓库。
2. 打开主 `.tex` 文件（通常称为 `main.tex` 或 `article.tex`）。
3. 加载模板提供的类或样式，并按照 README 文件中的“结构”（标题页、摘要、章节、参考文献）进行操作。

```latex
\documentclass[options]{mytemplate}   % class supplied by the template
\usepackage{mytemplate}               % sometimes a .sty instead of .cls
\begin{document}
  \title{My Title}
  \author{Me}
  \maketitle
  % <content>
\end{document}
```

使用 `pdflatex`、`latexmk -pdf` 或 Overleaf 的“重新编译”按钮进行编译。

## 如何创建自己的模板

| **目标** | **推荐文件** | **极简框架** |
|------|------------------|-----------------|
| 完全控制文档结构 | **类** (`.cls`) | 参见下方代码块 |
| 仅包含额外的宏或格式设置 | **样式** (`.sty`) | – |
| 分发 | Zip 压缩包或 GitHub 仓库（包含类/样式文件、可选的 `.bib` 文件、徽标和 README 文件） | – |

### Minimal class skeleton (`mytemplate.cls`)

```latex
% mytemplate.cls – a very simple article‑style class
\NeedsTeXFormat{LaTeX2e}
\ProvidesClass{mytemplate}[2025/12/03 v1.0 My custom class]
\LoadClass[12pt]{article}   % inherit from article

% ---- custom settings ----
\RequirePackage{geometry}
\geometry{margin=2cm}
\RequirePackage{fontspec}
\setmainfont{Latin Modern Roman}

% ---- user‑level commands ----
\newcommand\mytitle[1]{\centerline{\LARGE\bfseries #1}}
\endinput
```

在文档中将其与 `\documentclass{mytemplate}` 一起使用。

## 在哪里下载 LaTeX 模板

- **Overleaf Gallery** – 最大的公共集合（≈ 4 000 个免费模板）。  
  <https://www.overleaf.com/gallery>
- **CTAN (Comprehensive TeX Archive Network)** – official repository for journal‑specific classes.  
  <https://ctan.org/>
- **GitHub / GitLab** – 许多作者发布开源的论文或会议模板。  
- 大学/研究所网页 – 大多数学校提供“官方”论文/学位论文模板。

## 最常用 / 高评分模板

| **#** | **Template** | **Typical use** |
|---|----------|-------------|
| 1 | **IEEEtran** (`ieeetran.cls`) | IEEE 会议论文和期刊论文 |
| 2 | **Springer LNCS** (`llncs.cls`) | 计算机科学讲义 |
| 3 | **Elsevier 文章** (`elsarticle.cls`) | Elsevier 期刊 |
| 4 | **现代简约简历** | 单页简历 |
| 5 | **经典论文** (`classicthesis.sty`) | 排版精美的书籍/论文 |
| 6 | **Beamer** (`beamer.cls`) | 幻灯片演示 |
| 7 | **a0poster / tikzposter** | 大型科学海报 |
| 8 | **大学特定论文** (例如，`cambridgephd.cls`) | 机构博士/硕士论文 |
| 9 | **天文学与天体物理学** (`aa.cls`) | A&A 期刊文章 |
|10 | **基础学术期刊文章** | 文章写作入门指南 (Overleaf) |

## 首次使用者的快速工作流

1. **选择一个模板** → 点击“在 Overleaf 中打开” **或** 下载 ZIP 文件。
2. **编辑占位符字段**（例如 `\title{}`、`\author{}` 等）。
3. **编译** → 生成 PDF 文件。
4. 如果您在本地工作：解压缩 → 运行 `latexmk -pdf main.tex`（或根据需要运行 `pdflatex` + `biber`）。

5. **导出** PDF 文件或将源代码推送到 Git 仓库进行版本控制。

## 常见陷阱与技巧

- **缺少软件包** – 使用发行版管理器安装（`tlmgr install <pkg>` 或 MiKTeX 控制台）。
- **过时的类** – Overleaf 使用的是最新的 TeX Live；请定期更新您本地的 TeX 安装。
  **类过时** – Overleaf 使用最新的 TeX Live；请定期更新本地 TeX 安装。
- **参考文献引擎** – 许多现代模板都支持 `biber`。在第一次 LaTeX 编译后运行 `biber <basename>`。 
- **品牌资产** – 替换徽标、彩色 PDF 或定义机构颜色的 `.sty` 文件。
- **自定义命令** – 将它们保存在单独的 `.sty` 文件中；这样您就可以在多篇论文中重复使用相同的布局。

## Aspose 怎么样？

文件（合并、添加水印或转换为其他格式）时，诸如 **Aspose.TeX** 之类的库提供了一个与语言无关的 API，用于处理 PDF 文件，而无需完整的 LaTeX 工具链。
---

### TL;DR 快速概览

```text
What?   → 预构建布局（类+样式+资源）
Use?    → \documentclass{mytemplate} + 按 README 操作
Create? → 编写 .cls 或 .sty → 打包资源 → zip/GitHub
Get?    → Overleaf Gallery、CTAN、GitHub、大学站点
Hot 10  → IEEEtran、llncs、elsarticle、modern‑simple‑cv、
          classicthesis、beamer、a0poster、UNICAMP 论文、
          aa.cls、基础学术期刊文章
```

排版愉快！
