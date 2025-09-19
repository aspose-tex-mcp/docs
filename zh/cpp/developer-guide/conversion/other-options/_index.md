---
translation: true
template: /templates/_template-cpp.md
title: 其他管理Tex选项| C++的Aspose.TeX
linktitle: 其他选项
weight: 17
url: /cpp/other-options/
description: C ++的Aspose.TeX API解决方案的转换功能，让我们设置发动机启动的初始相互作用模式。这是一些代码示例。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 如何设置交互模式

正如我们提到的[此处](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes)，**aspose.tex 用于C ++**让我们设置发动机启动的初始交互模式。这是我们的工作方式：

```C++
// Create conversion options instance.
...
// Set the interaction mode.
options->set_Interaction(Interaction::NonstopMode);
```

## 如何设置工作名称

当我们将主要输入文件作为文件名传递时，我们将获得具有相同名称的输出文件，尽管其他扩展名。 Tex引擎将输入文件的名称称为 *作业名称*，并将其用于输出文件，除非在编写具有明确指定其他名称的辅助文件的情况下。当我们以[流](/tex/{{lang.url-fragment}}cpp/other-ways-of-main-input/#providing-the-main-input-file-as-a-stream)为单位的主要输入文件时，Tex引擎使用默认的作业名称，即 *texput*。
在这两种情况下，我们都可以通过分配适当的转换选项来覆盖作业名称。

```C++
// Create conversion options instance.
...
// Set the job name.
options->set_JobName(u"my-job-name");
```
## 如何重复工作

正如我们已经提到的[上文](/tex/{{lang.url-fragment}}net/latex-io/#latex-input)有关标签和参考文献的情况，在某些情况下，我们想两次运行相同的工作。这是可以做到的：
```C++
// Create conversion options instance.
...
// Set the job name.
options->set_Repeat(true);
```