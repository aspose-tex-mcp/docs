---
translation: true
template: /templates/_template-java.md
linktitle: 装饰符号和复合结构
title: 4. 装饰符号和复合结构
weight: 40
url: /java/latex-math-decorations/
keywords: ams-latex、amsmath、amsxtra、latex积分、latex分数、latex装饰、latex箭头、latex极限、latex模关系
description: 本文讨论了一些使用 amsmath 宏包生成各种中等大小数学结构的命令。
lastmod: "2026-04-21"
---

{{<section overview>}}

`amsmath` 宏包提供了一些用于生成如分数类对象和装饰符号等结构的命令。本文覆盖其中的部分内容。

## 4.1. 一般分数

`amsmath` 宏包定义了 `\genfrac` 命令，用于生成广义分数。

```tex
\genfrac{ldelim}{rdelim}{thick}{style}{num}{denom}
```

前两个参数分别定义左、右分隔符。使用第三个参数 *thick*，可以覆盖分数线的默认粗细。例如，下文的二项式系数将此参数设为 `0pt` 以使线条不可见。默认值（未填写时）由当前数学排版的字体设置决定。下表列出了本文示例中使用的默认粗细。

| ***样式*** | ***默认粗细*** |
|:---:|:---:|
| text/display | 0.4pt |
| script | 0.34pt |
| scriptscript | 0.24pt |

第四个参数 *style*（若不为空）会覆盖所使用的数学样式和字体大小。取值范围为 0-3：0 - `\displaystyle`，1 - `\textstyle`，2 - `\scriptstyle`，3 - `\scriptscriptstyle`。若该参数为空，则按照分数的常规规则选择样式。最后两个参数分别是分子和分母。

> 老的分数命令 `\over`、`\overwithdelims`、`\atop`、`\atopwithdelims`、`\above` 和 `\abovewithdelims`（LaTeX 从 TeX 继承而来）在与 `amsmath` 宏包一起使用时会产生警告。

### 4.1.1. 简单分数

在拥有 `\genfrac` 命令的基础上，`amsmath` 宏包还定义了三个方便的速记命令：`\frac`、`\dfrac` 和 `\tfrac`。

```tex
\newcommand\frac [2]{\genfrac{}{}{}{}{#1}{#2}}
\newcommand\dfrac[2]{\genfrac{}{}{}{0}{#1}{#2}}
\newcommand\tfrac[2]{\genfraction{}{}{}{1}{#1}{#2}}
```

下面的示例演示了这些命令的使用：

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

![\frac, \dfrac, and \tfrac](/tex/images/java/tutorial/latex-ams-math-4-1.png)

### 4.1.2. 二项式系数

另一种类似分数的结构是二项式系数。为帮助排版，`amsmath` 宏包提供了相应的命令 `\binom`、`\dbinom` 和 `\tbinom`。

它们是对 `\genfrac` 命令的简写方式：

```tex
\newcommand\binom[2]{\genfrac{(}{)}{0pt}{}{#1}{#2}}
\newcommand\dbinom[2]{\genfrac{(}{)}{0pt}{0}{#1}{#2}}
\newcommand\tbinom[2]{\genfrac{(}{)}{0pt}{1}{#1}{#2}}
```

下面是示例：

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \binom{k}{2} 2^{k - 1} + \tbinom{k - 1}{2} 2^{k - 2}
\end{equation}
Text: $ \binom{k}{2} 2^{k - 1} + \dbinom{k - 1}{2} 2^{k - 2} $.
```

![\binom, \dbinom, and \tbinom](/tex/images/java/tutorial/latex-ams-math-4-2.png)

### 4.1.3. 连分数

如果需要排版分数阵列，即本质上是无限分数，也称为“连分数”，`amsmath` 宏包提供了 `\cfrac` 命令。可使用可选参数 `[l]` 或 `[r]` 将分子左对齐或右对齐，默认居中。

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

![A continued fraction](/tex/images/java/tutorial/latex-ams-math-4-3.png)

## 4.2. 盒装数学

`amsmath` 宏包提供了类似于 `\fbox` 的 `\boxed` 命令，用于将数学模式内容放入盒子中。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \boxed { f(x_0 - x) \leq f(x_0) \leq f(x_0 + x) }
\end{equation}
```

![A boxed formula](/tex/images/java/tutorial/latex-ams-math-4-4.png)

## 4.3. 限制位置

积分、求和、乘积或其他算符的下标和上标可以放置在算符的上下（即“极限位置”）或算符右侧的下标/上标位置。通常在行内文本中不使用极限位置（否则行距可能增大）。在显示公式中，放置方式取决于算符。下面的示例展示了 LaTeX 的默认放置方式。

