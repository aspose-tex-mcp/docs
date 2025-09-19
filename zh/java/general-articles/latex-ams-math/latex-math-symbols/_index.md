---
translation: true
template: /templates/_template-java.md
linktitle: 乳胶数学符号
title: 9. 数学公式中的符号
weight: 90
url: /java/latex-math-symbols/
keywords: AMS-LATEX，AMSMATH，AMSFONTS，AMSSYMB，乳胶数学Sybol课程，Stmaryrd Package，St Mary Road Font
description: 了解TEX中数学符号的分类，并使用标准Tex(乳胶)和AMSSYMB软件包的命令访问各个类的符号。
lastmod: "2025-06-10"
---

{{<section overview>}}

本文中的表格列出了 AMS-LATEX 软件包提供的各种数学符号，包括访问每个符号的命令。它们还包含由 Allan Jeffrey 和 Jeremy Gibbons 设计的 **St Mary Road** 字体中的补充符号。该软件包扩展了 **Computer Modern** 和 AMS 符号字体集，通常应在 `amssymb` 之外加载，但始终在其之后加载。它为函数式编程、过程代数、领域理论、线性逻辑等领域提供了额外的符号。

表格指示了使用每个符号命令需要加载哪些额外的软件包。命令名称为黑色的符号在标准 LaTeX 中可用。命令名称为蓝色的符号需要加载 `amsmath`、`amssymb` 或 `stmaryrd`。如有必要，将通过标记进行进一步分类：当表格还包含来自其他软件包的符号时，<sup>(*StM*)</sup> 表示来自 `stmaryrd` 的符号； <sup>(*kernel*)</sup> 标记在标准 LaTeX 中可用但只能通过组合两个或多个字形而获得的符号，而在指定的包中存在单个字形；<sup>(*var*)</sup> 标记在[数学字母表标识符](/tex/{{lang.url-fragment}}java/latex-math-fonts/#81-math-alphabet-identifiers) 范围内使用时外观会发生变化的“字母符号”（类型为 `\mathalpha`）。

## 9.1. 乳胶数学符号课

数学符号的主要分类与它们在技术使用中的含义有关。在数学排版中，此分类定义了公式布局。特别是，Tex的数学格式化器根据其数学类调整了每个符号两侧的水平空间。此分类还使一些更细微的区别在于重音和简单符号之间，并将“关系 *符号”的巨大列表分为几个表。

数学的设置将每个符号归入以下类别之一：*普通* (Ord)、*运算符* (Op)、*二元* (Bin)、*关系* (Rel)、*开运算* (Open)、*闭运算* (Close) 或 *标点符号* (Punct)。可以使用命令 `\mathord`、`\mathop`、`\mathbin`、`\mathrel`、`\mathopen`、`\mathopen` 和 `\mathpunct` 明确更改符号的类别。在下一个示例中，`\#` 和 `\top`（默认均为 Ord）被更改为 Rel 和 Op。

```tex
\usepackage[fleqn]{amsmath}
\[ a \# \top _x^\alpha x^\alpha_b \]
\[ a \mathrel{\#} \mathop{\top}_x^\alpha x^\alpha_b \]
```

![明确更改符号类](/tex/images/java/tutorial/latex-ams-math-9-1.png)

除了上述类别之外，某些子公式（最重要的是分数以及由 `\left` 和 `\right` 生成的分数）形成一个名为 *Inner* 的类，可通过 `\mathinner` 命令明确使用。

![符号类和间距](/tex/images/java/tutorial/latex-ams-math-9-2.png)

> 表中，“0”表示“无空格”，“1”表示`\thinmuspace`，“2”表示`\medmuskip`，“3”表示`\thickmuskip`，“*”表示“不可能”。粗体表示在数学脚本样式中不添加相应的空格。

TEX仅通过在公式中识别每个对象的类，然后在上一对中的每对相邻对象之间添加空间来处理公式中的间距。该表被硬编码为Tex的数学排版例程，因此无法通过宏软件包更改。

只要没有之前， *二进制 *符号就会变成 *普通 *符号，其后是与二进制操作兼容的自然符号。这就是为什么表中的某些条目被标记为不可能的原因。例如，`$ +x $`给出 +*x*(一个unary plus)，而不是 +*x*。后者可以由`$ {}+x $`产生。

考虑以下公式(更改默认值以更清楚地显示添加的空间)：

```tex
thinmuskip=10mu \medmuskip=17mu \thickmuskip=30mu
% -------------------------------------------------------------------------------
\[
a - b = -\max \{ x , y \}
\]
```

![\ thinmuskip，\ medmuskip和\ chummuskip](/tex/images/java/tutorial/latex-ams-math-9-3.png)

Tex将对象识别为ORD，BIN，ORD等，然后插入以下空间：

```
 A      -      b      =      -    \max   \{   x    ,       y   \}
Ord \: Bin \: Ord \; Rel \; Ord \, Op   Open Ord Punct \, Ord Close
```

“ \ max”前面的减去变成了 *普通 *，因为 *二进制 *无法遵循 *关系 *。

在“`\left...\right`”结构中，由该结构分隔的整个子公式将变成一个属于“*Inner*”类的单个对象。相比之下，“`\Bigl`”和“`\Bigr`”等命令分别生成属于“*Opening*”和“*Closing*”类的单个符号。它们之间的区别如上图的间距表所示。虽然它们可能产生垂直方向大小相等的分隔符，但根据公式中相邻对象的不同，可能会出现间距差异。例如，*Ordinary* 后跟 *Opening* 时没有空格，而 *Ordinary* 后跟 *Inner* 时则由一个较窄的空格分隔。“`\left...\right`”结构中子公式内的空格按预期生成，以 *Opening* 符号开头，以 *Closing* 符号结尾。


```tex
\thinmuskip=10mu \medmuskip=17mu \thickmuskip=30mu
% -------------------------------------------------------------------------------
\[ a \Bigl( \sum x \Bigr) \neq a \left( \sum x \right) \]
```

![\左... \右和\ bigl ... \ bigr](/tex/images/java/tutorial/latex-ams-math-9-4.png)

总而言之，最好检查一个符号是否属于所需类别，而不仅仅是在随后的表中查找它。

## 9.2. 字母，数字和其他 *普通 *符号

未重新的ASCII拉丁字母和阿拉伯数字数字都称为“字母符号”。他们输入的字体可以有所不同。在数学公式中，拉丁字母的默认字体是斜体的，而对于阿拉伯数字，它是直立的/罗马的。字母顺序的符号都是班级 *普通 *。

![类的符号\ Mathord(希腊语)](/tex/images/java/tutorial/latex-ams-math-9-5.png)

与拉丁字母不同，数学希腊字母不再与用于排版正常希腊文本的字形密切相关。由于奇怪的18世纪的偶然性，在欧洲的主要数学排版传统中，数学公式中小写字母的默认字体是斜体是斜体的，而对于大写的希腊字母，它是直立的/罗马。 (例如，在物理和化学中，印刷传统略有不同。)

下表的第一行中的资本希腊字母也是字母符号，其字体各不相同，默认值为正直/罗马。有资本希腊字母，每个字母的外观与某些拉丁字母相同(例如 *a *an *and *alpha *， *b *and *beta *， *k *and *kappa *， *o *o *and *omicron *)。这些字母不存在于表中。出于同样的原因，没有小写的Omicron。在实践中，看起来像拉丁字母的希腊字母在数学公式中不使用。

![希腊字母](/tex/images/java/tutorial/latex-ams-math-9-6.png)

> 蓝色符号需要 `amssymb` 包。<sup>(*var*)</sup> 表示变量字母符号。

下表列出了其他字母形的符号 *普通 *。前四个是希伯来语字母。

![类的符号\ Mathord(字母形)](/tex/images/java/tutorial/latex-ams-math-9-7.png)

> 蓝色符号需要“amssymb”包。

下表列出了 *普通 *类中的其余符号，包括一些常见的标点符号。这些行为像字母和数字一样，因此它们在周围永远不会有任何额外的空间。

![\ Mathord类的符号(其他)](/tex/images/java/tutorial/latex-ams-math-9-8.png)

> 蓝色符号需要 `amssymb` 包，或者如果标有 <sup>(*StM*)</sup>，则需要 `stmaryrd` 包。

> 请注意，感叹号、句号和问号在公式中不被视为标点符号。

> 同义词：逻辑否定 - `\lnot`、`\neg`；`|` - `\vert`、`|`；`||` - `\Vert`、`\|`。

一个常见的错误是将这些符号直接用作 *二进制 * operation或 *关系 *符号，而无需使用该类型的正确定义的数学符号命令。因此，如果您使用'\＃`，`\ square'或`\＆'之类的命令，请仔细检查您获得正确的符号间空间，或者更好地定义自己的符号命令。

```tex
\usepackage[fleqn]{amsmath} \usepackage{amssymb}
\DeclareMathSymbol\bneg {\mathbin}{symbols}{"3A}
\DeclareMathSymbol\rsquare{\mathrel}{AMSa}{"03}
% -------------------------------------------------------------------------------
\[ a \neg b \qquad x \square y + z \]
\[ a \mathbin{\neg} b \qquad x \mathrel{\square} y + z \]
\[ a \bneg b \qquad x \rsquare y + z \]
```

![声明数学符号](/tex/images/java/tutorial/latex-ams-math-9-9.png)

`\declaremathsymbol`命令用于声明您自己的符号名称。

```tex
\DeclareMathSymbol{cmd}{type}{symbol-font}{slot}
```

第一个参数是您选择的命令名称。第二个参数是与符号类对应的命令之一。第三个参数标识应从中获取符号的符号字体。第四个参数给出符号在字体编码中的位置，可以是十进制、八进制或十六进制值。通过查看文件`amssymb.sty`或`fontmath.ltx`（针对核心符号）中的定义，可以最轻松地找到参数的正确值。例如，我们查找了`\neq`和`\square`，并在每种情况下替换了`\mathord`，最后为生成的符号赋予了新名称。

## 9.3. 数学口音

下表列出了公式中可用的重音命令。其中大多数是在标准Tex中定义的。有关可扩展口音的信息，请参见[此处](/tex/{{lang.url-fragment}}java/latex-math-extensible-symbols/#52-symbols-that-are-horizontally-extensible)。当您在符号中添加数学重音时，结果是类 *普通 *的符号。

![数学重音，给出类\ Mathord的子形式](/tex/images/java/tutorial/latex-ams-math-9-10.png)

> 蓝色重音符号需要 `amsmath` 软件包。

> 最后两个重音符号有多种宽度可供选择，系统会自动使用最合适的宽度。

```tex
\usepackage{amstext}
% -------------------------------------------------------------------------------
\[ a = b \text{ but } a \tilde{=} b
\text{ which is not } a \mathrel{\tilde{=}} b \]
```

![从重音符号中制作一个关系符号](/tex/images/java/tutorial/latex-ams-math-9-11.png)

在“关系”符号上放置符号的其他方法请参见[此处](/tex/{{lang.url-fragment}}java/latex-math-decorations/#47-other-decorations)。在数学公式中为“i”或“j”添加重音符号时，最好使用无点变体`\imath`和`\jmath`。

## 9.4.  *二进制*操作员符号

可以从中选择的类 *二进制 *的100多个符号。其中大多数在下表中列出。其中一些也可作为 *关系 *符号可用，尽管以不同的名称。

![类\ Mathbin的符号(其他)](/tex/images/java/tutorial/latex-ams-math-9-12.png)

> 蓝色符号需要 `amssymb` 包，或者如果标记为 <sup>(*StM*)</sup>，则需要 `stmaryrd` 包。

> 左三角形和右三角形也可用作 *关系* 符号。

> `stmaryrd` 包令人困惑地将 *二元* 符号 `\bigtriangleup` 和 `\bigtriangledown` 更改为 *运算符*，而 *二元* 运算符形式仅保留同义词 `\varbigtriangleup` 和 `\varbigtriangledown`。

`amssymb`软件包提供了几个盒子符号，可用作 *二进制 *操作员； ``stmaryrd''添加了更多。请参阅下表。

![类\ Mathbin的符号(盒子)](/tex/images/java/tutorial/latex-ams-math-9-13.png)

> 所有符号都需要 `amssymb` 包，或者如果用 <sup>(*StM*)</sup> 标记，则需要 `stmaryrd` 包。

您可以使用选项`heavycircles`加载`stmaryrd`包。这样，下一个表中每个以`\var`开头的圆形符号命令都会与不带`var`的相应命令交换其定义；例如，符号`\varodot`变为`\odot`，反之亦然。

![\ Mathbin类的符号(圆圈)](/tex/images/java/tutorial/latex-ams-math-9-14.png)

> 蓝色符号需要 `amssymb` 包，或者如果标有 <sup>(*StM*)</sup>，则需要 `stmaryrd` 包。

> `stmaryrd` 包的 `heavycircles` 选项会影响所有以 `\var` 开头的命令及其常规变体。

## 9.5. 关系符号

二进制 *关系 *符号的类别甚至大于 *二进制 *运算符的符号。下表列出了平等和顺序的符号。通过使用`\ not'命令将斜杠通过任何 *关系 *符号放在任何 *关系 *符号中。否定的符号代表关系的补充(或否定)。

![类\ Mathrel的符号(平等和顺序)](/tex/images/java/tutorial/latex-ams-math-9-15.png)

> 蓝色符号需要 `amssymb` 包，或者如果标记为 <sup>(*StM*)</sup>，则需要 `stmaryrd` 包。

```tex
$ u \not< v$ or $a \not\in \mathbf{A} $
```

![否定关系](/tex/images/java/tutorial/latex-ams-math-9-16.png)

这种否定 *关系 *符号的通用方法并不总是给出良好的结果，尤其是在较大的符号中，因为斜线始终具有相同的大小，位置和斜率。由于这个事实，也可以使用一些专门设计的“否定符号”。请参阅下表中的列表。

![类\ Mathrel的符号(平等和秩序已死)](/tex/images/java/tutorial/latex-ams-math-9-17.png)

> 蓝色符号需要`amssymb`包。

如果有选择，通常最好使用专门设计的字形。要查看原因，请在下一个示例中比较符号。

```tex
\usepackage{amssymb}
% -------------------------------------------------------------------------------
$ \not\leq \ \not\succeq \ \not\sim $ \par
$ \nleq \ \nsucceq \ \nsim $
```

![化合物和专门设计的否定关系符号](/tex/images/java/tutorial/latex-ams-math-9-18.png)

下表列出了集合和包含的 *关系 *符号。

![类\ Mathrel的符号(集合和包容)](/tex/images/java/tutorial/latex-ams-math-9-19.png)

> 蓝色符号需要 `amssymb` 包，或者如果用 <sup>(*StM*)</sup> 标记，则需要 `stmaryrd` 包。

现在，对集合和包含的 *关系 *符号的否定。

![类\ Mathrel的符号(集合和包含在内)](/tex/images/java/tutorial/latex-ams-math-9-20.png)

> 蓝色符号需要`amssymb`包。

下表列出了箭头形 *关系 *符号。描述了一些产生复合 *关系 *符号的可扩展箭头构造[此处](/tex/{{lang.url-fragment}}java/latex-math-extensible-symbols/#52-symbols-that-are-horizontally-extensible)。

![类的符号\ Mathrel(箭头)](/tex/images/java/tutorial/latex-ams-math-9-21.png)

> 蓝色符号需要 `amssymb` 包，或者如果用 <sup>(*StM*)</sup> 标记，则需要 `stmaryrd` 包。

这是否定的箭头 *关系 *符号。

![\ Mathrel类的符号(箭头已接管)](/tex/images/java/tutorial/latex-ams-math-9-22.png)

> 蓝色符号需要`amssymb`包。

还有其他元素(除了``\''不用于否定一般 *关系 *符号)，这些元素是专门设计的，这些元素是为否定或扩展类似箭头的符号而设计的。请参阅下表。

![\ Mathrel类的符号(否定和箭头扩展))](/tex/images/java/tutorial/latex-ams-math-9-23.png)

> 蓝色符号需要 `stmaryrd` 包。

> 这些符号用于组合，主要与箭头一起使用；例如 `\longarrownot\l​​ongleftarrow`。

> 使用 `\joinrel` 将关系符号“粘合”在一起，例如 `\lhook\joinrel\longrightarrow`。

> 这些符号的尺寸使其不适合用于其他用途。

```tex
\usepackage{stmaryrd}
% -------------------------------------------------------------------------------
$\Longarrownot\longleftrightarrow \qquad \arrownot \hookleftarrow$
```

![箭头否定](/tex/images/java/tutorial/latex-ams-math-9-24.png)

最后，下面是其他其他 *关系 *符号。

![\ Mathrel类的符号(其他)))))](/tex/images/java/tutorial/latex-ams-math-9-25.png)

> 蓝色的 *关系* 符号需要 `amssymb` 包。

> `\therefore` 是一个 *关系* 符号，因此其间距在常见用途中可能与预期不同。
