---
translation: true
template: /templates/_template-net.md
title: 外部 LaTeX 包 | Aspose.TeX for .NET
linktitle: 外部 LaTeX 包
weight: 20
url: /net/external-latex-packages/
description: Aspose.TeX API for .NET 允许使用外部包，即库本身未包含的包，如 fancybox 和 pgfplots 包。
keywords: 外部 LaTeX 包、Aspose.TeX、.NET TeX、LaTeX 包、fancybox、pgfplots、必需输入目录、输入 zip 文件、自定义输入目录、TeX 转换
lastmod: "2026-02-25"
---

{{<section overview>}}

## 外部 LaTeX 包

**Aspose.TeX** 库已经包含了许多[常用 LaTeX 包](/tex/{{lang.url-fragment}}net/embedded-packages/)。因此您无需担心如何向库的 TeX 引擎提供这些包。但有时（甚至经常）您的 LaTeX 文件可能需要超出“原生”支持的“捆绑”包。如果出现这种情况，您可以尝试通过 [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) 类实例的 [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) 选项提供所需的输入，即所需包的源文件。下面我们将通过两个示例来演示其工作方式。

### 已解压的必需输入（`fancybox` 包）

假设我们有下面这个简单的 LaTeX 文件，它来自我们的[示例解决方案](https://GitHub.com/aspose-tex/Aspose.TeX-for-.NET)中的 `required-input-fs.tex`：


```tex
\documentclass{article}
\usepackage[a6paper,landscape]{geometry}
\usepackage{fancybox}
\begin{document}
Test: \fbox{
  \begin{Bitemize}[b]
  \item First item
  \item A second one\\ on two lines
  \item(2pt) A third with extra space
  \end{Bitemize}
}
\par\bigskip
Test: \fbox{
  \begin{Beqnarray}[t]
  y & = & x^2 \\
  a^2 + 2ab + b^2 & = & (a + b)^2 \\
  \int_0^\infty e^{-ax} dx & = & \frac{1}{a}
  \end{Beqnarray}
}
\end{document}
```

在第 3 行可以看到文件需要 `fancybox` 包，而该包并未被“原生”支持。假设我们已经拥有 `fancybox` 包的源文件。它是一个简单的包，仅包含单个文件。我们可以将此文件放在文件系统的任意位置，并按如下方式指定目录路径：


```C#
options.RequiredInputDirectory = new InputFileSystemDirectory("path-to-directory-where-fancybox.sty-located");
```

使用此选项运行 TeX 作业后（别忘了根据需要调整其他选项），我们得到输出文档（即 PNG 图像）。

![Output Document](/tex/images/net/Conversion-RequiredInputFs.png)

以下是该示例的完整源代码：

{{< gist "aspose-com-gists" "03f720960e15bd497ed26ce2eb9c03b2" "Example-RequiredInput-FileSystem.cs" >}}

### 已归档的必需输入（`pgfplots` 包）

现在假设我们还有下面这个同样相当简单的 LaTeX 文件，它来自示例解决方案中的 `required-input-zip.tex`：


```tex
\documentclass{article}
\usepackage[margin=0.25in]{geometry}
\usepackage{pgfplots}
\pgfplotsset{width=10cm,compat=1.18}
\begin{document}

第一个示例是并排绘制的二维和三维数学表达式。

%Here begins the 2D plot
\begin{tikzpicture}
\begin{axis}
\addplot[color=red]{exp(x)};
\end{axis}
\end{tikzpicture}
%Here ends the 2D plot
\hskip 5pt
%Here begins the 3D plot
\begin{tikzpicture}
\begin{axis}
\addplot3[
    surf,
]
{exp(-x^2-y^2)*x};
\end{axis}
\end{tikzpicture}
%Here ends the 3D plot

\end{document}
```


在第 3 行可以看到文件需要 `pgfplots` 包，同样未被“原生”支持。再次假设我们已经拥有 `pgfplots` 包的源文件。该包文件数量较多，分布在两个位置：`\tex\generic` 和 `\tex\latex` 文件夹中。必须将这两个文件夹的内容作为必需输入提供给 Aspose.TeX 库。我们希望将这些源文件打包成 ZIP 存档，存档的布局如下：

![Archive’s Layout](/tex/images/net/pgfplots-zip-layout.png)

下面演示如何指定对这些源文件的访问方式：


```C#
using (Stream zipStream = File.Open("path-to-zip-with-pgfplots-sources", FileMode.Open))
{
    ...
    options.RequiredInputDirectory = new InputZipDirectory(zipStream);
    ...
}
```

使用此选项运行 TeX 作业后，我们得到输出文档：

![Output Document](/tex/images/net/Conversion-RequiredInputZip.png)

以下是该示例的完整源代码：

{{< gist "aspose-com-gists" "03f720960e15bd497ed26ce2eb9c03b2" "Example-RequiredInput-Zip.cs" >}}

> **_注意：_** 结果已使用 `pgfplots` 包版本 1.18.1 验证。**Aspose.TeX** 库中包含的 `pfg` 包版本为 3.1.9a。

### 使用外部字体包

通常，LaTeX 发行版会提供一套默认字体供排版使用。除这些字体外，**Aspose.TeX** 还包含若干非标准字体包，例如 `amsfonts`、`eurosym` 和 `wasysym`。正如前文所述，Aspose.TeX 也允许使用外部包，但大多数情况下我们讨论的是不包含字体的包。

**Aspose.TeX** 的 *Object TeX* 引擎扩展需要字体映射文件（即扩展名为 `.map` 的文本文件），以确定每个 TeX 内部字体名对应的实际字体。这些映射文件必须在初始化阶段加载到 TeX 的内存中，并且必须随您引入的包一起存在。由于引擎不知道所有字体映射的名称，它会搜索所有扩展名为 `.map` 的文件。因此，实现用于 `RequiredInputDirectory` 选项的 [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/) 接口时，需要提供一种按扩展名访问文件名集合的方式。更具体地说，该实现还必须实现 [IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/) 接口。标准实现——[InputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) 和 [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/)——已经具备此功能。

下面提供一个自定义必需输入目录的示例，该示例同样实现了 [IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/) 接口。示例侧重于按扩展名收集文件名，省略了文件存储和检索的细节。

{{< gist "aspose-com-gists" "03f720960e15bd497ed26ce2eb9c03b2" "Example-RequiredInputDirectory.cs" >}}

### 限制

如果您的 LaTeX 文件所需的包是基于 *LaTeX3e* 内核开发的，则该包很可能无法与 **Aspose.TeX** 库一起工作，因为后者基于 *LaTeX2e* 内核。

此外，如果您的 LaTeX 文件所需的包直接调用了 **Aspose.TeX** 的 *Object TeX* 引擎不支持的设备相关原语命令，则该包肯定无法工作。
