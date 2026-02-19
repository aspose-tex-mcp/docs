---
translation: true
template: /templates/_template-java.md
linktitle: LaTeX 数学符号
title: 9. 公式中的符号
weight: 90
url: /java/latex-math-symbols/
keywords: ams-latex、amsmath、amsfonts、amssymb、latex 数学符号类、stmaryrd 包、圣玛丽路字体
description: 学习 TeX 中数学符号的分类，并使用标准 TeX（LaTeX）和 amssymb 包的命令访问各种类的符号。
lastmod: "2026-02-19"
---

{{<section overview>}}

本文中的表格列出了 AMS‑LATEX 包提供的大量数学符号，并给出访问每个符号的命令。它们还包括由 Allan Jeffrey 和 Jeremy Gibbons 设计的 **St Mary Road** 字体的补充符号。该字体扩展了 **Computer Modern** 和 AMS 符号字体集合，通常需要在加载 `amssymb` 之后再加载它。它为函数式编程、过程代数、领域理论、线性逻辑等诸多领域提供了额外的符号。

表格会标注使用每个符号命令需要额外加载的包。命令名称为黑色的符号在标准 LaTeX 中可用。命令名称为蓝色的符号需要加载 `amsmath`、`amssymb` 或 `stmaryrd` 中的任意一个。如果必要，进一步的分类通过标记给出：<sup>(*StM*)</sup> 表示该符号来自 `stmaryrd`（当表格中还包含其他包的符号时）；<sup>(*kernel*)</sup> 标记在标准 LaTeX 中只能通过组合两个或多个字形得到的符号，而在所指包中则有单独的字形；<sup>(*var*)</sup> 标记“字母符号”（`\mathalpha` 类型），在使用 [math alphabet identifier](/tex/{{lang.url-fragment}}java/latex-math-fonts/#81-math-alphabet-identifiers) 时会改变外观。

## 9.1. LaTeX 数学符号类别

数学符号的主要分类与其在技术使用中的含义相关。在数学排版中，这一分类决定了公式的布局。特别是，TeX 的数学格式化程序会根据每个符号的数学类别在其两侧添加水平间距。该分类还会做更细的区分，例如在重音符号和普通符号之间，以及把庞大的 *Relation* 符号列表拆分成若干表格。

数学排版的设置将每个符号放入以下七类之一：*普通*（Ord），*运算符*（Op），*二元*（Bin），*关系*（Rel），*左括*（Open），*右括*（Close）或*标点*（Punct）。可以使用命令 `\mathord`、`\mathop`、`\mathbin`、`\mathrel`、`\mathopen`、`\mathopen`（应为 `\mathclose`）和 `\mathpunct` 显式改变符号的类别。在下例中，`\#` 和 `\top`（默认都是 Ord）被改为 Rel 和 Op。

```tex
\usepackage[fleqn]{amsmath}
\[ a \# \top _x^\alpha x^\alpha_b \]
\[ a \mathrel{\#} \mathop{\top}_x^\alpha x^\alpha_b \]
```

![Explicitly changing the symbol class](/tex/images/java/tutorial/latex-ams-math-9-1.png)

除了上述类别之外，某些子公式——尤其是分式以及由 `\left` 和 `\right` 产生的子公式——会形成一个称为 *Inner* 的类别，可通过 `\mathinner` 命令显式使用。

![Symbol classes and spacing](/tex/images/java/tutorial/latex-ams-math-9-2.png)

> 在表格中，"0" 表示“无间距”，"1" 表示 `\thinmuskip`，"2" 表示 `\medmuskip`，"3" 表示 `\thickmuskip`，"*” 表示“不可能”。粗体条目意味着对应的间距在数学脚本样式中不会被添加。

TeX 通过识别公式中每个对象的类别来处理间距，并依据前表在相邻对象之间添加相应的间距。此表已硬编码在 TeX 的数学排版例程中，宏包无法更改它。

当二元符号前后没有兼容的二元操作符时，它会被视为 *普通* 符号。这就是为什么表格中有些条目标记为“不可能”。例如，`$+x`（一元加号）而不是 `+$ x`。后者可以通过 `${}+x` 来产生。

### 示例：显示间距差异

考虑下面的公式（为了更清晰地显示添加的间距，已更改默认值）：

```tex
thinmuskip=10mu \medmuskip=17mu \thickmuskip=30mu
% -------------------------------------------------------------------------------
\[
a - b = -\max \{ x , y \}
\]
```

![\thinmuskip, \medmuskip, and \thickmuskip](/tex/images/java/tutorial/latex-ams-math-9-3.png)

TeX 将对象识别为 Ord、Bin、Ord 等，然后按如下方式插入间距：

```
 A      -      b      =      -    \max   \{   x    ,       y   \}
Ord \: Bin \: Ord \; Rel \; Ord \, Op   Open Ord Punct \, Ord Close
```

`\max` 前的负号被视为 *普通*，因为 *二元* 不能跟在 *关系* 后面。

在 `\left...\right` 构造中，整个由该构造限定的子公式会成为单一的 *Inner* 类对象。相比之下，`\Bigl` 和 `\Bigr` 等命令会产生分别属于 *Opening* 和 *Closing* 类的单独符号。它们在上表中的间距差异便可体现出来。虽然它们可能产生相同垂直尺寸的定界符，但根据公式中相邻对象的不同，间距会有所差别。例如，*普通* 后接 *Opening* 不产生间距，而 *普通* 后接 *Inner* 则会插入一个细间距。`\left...\right` 构造内部的子公式间距如预期般工作，以 *Opening* 符号开始，以 *Closing* 符号结束。

```tex
\thinmuskip=10mu \medmuskip=17mu \thickmuskip=30mu
% -------------------------------------------------------------------------------
\[ a \Bigl( \sum x \Bigr) \neq a \left( \sum x \right) \]
```

![\left...\right and \Bigl...\Bigr](/tex/images/java/tutorial/latex-ams-math-9-4.png)

总之，最好检查符号是否属于期望的类别，而不是仅仅在后面的表格中查找。

## 9.2. 字母、数字以及其他 *普通* 符号

未加重音的 ASCII 拉丁字母和阿拉伯数字统称为“字母符号”。它们的字体可以变化。在数学公式中，默认的拉丁字母使用斜体，而阿拉伯数字使用正体（Roman）。所有字母符号均属于 *普通* 类。

![Symbols of class \mathord (Greek)](/tex/images/java/tutorial/latex-ams-math-9-5.png)

与拉丁字母不同，数学中的希腊字母不再与用于排版普通希腊文的字形紧密对应。由于 18 世纪的一个偶然原因，在欧洲主流的数学排版传统中，数学公式中小写希腊字母默认使用斜体，而大写希腊字母使用正体（在物理和化学中，传统略有不同）。

下面表格第一行的希腊大写字母同样是字体可变的字母符号，默认使用正体。表中未列出与某些拉丁字母同形的大写希腊字母（例如 *A* 与 *Alpha*，*B* 与 *Beta*，*K* 与 *Kappa*，*O* 与 *Omicron*），因为它们在表中未出现。出于相同原因，表中也没有小写的 omicron。实践中，这类形似拉丁字母的希腊字母很少用于数学公式。

![Greek letters](/tex/images/java/tutorial/latex-ams-math-9-6.png)

> 蓝色符号需要 `amssymb` 包。<sup>(*var*)</sup> 表示可变的字母符号。

下表列出其他字母形状的 *普通* 符号，前四项是希伯来字母。

![Symbols of class \mathord (letter-shaped)](/tex/images/java/tutorial/latex-ams-math-9-7.png)

> 蓝色符号需要 `amssymb` 包。

随后表格列出其余的 *普通* 类符号，包括一些常见的标点。这些符号的行为类似字母和数字，因而在它们周围不会产生额外的间距。

![Symbols of class \mathord (miscellaneous)](/tex/images/java/tutorial/latex-ams-math-9-8.png)

> 蓝色符号需要 `amssymb` 包或（若标记有 <sup>(*StM*)</sup>）`stmaryrd` 包。

> 请注意感叹号、句点和问号在公式中不被视为标点。

> 同义词：逻辑非 – `\lnot`, `\neg`；`|` – `\vert`, `|`；`||` – `\Vert`, `\|`。

一个常见错误是直接将这些符号用作 *二元* 运算符或 *关系* 符号，而未使用相应的数学符号命令。因此，如果使用 `\#`、`\square` 或 `\&` 等命令，请仔细检查它们产生的符号间距，或更好地自行定义符号命令。

```tex
\usepackage[fleqn]{amsmath} \usepackage{amssymb}
\DeclareMathSymbol\bneg {\mathbin}{symbols}{"3A}
\DeclareMathSymbol\rsquare{\mathrel}{AMSa}{"03}
% -------------------------------------------------------------------------------
\[ a \neg b \qquad x \square y + z \]
\[ a \mathbin{\neg} b \qquad x \mathrel{\square} y + z \]
\[ a \bneg b \qquad x \rsquare y + z \]
```

![Declaring math symbols](/tex/images/java/tutorial/latex-ams-math-9-9.png)

`\DeclareMathSymbol` 命令用于声明自定义符号名称。

```tex
\DeclareMathSymbol{cmd}{type}{symbol-font}{slot}
```

第一个参数是你选择的命令名称。第二个参数是表示符号类别的命令之一。第三个参数指明符号应当取自哪个符号字体。第四个参数给出符号在该字体编码中的位置，可以是十进制、八进制或十六进制值。最容易获得这些值的方法是查阅 `amssymb.sty` 或 `fontmath.ltx`（核心符号）的定义。例如，我们查找了 `\neq` 与 `\square`，将其中的 `\mathord` 替换为相应的类别，并最终为新符号赋予新的名称。

## 9.3. 数学重音符

下表列出公式中可用的重音命令。大多数定义在标准 TeX 中。有关可水平伸展的重音，请参见 [这里](/tex/{{lang.url-fragment}}java/latex-math-extensible-symbols/#52-symbols-that-are-horizontally-extensible)。当你给符号添加重音时，结果将是 *普通* 类符号。

![Mathematical accents, giving sub-formulas of class \mathord](/tex/images/java/tutorial/latex-ams-math-9-10.png)

> 蓝色符号需要 `amsmath` 包。

> 最后两个重音提供多种宽度，系统会自动选取最合适的最大宽度。

```tex
\usepackage{amstext}
% -------------------------------------------------------------------------------
\[ a = b \text{ but } a \tilde{=} b
\text{ which is not } a \mathrel{\tilde{=}} b \]
```

![Making a Relation symbol from an accented symbol](/tex/images/java/tutorial/latex-ams-math-9-11.png)

其他在 *关系* 符号上放置符号的方法请参见 [这里](/tex/{{lang.url-fragment}}java/latex-math-decorations/#47-other-decorations)。在对 *i* 或 *j* 加重音时，最好使用无点形式的 `\imath` 与 `\jmath`。

## 9.4. *二元* 运算符符号

二元类符号超过 100 个，以下表格列出其中的大部分。有些符号也可作为 *关系* 符号使用，只是名称不同。

![Symbols of class \mathbin (miscellaneous)](/tex/images/java/tutorial/latex-ams-math-9-12.png)

> 蓝色符号需要 `amssymb` 包或（若标记有 <sup>(*StM*)</sup>）`stmaryrd` 包。

> 左右三角形同样也可作为 *关系* 符号使用。

> `stmaryrd` 包把二元符号 `\bigtriangleup` 与 `\bigtriangledown` 改为 *运算符*，仅保留 `\varbigtriangleup` 与 `\varbigtriangledown` 作为二元运算符形式。

`amssymb` 包提供了一些可作二元运算符的盒子符号，`stmaryrd` 则增加了更多。请参见下表。

![Symbols of class \mathbin (boxes)](/tex/images/java/tutorial/latex-ams-math-9-13.png)

> 所有符号均需要 `amssymb` 包或（若标记有 <sup>(*StM*)</sup>）`stmaryrd` 包。

加载 `stmaryrd` 包时可以使用 `heavycircles` 选项。结果是，下表中以 `\var` 开头的每个圆形符号的定义会与对应的非 `\var` 版本互换，例如 `\varodot` 变为 `\odot`，反之亦然。

![Symbols of class \mathbin (circles)](/tex/images/java/tutorial/latex-ams-math-9-14.png)

> 蓝色符号需要 `amssymb` 包或（若标记有 <sup>(*StM*)</sup>）`stmaryrd` 包。

> `stmaryrd` 包的 `heavycircles` 选项会影响所有以 `\var` 开头的命令及其普通变体。

## 9.5. 关系符号

二元 *关系* 符号的数量甚至超过 *二元* 运算符。下表列出等号和序关系的符号。通过在符号前加 `\not` 可以在任意 *关系* 符号上加斜杠。斜杠表示关系的补集（或否定）。

![Symbols of class \mathrel (equality and order)](/tex/images/java/tutorial/latex-ams-math-9-15.png)

> 蓝色符号需要 `amssymb` 包或（若标记有 <sup>(*StM*)</sup>）`stmaryrd` 包。

```tex
$ u \not< v$ or $a \not\in \mathbf{A} $
```

![Negating a relation](/tex/images/java/tutorial/latex-ams-math-9-16.png)

这种通用的否定方式并不总能得到理想的效果，尤其是对较大的符号，因为斜杠的大小、位置和倾斜角始终相同。为此，还提供了一些专门设计的“否定符号”。请参见下表。

![Symbols of class \mathrel (equality and order‑negated)](/tex/images/java/tutorial/latex-ams-math-9-17.png)

> 蓝色符号需要 `amssymb` 包。

如果有可供选择的符号，通常建议使用专门设计的字形。下面的例子可以说明两者的差异。

```tex
\usepackage{amssymb}
% -------------------------------------------------------------------------------
$ \not\leq \ \not\succeq \ \not\sim $ \par
$ \nleq \ \nsucceq \ \nsim $
```

![Compound and specially designed negated Relation symbols](/tex/images/java/tutorial/latex-ams-math-9-18.png)

下表列出集合与包含关系的 *关系* 符号。

![Symbols of class \mathrel (sets and inclusion)](/tex/images/java/tutorial/latex-ams-math-9-19.png)

> 蓝色符号需要 `amssymb` 包或（若标记有 <sup>(*StM*)</sup>）`stmaryrd` 包。

随后是这些集合与包含关系符号的否定形式。

![Symbols of class \mathrel (sets and inclusion‑negated)](/tex/images/java/tutorial/latex-ams-math-9-20.png)

> 蓝色符号需要 `amssymb` 包。

下表列出箭头形状的 *关系* 符号。一些可伸展的箭头构造会产生复合的 *关系* 符号，详见 [这里](/tex/{{lang.url-fragment}}java/latex-math-extensible-symbols/#52-symbols-that-are-horizontally-extensible)。

![Symbols of class \mathrel (arrows)](/tex/images/java/tutorial/latex-ams-math-9-21.png)

> 蓝色符号需要 `amssymb` 包或（若标记有 <sup>(*StM*)</sup>）`stmaryrd` 包。

下面是这些箭头形状的否定符号。

![Symbols of class \mathrel (arrows‑negated)]/tex/images/java/tutorial/latex-ams-math-9-22.png)

> 蓝色符号需要 `amssymb` 包。

除了使用 `\not` 否定一般的 *关系* 符号之外，还有其他专门设计用于否定或扩展箭头类符号的元素。请参见下表。

![Symbols of class \mathrel (negation and arrow extensions)](/tex/images/java/tutorial/latex-ams-math-9-23.png)

> 蓝色符号需要 `stmaryrd` 包。

> 这些符号主要用于与箭头组合，例如 `\longarrownot\longleftarrow`。

> 使用 `\joinrel` 可以“粘合”关系符号，例如 `\lhook\joinrel\longrightarrow`。

> 这些符号的尺寸通常不适合其他用途。

```tex
\usepackage{stmaryrd}
% -------------------------------------------------------------------------------
$\Longarrownot\longleftrightarrow \qquad \arrownot \hookleftarrow$
```

![Arrow negations](/tex/images/java/tutorial/latex-ams-math-9-24.png)

最后，以下是其他杂项的 *关系* 符号。

![Symbols of class \mathrel (miscellaneous)](/tex/images/java/tutorial/latex-ams-math-9-25.png)

> 蓝色的 *关系* 符号需要 `amssymb` 包。

> `\therefore` 是一个 *关系* 符号，因此在常规使用中其间距可能不符合预期。
