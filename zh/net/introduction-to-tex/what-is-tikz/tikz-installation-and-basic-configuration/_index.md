---
translation: true
template: /templates/_template-net.md
title: 安装和基本配置 | Aspose.TeX .NET
linktitle: 安装和配置
weight: 18
url: /net/tikz-installation-and-basic-configuration/
aliases: /net/installation-and-basic-configuration/
keywords: 安装 tikz, 配置 tikz, 设置 tikz
description: 分步指南，教您如何安装和配置 TikZ，以在您的 TeX 和 LaTeX 文档中使用。
lastmod: "2026-04-22"
---

{{<section overview>}}

本章节介绍 TikZ 扩展在 TeX 和 LaTeX 中的安装和基本配置。我们将提供清晰的分步指南，帮助您快速开始使用 TikZ 创建图形。

## 安装 TikZ

TikZ 已随流行的 TeX 发行版预装，如 **TeX Live** 和 **MiKTeX**。如果您使用这些发行版，可能已经安装了 TikZ。如果没有，请按照以下说明操作：

### TeX Live 用户

1. 打开 TeX Live Manager（`tlmgr`）。
2. 更新包列表：
   ```bash
   tlmgr update --self --all
   ```
3. 安装 TikZ（`pgf` 包的一部分）：
   ```bash
   tlmgr install pgf
   ```

### MiKTeX 用户

1. 打开 MiKTeX Console。
2. 转到 **Packages** 选项卡。
3. 在搜索栏中输入 `pgf`。
4. 选择并安装 `pgf` 包（如果尚未安装）。

## 验证安装

您可以使用以下简单的测试文档来验证 TikZ 是否成功安装：

```tex
\documentclass{article}
\usepackage{tikz}

\begin{document}

Testing TikZ:
\begin{tikzpicture}
  \draw (0,0) rectangle (2,1);
\end{tikzpicture}

\end{document}
```

使用 `pdflatex` 或任何兼容 LaTeX 的编辑器（如 TeXworks 或 Overleaf）编译此文档。您应在生成的 PDF 中看到一个小矩形。

## TikZ 的基本配置

TikZ 需要的配置很少。不过，您可以设置全局选项来控制图形行为：

- **全局缩放图形**：
  ```tex
  \tikzset{every picture/.style={scale=1.5}}
  ```

- **设置默认颜色和线条样式**：
  ```tex
  \tikzset{
    every path/.style={thick, blue},
    every node/.style={font=\small}
  }
  ```

将这些命令放入文档的导言区，以实现统一的样式。

## 推荐的 TikZ 编辑器

为了便于编辑和实时编译，我们推荐以下 LaTeX 编辑器：

- **TeXstudio** – 免费、功能丰富的编辑器，内置 TikZ 预览。
- **Overleaf** – 基于云的协作编辑器，提供出色的 TikZ 支持。
- **Visual Studio Code** 与 **LaTeX Workshop** 扩展 – 现代、轻量的编辑器，支持 TikZ。

根据您的偏好和工作流需求选择合适的编辑器。

---

通过遵循这些说明，您将成功设置 TikZ，并能够为您的 TeX 和 LaTeX 文档创建出色的图形。

**此外，探索基于 [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) 的免费 [Web 应用](https://products.aspose.app/tex/conversion/latex/) ，实现快速、简便的 TeX 转换。**
