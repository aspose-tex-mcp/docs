---
translation: true
template: /templates/_template-java.md
linktitle: 底层接口
title: 5. 底层接口
weight: 50
url: /java/latex-fonts-low-level/
keywords: LaTeX、LaTeX字体、LaTeX字体替换、LaTeX字体系列、LaTeX字体形状
description: 本文介绍了LaTeX底层字体接口，该接口主要用于命令定义中。
lastmod: "2026-02-28"
---

{{<section overview>}}

与面向文档使用的高级字体命令不同，低级字体命令主要用于在宏包或文档前言中定义新命令。若要充分利用这些命令，了解 LaTeX 字体选择方案（NFSS）内部的组织结构会非常有帮助。

一方面，LaTeX 的字体选择方案旨在通过遵循通用标记原则的算法，实现理性化的字体选择。为此，理想状态下应尽可能让尽可能多的字体属性能够独立更改。另一方面，实际的字体族往往只包含属性组合的一个子集。因此，若让过多属性独立变化，会产生大量不存在对应外部字体的组合，必须使用默认字体进行替代。

在内部，LaTeX 跟踪五个独立的字体属性：*当前编码*、*当前族*、*当前系列*、*当前形状*以及*当前尺寸*。编码属性是在 NFSS 2 版引入的，当时人们意识到如果不把字符编码方案独立于其他字体属性，就无法支持多语言。

这些属性的取值决定了当前使用的字体。LaTeX 还维护了一套大型表格，用于将属性组合关联到外部字体（即 `.tfm` 文件，包含 LaTeX 工作所需的数据）。字体选择分两步完成：

1. 使用低级命令 `\fontencoding`、`\fontfamily`、`\fontseries`、`\fontshape` 和 `\fontsize` 更改若干字体属性。

2. 通过调用 `\selectfont` 命令选择对应上述新属性设置的字体。

第二步涉及多个操作。首先，LaTeX 检查系统中是否已知（即已加载）对应属性设置的字体（`.tfm` 文件），若已知则直接选择该字体。否则，搜索内部表格以寻找与这些设置关联的外部字体名。如果找到该字体名，则读取相应的 `.tfm` 文件到内存，并选定该字体用于排版；若未找到，则如后文所述，LaTeX 会尝试寻找替代字体。

## 5.1. 设置单个字体属性

每个字体属性都有一个对应的命令用于更改其当前值。这些命令接受几乎任意字符字符串作为参数，但只有少数值是有意义的。这些值并未硬编码在 NFSS 中，而是作为内部表格中的约定。下面的章节介绍标准 LaTeX 设置中使用的命名约定，任何人都可以通过在内部表格中添加新的字体声明来修改这些约定。通常情况下，设置新字体时应尽量遵守这些约定，因为只有一致的命名约定才能保证在通用标记文档中正确选择合适的字体。

如果你想使用该接口选择特定字体——例如 **Computer Modern Dunhill bold condensed italic 14pt**——仅了解接口约定是不够的，因为并非每种属性组合都有对应的外部字体。你可以尝试如下写法：

```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{bc}\fontshape{it}%
\fontsize{14}{16pt}\selectfont
```

