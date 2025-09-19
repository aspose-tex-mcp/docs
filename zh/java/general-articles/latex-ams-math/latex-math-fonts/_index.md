---
translation: true
template: /templates/_template-java.md
linktitle: 乳胶数学字体
title: 8. 数学公式中的字体
weight: 80
url: /java/latex-math-fonts/
keywords: AMS-LATEX，AMSMATH，AMSFONTS，AMSSYMB，乳胶数学字体，乳胶数学字母，乳胶BM套件，乳胶字体，乳胶字体数学
description: 本文讨论了通过标准乳胶处理数学字体，以及使用AMSMATH和BM软件包。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 乳胶字体简介

与浮动文本不同，通常不需要字体形状的自动更改。不同的形状在数学上具有特定的含义。例如，大胆的直立字母可用于向量。如果公式中的字符由于周围条件而改变，则结果将是不正确的。这就是为什么在数学公式中处理字体与文本中的字体不同的原因。

公式中的字符可以分为两个类：符号和字母字符(包括数字)。实际上，Tex在内部处理八个类别定义适当间距的类。但是对于当前的讨论，分为两个类别就足够了。

可以直接从键盘输入一些符号，例如`=`。但是，必须通过命令输入部分，例如，`\ leq`给出小于或相等的符号。公式中的其他主要字符组，即字母字符，直接从键盘输入。

标准乳胶中有200多个符号。它允许用户几乎排版任何所需的公式。这些符号位于许多不同的字体中，但是可以以使用户不必意识到内部表示的方式访问它们。如有必要，可以使其他符号字体以类似的方式访问。

符号和字母字符具有一个对我们现在最重要的差异：符号在一个公式中具有相同的图形表示，而用户可以更改字母字符的外观。更改公式中字母字符外观的命令称为 *数学字母标识符 *，与这些命令相关的字体称为 *数学字母 *。公式在定理环境中放置在默认情况下是斜体的定理环境中，因为字母标识符独立于公式外的周围字体命令。这种行为非常重要，因为角色形状具有任何公式出现在文档中的含义，必须保持不变。

## 8.1. 数学字母标识符

