---
translation: true
template: /templates/_template-java.md
linktitle: 装饰的符号和复合结构
title: 4. 装饰的符号和复合结构|乳胶手册
weight: 40
url: /java/latex-math-decorations/
keywords: AMS-LATEX，AMSMATH，AMSXTRA，乳胶积分，乳胶分数，乳胶装饰，乳胶箭头，乳胶限制，乳胶模块化关系
description: 本文讨论了许多使用AMSMATH软件包生成各种中型数学结构的命令。
lastmod: "2025-06-10"
---

{{<section overview>}}

`amsmath`软件包提供了一些命令，以产生诸如分数式对象和装饰符号之类的结构。这讨论涵盖了其中一些。


## 4.1. 一般分数

`amsmath`软件包定义了“ \ genfrac”命令，该命令产生了广义分数。

```tex
\genfrac{ldelim}{rdelim}{thick}{style}{num}{denom}
```

前两个参数分别定义了左右定义程序。使用第三个参数， *厚 *，您可以覆盖分数规则的默认厚度。例如，二线系数(请参见下文)使用该参数的值`0pt'，以使线变得不可见。线厚度的默认值(当剩下的空)由用于数学排放的当前字体设置确定。以下列表包含本文示例中使用的默认值。

| ***Style*** | ***Default Thickness*** |
|:---:|:---:|
| text/display | 0.4pt |
| script | 0.34pt |
| scriptscript | 0.24pt |

第四个参数， *样式 *，覆盖(如果不为空的话)使用的布局和字体大小的数学样式。该值必须在0-3：0 -`\ displayStyle`，1-`\ textStyle`，2- \ scriptStyle`，3- \ scriptsscriptstyle`。如果此参数为空，则根据分数的正常规则选择样式。最后两个参数是分子和分母。

> The old fraction commands `\over`, `\overwithdelims`, `\atop`, `\atopwithdelims`, `\above`, and `\abovewithdelims`, which standard LaTeX inherits from TeX, produce warnings when they are used with the `amsmath` package.

### 4.1.1. 简单的部分

拥有`\ genfrac`命令，'amsmath`包还将三个命令定义为方便的速记：`\ frac`，'\ dfrac`和'\ tfrac`。

```tex
\newcommand\frac [2]{\genfrac{}{}{}{}{#1}{#2}}
\newcommand\dfrac[2]{\genfrac{}{}{}{0}{#1}{#2}}
\newcommand\tfrac[2]{\genfrac{}{}{}{1}{#1}{#2}}
```

下面的示例说明了这些命令的使用：

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \frac{1}{k} \log_2 c(f)
  \quad \tfrac{1}{k} \log_2 c(f)
\end{equation}
Text: $ \sqrt{ \frac{1}{k} \log_2 c(f) } \quad
        \sqrt{ \dfrac{1}{k} \log_2 c(f) }\, $.

```

![\ frac，\ dfrac和\ tfrac](/tex/images/java/tutorial/latex-ams-math-4-1.png)

### 4.1.2. 二项式系数

另一个分数的结构是二项式系数。为了帮助您汇总它们，`amsmath`软件包提供了类似的命令`\ binom`，`\ dbinom`和`\ tbinom''。

这就是他们缩写“ \ genfrac”命令的方式：


```tex
\newcommand\binom[2]{\genfrac{(}{)}{0pt}{}{#1}{#2}}
\newcommand\dbinom[2]{\genfrac{(}{)}{0pt}{0}{#1}{#2}}
\newcommand\tbinom[2]{\genfrac{(}{)}{0pt}{1}{#1}{#2}}
```

这是一个例子：

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \binom{k}{2} 2^{k - 1} + \tbinom{k - 1}{2} 2^{k - 2}
\end{equation}
Text: $ \binom{k}{2} 2^{k - 1} + \dbinom{k - 1}{2} 2^{k - 2} $.
```

![\ binom，\ dbinom和\ tbinom](/tex/images/java/tutorial/latex-ams-math-4-2.png)

### 4.1.3. 继续分数

如果您需要排版一个分数阵列，该阵列本质上是无限分数，也称为“持续分数”，则`amsmath`软件包中有 `\ cfrac`命令。传递可选的参数`[l]或[r]`以对齐左侧或右侧的分子，默认为中心。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation*}
\cfrac {1}{\sqrt{2} +
  \cfrac {1}{\sqrt{3} +
    \cfrac {1}{\sqrt{4} +
      \cfrac[r] {1}{\sqrt{5} +
        \cfrac[l] {1}{\sqrt{6} + \dotsb }
}}}}
\end{equation*}
```

![持续的部分](/tex/images/java/tutorial/latex-ams-math-4-3.png)

## 4.2. 盒装数学

`amsmath`软件包提供了类似于`\ fbox`的`\ boxed`命令，以将数学模式内容放入框中。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \boxed { f(x_0 - x) \leq f(x_0) \leq f(x_0 + x) }
\end{equation}
```

![盒装公式](/tex/images/java/tutorial/latex-ams-math-4-4.png)

## 4.3. 定位极限

可以将积分，总和，产品或其他运算符上的下标和上标放置在数学运算符(“限制位置”)上方和下方，或在操作员右侧的下标/超级标题位置。通常，限制在文本中不使用(否则行可能会扩散)。在显示的公式中，放置取决于操作员。以下示例显示了乳胶中的默认位置。

```tex
\[
\sum_{n=1}^N \qquad \int_{-\infty}^\infty \qquad \lim_{x \to x_0}
\]
Text: $\sum_{n=1}^N$, $\int_{-\infty}^\infty$, $\lim_{x \to x_0}$.
```

![在乳胶中的下标/上标的默认位置](/tex/images/java/tutorial/latex-ams-math-4-5.png)

`amsmath`软件包提供了控制定位的选项。它们在下面列出，其中 *默认值 *标记了行为，以防标准乳胶文档类，但没有任何这些选项。

|||
|:---:|---|
| `intlimits`, `nointlimits` | 将积分符号的上标/下标分别放在上方、下方或侧面（默认）。仅用于显示的公式。|
| `sumlimits`, `nosumlimits` | 将*大型运算符*（和、积等）的上标/下标分别放在上方、下方（默认）或侧面。仅用于显示的公式。|
| `namelimits`, `nonamelimits` | 与 `sumlimits` 或 `nosumlimits` 类似，但适用于某些运算符或“运算符名称”，例如 `inf`、`sup`、`lim`、`min`、`max`，这些运算符或“运算符名称”传统上会在下面排版下标，至少当它们出现在显示的公式中时是这样。|

Tex具有三个原始命令，它们在符号或操作员名称之后立即出现，控制下标/上标的定位：`\ limits`，`\ nolimits`和'\ displaylimits“。当当前的数学样式是显示样式时，`\ displaylimits`命令在限制位置产生下标/上标。每当出现类 *运算符 *的符号或使用`\ Mathop`命令时，这都是默认行为。如果您需要在显示屏外部以限制位置以订阅/超级字样为操作员发行操作员，则必须使用` \ limits`命令单独声明它。

将以下示例与上一个示例进行比较。

```tex
\[
\sum\nolimits_{n=1}^N \qquad \int\limits_{-\infty}^\infty \qquad \lim\displaylimits_{x \to x_0}
\]
Text: $\sum\nolimits_{n=1}^N$, $\int\limits_{-\infty}^\infty$, $\lim\displaylimits_{x \to x_0}$.
```

![用Tex原始人控制下标/上标的位置](/tex/images/java/tutorial/latex-ams-math-4-6.png)

## 4.3. 多个积分

要在文本和显示器中以良好调整的空间进行排版多个积分符号，请使用`\iint`，`\iiint` `\iiint`和`\iiiint`命令''。 `\idotsint`产生了两个积分符号，它们之间有椭圆点。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather*}
\iint \limits _V f(x,y) \,dx \,dy \\
\iiint \limits _V f(x,y,z) \,dx \,dy \,dz \\
\iiiint \limits _V f(t,x,y,z) \,dt \,dx \,dy \,dz \\
\idotsint \limits _V f(x_1, \dots, x_k) \,\mathbf{dx}
\end{gather*}
```

![多个积分](/tex/images/java/tutorial/latex-ams-math-4-7.png)

## 4.4. 模块化关系

整数的等效类别的“ mod”表示法受特殊间隔惯例的约束。为了处理它，`amsmath`软件包提供了`\ mod`，`\bmod`，`\pmod`和`\ pod`命令。以下示例显示了这些命令的使用。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align*}
u & \equiv v + 1 \mod{n^2} \\
u & \equiv v + 1 \bmod{n^2} \\
u & = v + 1 \pmod{n^2} \\
u & = v + 1 \pod{n^2}
\end{align*}
The in-text layout: $ u = v + 1 \pmod{n^2} $
\begin{gather*}
(m \bmod n) = k^2 \, ; \quad x \equiv y \pmod b \, ; \\
x \equiv y \mod c \, ; \quad x \equiv y \pod d\, .
\end{gather*}
```

![模块化关系](/tex/images/java/tutorial/latex-ams-math-4-8.png)

> 使用 `amsmath`，在未显示的公式中 `\pmod` 的间距会减小。

## 4.5. 数学点重音

除了`\dot`和`\ddot`数学口音外，还提供命令`\dddot`和`\ddddot`，分别产生三重和四倍点点数。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
$ \dot{A} \quad \ddot{B} \quad \dddot{C} \quad \ddddot{D} $
```

![点口音](/tex/images/java/tutorial/latex-ams-math-4-9.png)

## 4.6. 用口音制作上标：“ amsxtra”软件包

`Amsxtra`软件包提供了一个有用的功能，一个简单命令的集合，用于将重点放置为Subformula的上标：

```tex
\usepackage{amsxtra}
% -------------------------------------------------------------------------------
$(abc)\spdddot$ \quad $(abc)\spddot$ \quad $(abc) \spdot$ \\
$(abc)\spbreve$ \quad $(abc)\spcheck$ \\
$(abc)\sphat$ \quad $(abc)\sptilde$
```

![重音作为上标](/tex/images/java/tutorial/latex-ams-math-4-10.png)

## 4.7. 其他装饰

标准乳胶具有`\stackrel`命令，该命令将上标放置在 *关系 *符号上方。此外，`amsmath`软件包定义了\ overset”和`\underSet`命令。使用它将材料放在任何 *普通 *或 *关系 *符号或 *二进制操作员 *符号上方或下方。

除正常限制外，`\sideet`命令还将装饰添加到任何 *运算符 *符号(总和，产品等)中。这些被放置在 *运算符 *的左右标记中的下标。

```tex
\[ \overset{*}{X} > \underset{*}{X}
\iff \sideset{}{'}\sum_{a,b \in \mathbf{R^*}}
\overset{a}{\underset{b}{X}} = X \]
```

![更多装饰](/tex/images/java/tutorial/latex-ams-math-4-11.png)