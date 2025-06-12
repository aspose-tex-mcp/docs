---
translation: true
template: /templates/_template-net.md
linktitle: 对象Tex
title: Aspose.TeX和对象Tex | Aspose.TeX for .NET
weight: 11
url: /net/aspose-tex-and-object-tex/
description: TEX是此API解决方案的输入和输出格式，因此我们可以在这里解释对象Tex以及如何将其转换为目标格式。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 对象Tex

现在，让我们考虑输出格式。

原始TEX仅能以 *DVI*(独立)格式输出文件。碰巧的是，DVI格式并未定义要打印文件的媒体的指标 - 页面大小和整个页面内容的左上角的位置。一旦我们决定使TEX引擎能够输出文件，例如，我们需要定义此类指标。因此，我们需要将新的原始图包括在原始Tex发动机的套装中。这将是引擎本身的延伸。

那就是 *对象* Tex。同样，**一方面，这是一种编程语言，其中包括Virtex的一组原语，并随着新的输出需求施加的新原语言而扩展。另一方面，这是一种扩展的Tex发动机，也了解新的原语。而且，第三方，Object Tex是一个整体的新排版系统。**

有第四只手。对象TEX格式也是基于平原TEX的格式，其中包含涉及新原始词的定义，例如将默认值分配给媒体指标。

## Aspose.TeX

aspose.tex只是对象Tex系统的API。

## 为什么新的Tex是对象？

那么，为什么我们在系统的名称中使用“对象”呢？原因是对象TEX引擎的实际输出不是输出格式的文件，而是某些中间 *对象 *模型，然后将其转换为目标格式。