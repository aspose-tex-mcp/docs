---
translation: true
template: /templates/_template-java.md
title: 提供主TeX输入文件的其他方法 | Java
linktitle: 提供主TeX输入文件的其他方法
weight: 14
url: /java/other-ways-of-main-input/
description: Java的Aspose.TeX API解决方案的转换功能具有一个构造函数，该构造函数接受流作为第一个参数。这是一些代码示例。
lastmod: "2026-04-21"
---

{{<section overview>}}

## 将主要输入文件作为流提供给TeX引擎

到目前为止，我们只知道如何将[主输入文件](/tex/{{lang.url-fragment}}net/tex-io/#tex-input)传递给TeX引擎作为文件名，无论是完全指定还是简短形式，无论是扩展名还是没有扩展名。但是，“ Texjob”类中还有另一个[构造函数](https://reference.aspose.com/tex/java/com.aspose.tex/TeXJob#TeXJob-java.io.InputStream-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-)，它接受流作为第一个参数。如果出于某种原因，我们将主要输入文件中的主要输入文件中的其他形式除外，则很方便。这是我们可以处理的方法：

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-InputStream.java" >}}

请注意，所有输出文件都有名称 *texput*。那是因为引擎在任何地方都无法获得任何其他名称。 *texput*是默认作业名称。有关工作名称的详细信息，请参见[此处](/tex/{{lang.url-fragment}}net/tex-io/#tex-output)和[此处](/tex/{{lang.url-fragment}}java/other-options/#how-to-set-the-job-name)。

## 从终端输入主TeX输入文件

“ Texjob”类还有另一个[构造函数](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) ，它根本不允许我们指定输入。那么，您可能会想知道什么是这样的TeX工作？这次我们将需要一个输入终端。 TeX引擎将要求我们从终端输入文件名。

这是代码：

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-MainInputTerminal.java" >}}

一旦运行，发动机都会粘贴，等待我们输入文件名(有或没有路径，有或没有扩展的情况)：


![终端窗口](/tex/images/java/Conversion-MainInputTerminal.png)

这就是它在输出终端上的外观，即控制台：

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode
**<path_to_the_file>/hello-world.ltx
(<path_to_the_file>/hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.xps (1 page).
Transcript written on hello-world.log.
```