根据命名约定，这段代码是正确的。不过，由于该属性组合并不对应真实的字体，LaTeX 必须进行替代。替代机制可能会选择与所需字体差别很大的字体，因此你应查阅字体表以确认所需组合是否可用。更多细节请参见 [font substitution process](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/#53-automatic-substitution-of-fonts)。

### 选择字体族

字体族通过 `\fontfamily` 命令选择。其参数是指向内部表格中已声明字体族的字符字符串。该字符串在建立表格时定义，通常是一个简短的字母序列——例如，Computer Modern Roman 家族对应 `cmr`。族名不应超过五个字母，因为它们会与最多三个字母组合形成文件名，而某些系统的文件名最长只能有八个字符。

### 选择字体系列

`\fontseries` 命令更改系列属性。系列在参数中同时包含字重（weight）和字宽（width），这意味着无法独立更改当前字体的宽度而不影响字重。这是可以接受的，因为几乎不需要单独更改字重或字宽。相反，设计者往往同时修改字重和字宽。字重的变化会影响字母的水平外观，从而需要相应地调整扩展（宽度）以保持视觉平衡。

系列名称采用缩写形式，使每种组合唯一。下表展示了这些命名约定。出现 `m`（代表中等字重或宽度）时会省略，除非字重和宽度同时为中等，此时使用单个 `m`。例如，粗体宽展为 `bx`，中等宽展为 `x`，粗体中等为 `b`。

![Font series naming conventions](/tex/images/java/tutorial/latex-font-selection-5-1.png)

### 选择字体形状

`\fontshape` 命令更改形状属性。标准形状使用一到两个字母的缩写表示。下表列出了这些形状：

![Font shapes naming conventions](/tex/images/java/tutorial/latex-font-selection-5-2.png)

### 选择字体尺寸

`\fontsize{<size>}{<skip>}` 命令更改字体尺寸。它接受两个参数：要切换到的 `<size>` 与基线 `<skip>`（该尺寸的行距）。字体尺寸通常以点 (pt) 为单位，约定上不写单位，第二个参数同理。但如果基线距需要弹性长度，则必须写出单位。例如：

```tex
\fontsize{14.4}{17}\selectfont
```

即使此请求有效，仍可能没有对应尺寸的外部字体。若如此，LaTeX 会尝试在内部表格允许的情况下进行尺寸校正，或报错。

如果你使用任意尺寸的字体，当然可以随意指定尺寸：

```tex
\fontsize{1in}{1.2in}\selectfont A text in an arbitrary font size
```

### 选择编码

`\fontencoding` 命令用于更改编码。参数是所需编码的内部名称。该名称必须为 LaTeX 所认识，既可以是内核预加载的预定义编码，也可以是使用 `\DeclareFontEncoding` 声明的自定义编码。更多信息请参见 [declaring font encodings](/tex/{{lang.url-fragment}}java/latex-fonts-setup/#64-how-to-declare-a-new-font-encoding-scheme)。标准字体编码名称列于下表：

![Standard font encoding names](/tex/images/java/tutorial/latex-font-selection-5-3.png)

NFSS 假设大多数（或更确切地说，全部）文本字体在相同语言下使用相同编码即可。换言之，只有在切换语言时才需要更改编码。在这种情况下，语言支持宏包（例如 `babel` 系统）通常会自动处理编码切换。

下面的示例手动更改编码，定义了一个用于西里尔文排版的环境 `Cyr`。在该环境中，字体编码和输入编码都会局部更改。实际的语言支持还需要额外工作，如修改断字规则。我们通过加载 `fontenc` 宏包来声明这些编码，`T2A` 为标准西里尔编码之一，`T1` 因为最后加载而成为默认编码。

![Encondings exmple source code](/tex/images/java/tutorial/latex-font-selection-5-4.png)

![Encondings exmple output](/tex/images/java/tutorial/latex-font-selection-5-5.png)

不幸的是，大多数 PostScript 字体无法完整实现 `T1` 编码。下面示例中的五个字符可能会显示为墨点，表明相应字形缺失。值得注意的是，“千分号”和“万分号”实际上是通过组合百分号和一个或两个小的零构成的；仅后者的字形缺失。

```tex
\usepackage[T1]{fontenc}
-----------------------------------------
\fontfamily{cmr}\selectfont
\j{} \ng{} \NG{} \textperthousand{}\textpertenthousand \par
\fontfamily{ptm}\selectfont
\j{} \ng{} \NG{} \textperthousand{}\textpertenthousand{}
```

![T1 for PostScript fonts](/tex/images/java/tutorial/latex-font-selection-5-5.png)

## 5.2. 同时设置多个字体属性

在设计页面样式或面向布局的命令时，通常需要一次性指定所有属性。这时可以使用 `\usefont` 命令，它接受四个参数：编码、族、系列和形状。该命令会更新这些属性并随后调用 `\selectfont`。如果还想指定尺寸和基线距，可在 `\usefont` 前放置 `\fontsize` 命令。例如：

```tex
\fontsize{14}{16pt}\usefont{OT1}{cmdh}{bc}{it}
```

将产生与以下命令相同的效果：

```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{bc}\fontshape{it}%
\fontsize{14}{16pt}\selectfont
```

LaTeX 还提供 `\DeclareFixedFont` 声明，可用于定义切换到完全固定字体的新命令。这类命令非常快，因为不需要查找内部表格。它们在需要频繁在不同字体之间切换的宏定义中尤为有用。例如，若想声明一个用于排版脚本尺寸文本的命令，可如下操作：

```tex
\DeclareFixedFont\ScriptSizeFont{\encodingdefault}{\familydefault}
    {\seriesdefault}{\shapedefault}{7pt}
\newcommand\theScript[1]{{\ScriptSizeFont #1}}
```

`\DeclareFixedFont` 共有六个参数。要定义的命令名后跟 NFSS 分类的五个字体属性。除尺寸外，使用的是描述主文档字体的内建钩子。因此，上例中的 `\ScriptSizeFont` 仍然依赖文档的整体布局。但一旦定义执行完毕，其含义即被冻结，后续对默认值的更改不会影响 `\ScriptSizeFont`。

## 5.3. 字体的自动替代

当字体更改请求因组合未被 LaTeX 认识而无法完成时，LaTeX 会尝试使用属性相近的字体进行恢复。具体过程如下：如果编码、族、系列、形状的组合未声明，LaTeX 首先将形状属性改为默认值并尝试匹配；若仍未找到，则将系列改为默认；最后将族改为默认。随后在内部表格中查找对应尺寸。例如，若请求 `\ttfamily\bfseries\itshape`（等宽字体、粗体、斜体——通常不存在），LaTeX 会先重置形状为直立，再重置系列为中等，最终得到等宽、普通粗细、直立的字体。如果你希望保留斜体形状，需要使用 `sub` 函数在 [How to set up new fonts](/tex/{{lang.url-fragment}}java/latex-fonts-setup/) 文章中所述的方法向 LaTeX 声明偏好。

替代过程永远不会更改编码方案，因为任何更改都可能导致输出字符错误。正如之前提到的，编码方案决定了如何解释输入字符，而其他属性决定输出的外观。因此，不能因为软件“聪明”而在合同中把英镑符号替换成美元符号。

因此，每种编码方案必须拥有默认的族、系列和形状，并且该编码连同其默认值的组合必须在 LaTeX 中有相应的定义。

## 5.4. 在文档中使用低级命令

前述章节介绍的低级命令主要用于在高层命令的定义中（无论是在文档类、宏包文件还是文档前言中）使用。

如果可以使用高级命令（如 `\textsf`），应尽量避免在文档中直接使用低级命令。原因在于低级命令会精确地切换到特定字体，而高级命令可以通过宏包或前言中的声明进行定制。例如，你已经通过 `\fontfamily{cmss}\selectfont` 选择了 Computer Modern Sans。如果之后决定将整篇文档切换为 PSNFSS 套件中的字体（如 Times），只需加载相应宏包即可，而不必手动改动所有显式的 `\fontfamily` 调用。