```tex
\[
\sum_{n=1}^N \qquad \int_{-\infty}^\infty \qquad \lim_{x \to x_0}
\]
Text: $\sum_{n=1}^N$, $\int_{-\infty}^\infty$, $\lim_{x \to x_0}$.
```

![The default placement of the subscripts/superscripts in LaTeX](/tex/images/java/tutorial/latex-ams-math-4-5.png)

`amsmath` 宏包提供了控制位置的选项。下面列出这些选项，其中 *default* 标记在使用标准 LaTeX 文档类且未指定任何选项时的行为。

|||
|:---:|---|
| `intlimits`, `nointlimits` | 在积分符号上方和下方放置上下标（默认），或放在侧面。仅适用于显示公式。 |
| `sumlimits`, `nosumlimits` | 在大算符（求和、乘积等）的上下方放置上下标（默认）或侧面。仅适用于显示公式。 |
| `namelimits`, `nonamelimits` | 类似于 `sumlimits` 或 `nosumlimits`，但针对某些算符或“算符名称”，如 `inf`、`sup`、`lim`、`min`、`max`，这些通常在显示公式中以下标形式排版。 |

TeX 有三个原始命令，可在符号或算符名称后立即出现，控制下标/上标的位置：`\limits`、`\nolimits` 和 `\displaylimits`。`\displaylimits` 命令在当前数学样式为显示样式时，使下标/上标出现在极限位置。这是当出现 *Operator* 类符号或使用 `\mathop` 命令时的默认行为。如果需要在显示之外的环境中将算符的下标/上标置于极限位置，需要单独使用 `\limits` 命令。

将下面的示例与前一个进行比较。

```tex
\[
\sum\nolimits_{n=1}^N \qquad \int\limits_{-\infty}^\infty \qquad \lim\displaylimits_{x \to x_0}
\]
Text: $\sum\nolimits_{n=1}^N$, $\int\limits_{-\infty}^\infty$, $\lim\displaylimits_{x \to x_0}$.
```

![Controlling the placement of the subscripts/superscripts with TeX primitives](/tex/images/java/tutorial/latex-ams-math-4-6.png)

## 4.3. 多重积分

要在行文和显示公式中排版多个积分符号并使它们之间的间距合适，可使用 `\iint`、`\iiint` 和 `\iiiint` 命令。`\idotsint` 会生成两个积分符号，并在它们之间放置省略号。

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

![Multiple integrals](/tex/images/java/tutorial/latex-ams-math-4-7.png)

## 4.4. 模运算关系

整数同余类的 “mod” 表记受特殊间距约定的约束。为处理它，`amsmath` 宏包提供了 `\mod`、`\bmod`、`\pmod` 和 `\pod` 命令。下面的示例展示了这些命令的用法。

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

![Modular relation](/tex/images/java/tutorial/latex-ams-math-4-8.png)

> 使用 `amsmath` 时，`\pmod` 在非显示公式中的间距会减小。

## 4.5. 数学点重音

除了 `\dot` 和 `\ddot` 这两个数学重音外，`amsmath` 宏包还提供了 `\dddot` 和 `\ddddot` 命令，分别生成三点和四点重音。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
$ \dot{A} \quad \ddot{B} \quad \dddot{C} \quad \ddddot{D} $
```

![Dot accents](/tex/images/java/tutorial/latex-ams-math-4-9.png)

## 4.6. 将重音作为上标：`amsxtra` 宏包

`amsxtra` 宏包提供了一个实用功能，即一组简单命令，可将重音作为上标放置在子公式上：

```tex
\usepackage{amsxtra}
% -------------------------------------------------------------------------------
$(abc)\spdddot$ \quad $(abc)\spddot$ \quad $(abc) \spdot$ \\
$(abc)\spbreve$ \quad $(abc)\spcheck$ \\
$(abc)\sphat$ \quad $(abc)\sptilde$
```

![Accents as superscripts](/tex/images/java/tutorial/latex-ams-math-4-10.png)

## 4.7. 其他装饰

标准 LaTeX 提供了 `\stackrel` 命令，可在 *关系* 符号上方放置上标。此外，`amsmath` 宏包定义了 `\overset` 和 `\underset` 命令，用于在任意 *普通*、*关系* 或 *二元运算符* 符号的上方或下方放置内容。

`\sideset` 命令在任何 *算符* 符号（求和、乘积等）上添加装饰，除常规极限外，这些装饰会放置在算符左右的下标和上标位置。

```tex
\[ \overset{*}{X} > \underset{*}{X}
\iff \sideset{}{'}\sum_{a,b \in \mathbf{R^*}}
\overset{a}{\underset{b}{X}} = X \]
```

![More decoration](/tex/images/java/tutorial/latex-ams-math-4-11.png)