对科学家来说，单一字母表和大量符号是不够的。他们试图用所有可用的字体来表示特殊概念。除了通常以符号形式出现的外来字母（例如`\alpha`、`\beta`等）外，我们还可以找到表示矩阵的无衬线字母、表示向量的粗体衬线字母，以及表示群、理想或域的 Fraktur 字体。其他人则使用书法形状来表示集合。约定的数量是无限的，并且它们因学科而异。LaTeX 适应了这一点，使得声明新的数学字母标识符并将其与任何所需的字体形状组相关联成为可能，而不必仅仅依赖于无法扩展的预定义集合。这些标识符是用于公式中的特殊命令，用于以特定字体排版其参数中的任何字母字符。这些标识符可能在不同的公式中使用不同的字体，正如我们将在[稍后](/tex/{{lang.url-fragment}}java/latex-math-fonts/#3-math-formula-versions)中看到的那样，但在一个公式中，它们总是选择相同的字体，而不管周围的条件如何。

### 预定义的字母标识符
乳胶已经有一些内置字母标识符。它们显示在下表中。最后两行表明，公式中使用的字母取自数学字母`\mathnormal`。另一方面，`\mathit`产生的字母具有不同的间距，这意味着该字母可用于提供某些学科中常见的全词变量名称。

| *Command* | *Example code* | *Result* |
|---|---|---|
| `\mathcal` | `$\mathcal{A}=a$` | !["书法 A 等于 a"](/tex/images/java/tutorial/latex-ams-math-8-1.png) |
| `\mathrm` | `$\mathrm{max}_i$`| !["罗马数字最大下标 i"](/tex/images/java/tutorial/latex-ams-math-8-2.png) |
| `\mathbf` | `$\sum x = \mathbf{v}$`| !["粗体和 x 等于 v"](/tex/images/java/tutorial/latex-ams-math-8-3.png) |
| `\mathsf` | `$\mathsf{G}_1^2$`| !["无衬线 G 下标 1 上标 2"](/tex/images/java/tutorial/latex-ams-math-8-4.png) |
| `\mathtt` | `$\mathtt{W}(a)$`| !["打字机 W 的 a"](/tex/images/java/tutorial/latex-ams-math-8-5.png) |
| `\mathnormal` | `$\mathnormal{abc}=abc$`| !["正常的 abc 等于 abc"](/tex/images/java/tutorial/latex-ams-math-8-6.png) |
| `\mathit` | `$differ\neq\mathit{differ}$`| !["斜体不同不等于不同"](/tex/images/java/tutorial/latex-ams-math-8-7.png) |

在latex2e中，数学字母标识符是带有一个参数，一个字母或单个单词的命令，是特殊字体中的排版。


```tex
Therefore, $\mathsf{G}$ can be computed as
\begin{equation}
\mathsf{G} = \mathcal{A} +
             \sum_{i=1}^{n} \mathcal{B}_{i}
\end{equation}
```

![预定义的数学字母标识符](/tex/images/java/tutorial/latex-ams-math-8-8.png)

***默认数学字母***

如果您不明确指定字母标识符，则选择字母字符是哪个字母？换句话说，默认数学字母是什么？答案是没有单个默认数学字母。可以设置乳胶系统，以便从不同的字母中获取字母顺序的字符，除非用户明确询问特定的字符，否则通常是这种情况，如以下示例所示。

```tex
\begin{eqnarray}
x &=& 12345 \\
\mathrm{x} &=& \mathrm{12345} \\
\mathnormal{x} &=& \mathnormal{12345}
\end{eqnarray}
```

![没有默认数学字母](/tex/images/java/tutorial/latex-ams-math-8-9.png)

在这里，您可以看到“ \ mathrm”不会更改数字，并且`\mathnormal`不会更改字母，因此正常设置中数字的默认值是与\ Mathrm'相关的数学字母，并且字母的默认值是与`\mathnormal`相关的字母。可以使用`\declaremathsymbol`命令来控制此行为。

### 乳胶用于数学字体什么？

在乳胶中，用于数学模式的默认字体通常为 *计算机现代 *。但是，您也可以通过使用软件包在乳胶文档序言中指定它们来使用不同的字体。

### 自定义字母标识符

您可以使用`\declaremathalphabet`命令来定义新的数学字母标识符。假设您想将倾斜的sans serif字体作为数学字母可用。首先，您决定使用一个新的命令名称，例如`\msfsl`，用作字母标识符。然后，您参考下面的字体分类表，以找到合适的字体形状组，以分配给此字母标识符。

![计算机现代字体家庭的分类](/tex/images/java/tutorial/latex-ams-math-8-10.png)

例如，您会发现**计算机现代sans** family由中等系列组成，形状直立和倾斜。如果您决定使用该家族的倾斜形状，则使用`\declaremathalphabet'告诉乳胶。

```text
\DeclareMathAlphabet{cmd}{encoding}{family}{series}{shape}
```

声明中有四个参数(除了标识符本身)：编码名称，家庭，系列和要使用字体的形状。以下示例中定义的字母标识符将始终切换到**计算机Modern Sans**中型。

```tex
\DeclareMathAlphabet{\msfsl}{OT1}{cmss}{m}{sl}
% -------------------------------------------------------------------------------
We demonstrate this with the formula
\begin{equation}
\sum \msfsl{A}_{i} = a \tan \beta
\end{equation}
```

![声明自定义数学字母标识符](/tex/images/java/tutorial/latex-ams-math-8-11.png)

您还可以在软件包文件或文档的序言中重新定义现有的数学字母标识符。例如，

```tex
\DeclareMathAlphabet{\mathsf}{OT1}{pag}{m}{n}
```

将覆盖“ \ Mathsf”字母标识符的默认设置。它将在您的配方中切换到**Adob​​e Adob​​e Adbant Garde**。

> 请注意，如果所讨论的数学字母是符号字体的一部分，并且由于其他原因（例如 `\mathcal`）已由 LaTeX 加载，则最好使用 `\DeclareSymbolFontAlphabet`，因为它可以更好地利用 TeX 有限的数学资源。

## 最好的数学字体

除默认 *计算机现代 *字体外，乳胶还提供了七个用于排版数学字母的内置字体，因此用户可以自定义其数学表达式，而无需序言中的其他软件包。最好的选择是使用这8个字体之一。

| **字体** | **用法** | **命令** |
|---|---|---|
|直立罗马体 | 标准直立字体 |`\mathrm{}`|
|书法体 | 用于排版常规数学字母。|`\mathnormal{}`|
|书法体 | 用于使用特殊的书法字体排版大写字母。|`\mathcal{}`|
|斜体字母 | 将文本设置为斜体 |`\mathit{}`|
|直立 [无衬线](/font/net/what-is-font/sans-serif-fonts/)| 设置直立无衬线字母 |`\mathsf{}`|
|直立罗马体粗体 | 用于排版直立罗马体粗体字母 |`\mathbf{}`|
|打字机类型|用于排版直立打字机类型的字母。|`\mathtt{}`|


## 8.2. 文本字体命令在数学中

尽管诸如'\ rmfamily`之类的文本字体声明不能在数学中使用，但字体改变命令 - 例如，`\ textrm`-都可以在文本和数学中使用。使用这些命令，您可以在公式中间暂时切换到文本上下文，并在公式的中间进行一些文本，这些文本是公式外周围文本的一部分。如下示例所述，用于排版此文本的字体将取决于周围条件，这意味着它将继承当前的编码，家庭，系列和形状。

```tex
\sffamily The result will be
\[ x = 10 \textbf{ and thus } y = 12 \]
```

![文本字体命令在数学中](/tex/images/java/tutorial/latex-ams-math-8-12.png)

这里我们可以看到，**Sans** 字体系列被保留了下来，并且系列被改为粗体。`amstext` 包（`amsmath` 也加载了该包）提供的 [`\text`](/tex/{{lang.url-fragment}}java/latex-text-in-math-formula/#61-the-text-command) 命令可能更有用。它会获取当前的编码、字体系列、系列和形状值，而不会进行任何更改。

## 8.3. 数学公式版本

我们已经讨论了如何使用数学字母标识符更改公式的部分。乳胶还允许您更改整个公式的外观。数学公式始终是特定 *数学版 *中的排版。您可以使用命令“ \ Mathversion”在数学模式之外切换数学版本，该命令更改以下公式的整体布局。

乳胶默认情况下有两个数学版本： *normal*and *bold*。而且特殊包装提供了更多版本。例如，*MathTime*软件包(用于商业**Mathtime**字体)设置了一个名为*heavy*的数学版本，以使用**Mathtime**字体提供的超粗体符号的排版公式。

显然，默认的数学版本是 `\mathversion{normal}`。粗体版本会生成更粗的字母和符号，但像 `\sum` 这样的大运算符默认情况下不会更改。下面的示例分别显示了同一个公式在普通版本和粗体数学版本中的显示效果。

```tex
\begin{equation}
  \sum_{j=1}^{z} j = \frac{z(z+1)}{2}
\end{equation}
\mathversion{bold}
\begin{equation}
  \sum_{j=1}^{z} j = \frac{z(z+1)}{2}
\end{equation}
```

![数学版本](/tex/images/java/tutorial/latex-ams-math-8-13.png)

在某些情况下（例如标题）使用 `\mathversion` 可能比较合适，但请记住，更改版本意味着更改整个公式的外观，甚至可能更改其含义。如果您只想加深某个公式中的部分符号或字符，则应使用 `\mathbf` 字母标识符来表示字符，和/或使用 [`bm`](/tex/{{lang.url-fragment}}java/latex-math-fonts/#5-bold-face-in-formulas-the-bm-package) 包提供的 `\bm` 命令，而不是更改 `\mathversion`。

当您更改数学版本时，乳胶在其内部表中查看以查找该新数学版本的所有符号所在的位置。它还可能更改所有或某些数学字母标识符，并将它们与此版本中的其他字体形状相关联。

但是，我们在[示例](/tex/{{lang.url-fragment}}java/latex-math-fonts/#custom-alphabet-identifiers)中定义的自定义字母标识符会发生什么？只要您使用`\declaremathalphabet'声明它们，它们在所有数学版本中都将保持不变。

如果要在特殊数学版本中生成不同的字体，则必须使用 `\SetMathAlphabet` 命令告知 LaTeX。例如，在默认设置中，`\mathsf` 字母标识符定义如下：

```tex
\DeclareMathAlphabet{\mathsf}{OT1}{cmss}{m}{n}
\SetMathAlphabet{\mathsf}{bold}{OT1}{cmss}{bx}{n}
```

第一行将 **Computer Modern Sans** medium 设置为所有数学版本中 `\mathsf` 的默认值。第二行指示 LaTeX 在粗体数学版本中使用 **Computer Modern Sans** bold extended。
```tex
\SetMathAlphabet{cmd}{version}{encoding}{family}{series}{shape}
```

您可能已经从前面的例子中猜到了，`\SetMathAlphabet` 接受六个参数：数学字母标识符、您正在为其定义特殊设置的数学版本名称，以及四个用于标识与设置关联的字体的参数。

如前所述，您可以使用 `\DeclareMathAlphabet` 重新定义现有的数学字母标识符。如果您这样做，则该标识符的所有先前 `\SetMathAlphabet` 声明都将从 LaTeX 的内部存储器中删除。因此，除非您为其添加新的 `\SetMathAlphabet` 声明，否则该标识符在所有数学版本中都会相同。

## 8.4. 使用AMS-LATEX包中的配方中调整字体

*amsfonts*（和 *amssymb*）包定义了两种数学字母表：欧拉花体字母表（`\mathfrak`）和黑板粗体字母表（`\mathbb`）。请参见下面的示例。

```tex
\usepackage{amsfonts}
% -------------------------------------------------------------------------------
$ \forall n \in \mathbb{N} : \mathfrak{M}_n \leq \mathfrak{A} $
```

![AMSFONTS数学字母标识符](/tex/images/java/tutorial/latex-ams-math-8-14.png)

## 5. 大胆的数学字体样式。 “ BM”包

仅对于拉丁字母，您可以使用 `\mathbf` 命令。对于其他所有字母，您可以使用 `bm` 包。只需加载它并使用 `\bm`，即可使任何公式尽可能地粗体和美观，直至可用字体允许。

以下示例展示了 `\bm` 和 `\mathbf` 命令的多种使用方法。它还展示了一种为常用粗体符号定义简写名称的策略，该策略同时使用了标准 LaTeX 的 `\newcommand` 和 `\bmdefine`（由 `bm` 包提供）。请注意，`\mathbf{xy}` 与 `\bm{xy}` 不同。前者生成粗体罗马数字“**xy**”，而后者生成“***xy***”（粗体数学斜体）。

```tex
\usepackage{amsmath,amssymb,bm}
\newcommand\bfB{\mathbf{B}} \newcommand\bfx{\mathbf{x}}
\bmdefine\bpi{\pi} \bmdefine\binfty{\infty}
% -------------------------------------------------------------------------------
\section{The bold equivalence
  $\sum_{j < B} \prod_\lambda : \bm{\sum_{x_j} \prod_\lambda}$}
\begin{gather}
  B_\infty + \pi B_1 \sim \bfB_{\binfty} \bm{+} \bpi \bfB_{\bm{1}}
    \bm {\sim B_\infty + \pi B_1}\\
  B_\binfty + \bpi B_{\bm{1}} \bm{\in} \bm{\biggl\lbrace}
    (\bfB, \bfx) : \frac {\partial \bfB}{\partial\bfx}
    \bm{\lnapprox} \bm{1} \bm{\biggr\rbrace}
\end{gather}
```

![使用BM软件包](/tex/images/java/tutorial/latex-ams-math-8-15.png)
 
在此示例中，`bm` 会尽力满足对单个符号和字母加粗版本的请求。但如果仔细观察，就会发现结果并非总是最佳。例如，求和运算符和乘积运算符采用一种称为“穷人的粗体”的技术，其中符号被套印三次，并略有偏移。此外，花括号根本没有加粗。这些缺陷是无法避免的，因为对于某些符号，使用**Computer Modern**数学字体时根本没有加粗版本。

`\bm` 遵循哪些具体规则来生成其参数中符号的加粗形式？通常，它利用 LaTeX 包含**粗体**数学版本（可通过 `\boldmath` 访问）这一事实，将整个公式排版为粗体（前提是存在并设置了合适的粗体字体）。对于每个符号，`\bm` 命令都会查看该数学版本，以了解该版本会执行的操作。如果符号选择的字体与普通数学版本中的字体不同，它会将符号排版为粗体字体，从而获得完美的效果（假设粗体数学版本设置正确）。如果两个版本的字体相同，它会假定没有可用的粗体变体，并采用“粗体”字体。

> 在改变现有数学字体设置的包之后加载“bm”包！

对于分隔符，情况会更加复杂，例如示例中的`\biggl\lbrace`。TeX 通常使用从一系列不同大小中选择的字形来排版分隔符，以匹配请求的高度。这些字形可以位于不同的字体中，并且特定大小可能有也可能没有粗体变体。所有这些因素加在一起使得`\bm`无法准确地确定是否需要应用“穷人的粗体”。因此，它使用粗体数学版本提供的任何字体来排版分隔符。使用**Computer Modern**数学字体，只有最小的分隔符大小可用于粗体；所有其他大小都来自没有粗体变体的字体。

```tex
\usepackage{bm}
% -------------------------------------------------------------------------------
$\bm{\Biggl\lbrace\biggl\lbrace\Bigl\lbrace\bigl \lbrace \lbrace
  \mathcal{Q}
  \rangle \bigr\rangle\Bigr\rangle\biggr\rangle
\Biggr\rangle}$
```

![\ bm命令制作(而不是制造)大胆的定界符](/tex/images/java/tutorial/latex-ams-math-8-16.png)

通常，如果命令本身带有参数，并且该参数位于 `\bm` 的参数内，则该命令必须完全包含在 `\bm` 的参数中。因此，排版材料的所有部分都将以粗体显示。如果您需要带参数的命令的输出仅部分加粗，则应执行以下操作。您应该将不想加粗的符号放在 `\mbox` 中，并使用 `\unboldmath` 明确重置框内容中的数学版本。TeX 将 `\mbox` 视为 *普通* 类的符号。因此，为了获得正确的间距，您可能需要用 `\mathbin`、`\mathrel` 或 `\mathop` 将其括起来。

```tex
\usepackage{amsmath,bm}
% -------------------------------------------------------------------------------
$ \bm{\sqrt[2]{x \times \alpha}} $ but
$ \bm{\sqrt[2]{x \mathbin{\mbox{\unboldmath$\times$}} \alpha}} $
or the similar
$ \bm{\sqrtsign}{\bm{x} \times \bm{\alpha}} $
```

![\ bm带有参数的命令](/tex/images/java/tutorial/latex-ams-math-8-17.png)

幸运的是，这种复杂的操作很少需要。在大多数涉及带参数的命令的情况下，只需将部分参数加粗。这可以通过在这些参数中使用 `\bm` 命令来实现。与上例中的 `\sqrtsign` 一样，对于常见的加粗重音符，`\bm` 经过特殊编程，允许重音符的参数位于其自身参数之外。但是，如果您经常需要这样的重音符，最好定义自己的缩写，如下例所示。

***提高性能***

虽然 `\bmdefine\bpi{\pi}` 看起来只是 `\newcommand\bpi{\bm{\pi}}` 的简写，但事实却恰恰相反：`\bm` 使用 `\bmdefine` 定义了一个新的隐藏临时命令，然后立即使用这个临时命令生成粗体符号。换句话说，`\bmdefine` 完成了所有繁琐的工作！例如，如果您经常使用通过 `\bm{\alpha}` 定义的某个命令，那么每次都会执行一个新的 `\bmdefine`。如果您在序言中提供 `\bmdefine\balpha{\alpha}` 定义，那么无论 `\balpha` 使用多少次，`\bmdefine` 都只会执行一次耗时的工作。

```tex
\usepackage{bm}
\bmdefine\bhat{\hat}
% -------------------------------------------------------------------------------
$\hat a \neq \bm{\hat a} \neq \bm\hat a = \bhat a\neq \bm\widehat a$
```

![优化用\ bm命令粗体制作口音](/tex/images/java/tutorial/latex-ams-math-8-18.png)

该示例还表明，可变宽度的重音(例如\ widehat”)与定界符有所不足：在**计算机现代**数学设置中，它们来自一个字体，没有可用的大胆变体。