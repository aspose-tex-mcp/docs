---
translation: true
template: /templates/_template-java.md
linktitle: 7. 定义者
title: 定界符|乳胶手册| aspose.tex
weight: 70
url: /java/latex-math-delimiters/
keywords: 乳胶，乳胶数学公式，乳胶数学，乳胶数学分配器，乳胶数学括号，乳胶数学括号，乳胶数学括号
description: 本文讨论了如何用不同种类的定系数将逻辑公式分为副形式。
lastmod: "2025-06-10"
---

{{<section overview>}}

无论是数学公式的大型公式，Tex都知道一种使一些符号足够大以具有适当外观的方法。例如，键入的结果

```tex
$$\sqrt{1+\sqrt{1+\sqrt{1+
            \sqrt{1+\sqrt{1+\sqrt{1+\sqrt{1+x}}}}}}}$$
```

显示各种可用的自由基或平方根的标志：

![不同尺寸的自由基](/tex/images/java/tutorial/latex-math-7-1.png)

这里的三个最大符号是相同的，除了垂直段，该部分会根据需要重复多次以达到所需的尺寸。同时，较小的标志是从Tex的数学字体中获取的不同字符。

括号和其他所谓的“定界符”符号也会发生类似的事情。这些符号在数学中很重要，因为它们为复杂表达式的基本结构提供了视觉线索。换句话说，它们限制了单个子形成的边界。这是乳胶提供的22个基本定系数的列表：

![乳胶中定义的22个基本定系数](/tex/images/java/tutorial/latex-math-7-2.png)

为了获得这些符号中任何一个稍大的版本，只需键入`\bigl`或`\bigr`即可打开或关闭定界数。这使得带有嵌套定界符的公式更容易阅读：

![使用\ big分界符的示例](/tex/images/java/tutorial/latex-math-7-3.png)

`\big`定界符比普通的定系数足够大，因此可以注意到差异，但足够小，可以在段落的文本中使用：

![与普通的分界符相比](/tex/images/java/tutorial/latex-math-7-4.png)

如果您键入`\bigl`和`\bigr`而不是`\bigl`和`\bigr`：`\ bigr`：''：

![\大分界符](/tex/images/java/tutorial/latex-math-7-5.png)

这些比上一步中的版本高50％。显示的公式经常使用更高的定界器(大小的两倍)。您可以通过键入`\biggl`和`\biggr'来获得它们：

![\ bigg分界符](/tex/images/java/tutorial/latex-math-7-6.png)

最后，您可以键入`\biggl`和`\biggr`版本，是`\ bigl`和`\bigr`定界器的高2.5倍：

![\ bigg分界符](/tex/images/java/tutorial/latex-math-7-7.png)

乳胶还提供`\bigm`，`\bigm`，`\biggm`和`\biggm`命令来产生可用于公式中间的定界器。这样的定界符就像一个关系一样，因此Tex在其两侧都放了一点空间：

![公式中间的定界符](/tex/images/java/tutorial/latex-math-7-8.png)

也可以说`\big`，`\big`，`\bigm`或`\bigg`生成一个类似于普通变量的定界符。这些命令主要将用于斜线和反斜线：

![大普通符号](/tex/images/java/tutorial/latex-math-7-9.png)

Tex实施了一种算法，该算法要弄清一对定界符需要，以封闭给定的子形式。您可以使用它，而不是确定定界符是否应为`\big`或`\bigg`或其他。只是说


```tex
\left<delim1><subformula>\right<delim2>
```

Tex将排版一个子形式，将指定的定系数放在左侧和右侧。定系数的大小将足够大，可以覆盖子形式：

![由\ left和\右命令设置的定界符](/tex/images/java/tutorial/latex-math-7-10.png)

使用 `\left` 和 `\right` 时，它们必须配对使用，就像括号与组一样。您不能在一个子公式中使用 `\left`，而在另一个子公式中使用 `\right`。另外，您不能输入诸如 `\left(...{...\right...}` 或 `\left(...\begingroup...\right)...\endgroup` 之类的内容。这是因为 TeX 需要先排版出现在 `\left` 和 `\right` 之间的子公式，然后才能决定分隔符的大小。当您不使用 `\left` 和 `\right` 时，您不必匹配括号和方括号。因此，您可以输入诸如 `$[0,1)$` 或 `$)($` 甚至 `$)$` 之类的内容。即使您使用 `\left` 和 `\right`，您也不必匹配特定的符号，因此 `\left)` 或 `\right(` 不会导致错误。

但是，为什么当Tex可以自动计算`\ left`\ weled`\ right`的尺寸时，为什么要学习`\bigl`和`\bigr`以及其他同类人的知识呢？至少有三种情况，您需要自己选择适当的定界符大小：

(1)只需比较以下两个公式：

![\左和\右\ vs. \ bigl和\ bigr带垂直条](/tex/images/java/tutorial/latex-math-7-11.png)

确实，使用`\ left`和`\ right`不是一个明智的选择，因为他们无法找出适合最佳可读性的定界符大小。

(2)另一方面，有时`\ left`和`\ right`选择比您想要的更大的定界符。这主要是在将大型操作员封闭在显示屏中时发生的：

![\左而\右\ vs. `\ bigl` and `\ bigr`，带求和](/tex/images/java/tutorial/latex-math-7-12.png)

Tex的算法会导致`\ left`，`\ right`将``\ sum``及其限制一起包裹起来，但是在这种特殊情况下，让限制挂断一点看起来更好。因此，`\bigg`定界符在这里更好。

(3)当您需要排版大型显示的公式时，您必须将其分为两条或更多行。您要确保其打开和关闭的定系数具有相同的大小；但是，您不能在第一行上使用`\左`，而最后一行则不能使用`\ right`，因为必须成对出现`\ left`\ weled`\ right`。唯一的解决方案是在第一行上使用`\biggl`(例如)，而最后一行使用`\biggr`。

> 虽然 `\left` 和 `\right` 通常可以构成任意大小的分隔符，但斜线和尖括号却有最大长度限制。如果您需要这些符号的超大版本，您将获得最大的可用版本。

您还可以使用产生所谓的空零(空白)定界符的技巧。当您需要在视觉上只包含一个大型定界符的公式时，您将需要这样的定界符。例如，

![案件中的无分界符](/tex/images/java/tutorial/latex-math-7-13.png)

具有'{'''}'。它可以通过形式的构造产生


```tex
$$|x|=\left\{ ... \right.$$ 
```

其中`\ right。

乳胶还提供了更多的定系数，这些定界符在22的基本集合中未列出，因为它们很特别。命令`\ arrowvert`，`\ arrowvert`和`\ bracevert`产生由垂直箭头，双垂直箭头和大括号的可重复部分制成的定界器，没有箭头或撑杆的卷发部分。它们产生的结果类似于“ `\ vert`”和`\ vert`，但它们被更多的空间包围，并且重量不同。还有`\ lgroup`和`\ rgroup`，它们是由没有中间部分的牙套构造的；和“ `\ lmoustache`”和`\ rmoustache`产生大括号的顶部和底部。以下是带有`\big`和`\bigg`的版本`\ vert`，`\ vert`的显示器，以及这七个特殊的分隔符：

![乳胶提供的其他定界符](/tex/images/java/tutorial/latex-math-7-14.png)

您会发现`\ lgroup`和`\ rgroup`都像大胆的括号一样，弯道上有更尖锐的弯曲。这使它们在某些大型显示器上很有吸引力。请注意，您不能像括号那样完全使用它们，因为它们仅以`\big`的尺寸以及更多。