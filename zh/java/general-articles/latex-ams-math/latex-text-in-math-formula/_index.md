---
translation: true
template: /templates/_template-java.md
linktitle: 数学公式中的文本
title: 6. 数学公式中的文本
weight: 60
url: /java/latex-text-in-math-formula/
keywords: ams-latex、amsmath、LaTeX 数学运算符、LaTeX 数学函数、LaTeX 数学文本
description: 本文讨论如何在 LaTeX 数学公式中插入文本。文章还介绍了数学函数和运算符，以及定义它们的方法。
lastmod: "2026-02-19"
---

{{<section overview>}}

## 6.1. `\text` 命令

要在数学公式中放入普通文本，最好使用 `\text` 命令，而不是像 `\mathrm` 这样的命令。`\text` 命令确保文本使用正确的字号。该字体将是当前数学材料之外使用的正文字体。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
\text{Also, if } \Delta_{\text{max up}} = \Delta_{\text{min down}} \notag \\
\text{(for all ups and downs) then} \notag \\
\Delta_{\text{sum of ups}} = \Delta_{\text{sum of downs}}
\end{gather}
```

![数学公式中的文本](/tex/images/java/tutorial/latex-ams-math-6-1.png)

## 6.2. 运算符名称

常用数学函数（例如 *sin* 和 *log*）和运算符（例如 *min* 和 *sup*）的名称通常需要与斜体变量名区分开来。因此，它们传统上以罗马体文本形式设置。标准 LaTeX 为最常用的函数和运算符提供了预定义的命令。`amsmath` 宏包大幅扩展了这些命令的集合。下表列出了“标准”命令以及 `amsmath` 提供的命令。后者用粗体标出。斜体形式的命令在显示公式中使用时，其下标/上标可以位于极限位置。

|||||||
|:---:|---|:---:|---|:---:|---|
| !["Arccos"](/tex/images/java/tutorial/latex-ams-math-foper-6-1.png) | `\arccos` | !["Arcsin"](/tex/images/java/tutorial/latex-ams-math-foper-6-14.png) | `\arcsin` | !["Arctan"](/tex/images/java/tutorial/latex-ams-math-foper-6-27.png) | `\arctan` |
| !["Arg"](/tex/images/java/tutorial/latex-ams-math-foper-6-2.png) | `\arg` | !["Cos"](/tex/images/java/tutorial/latex-ams-math-foper-6-15.png) | `\cos` | !["Cosh"](/tex/images/java/tutorial/latex-ams-math-foper-6-28.png) | `\cosh` |
| !["Cot"](/tex/images/java/tutorial/latex-ams-math-foper-6-3.png) | `\cot` | !["Coth"](/tex/images/java/tutorial/latex-ams-math-foper-6-16.png) | `\coth` | !["Csc"](/tex/images/java/tutorial/latex-ams-math-foper-6-29.png) | `\csc` |
| !["Deg"](/tex/images/java/tutorial/latex-ams-math-foper-6-4.png) | `\deg` | !["Det"](/tex/images/java/tutorial/latex-ams-math-foper-6-17.png) | *`\det`* | !["Dim"](/tex/images/java/tutorial/latex-ams-math-foper-6-30.png) | `\dim` |
| !["Exp"](/tex/images/java/tutorial/latex-ams-math-foper-6-5.png) | `\exp` | !["Gcd"](/tex/images/java/tutorial/latex-ams-math-foper-6-18.png) | *`\gcd`* | !["Hom"](/tex/images/java/tutorial/latex-ams-math-foper-6-31.png) | `\hom` |
| !["Inf"](/tex/images/java/tutorial/latex-ams-math-foper-6-6.png) | *`\inf`* | !["Injlim"](/tex/images/java/tutorial/latex-ams-math-foper-6-19.png) | ***`\injlim`*** | !["Ker"](/tex/images/java/tutorial/latex-ams-math-foper-6-32.png) | `\ker` |
| !["Lg"](/tex/images/java/tutorial/latex-ams-math-foper-6-7.png) | `\lg` | !["Lim"](/tex/images/java/tutorial/latex-ams-math-foper-6-20.png) | *`\lim`* | !["Liminf"](/tex/images/java/tutorial/latex-ams-math-foper-6-33.png) | *`\liminf`* |
| !["Limsup"](/tex/images/java/tutorial/latex-ams-math-foper-6-8.png) | *`\limsup`* | !["Ln"](/tex/images/java/tutorial/latex-ams-math-foper-6-21.png) | `\ln` | !["Log"](/tex/images/java/tutorial/latex-ams-math-foper-6-34.png) | `\log` |
| !["Max"](/tex/images/java/tutorial/latex-ams-math-foper-6-9.png) | *`\max`* | !["Min"](/tex/images/java/tutorial/latex-ams-math-foper-6-22.png) | *`\min`* | !["Pr"](latex-ams-math-foper-6-35.png) | *`\Pr`* |
| !["Projlim"](/tex/images/java/tutorial/latex-ams-math-foper-6-10.png) | ***`\projlim`*** | !["Sec"](/tex/images/java/tutorial/latex-ams-math-foper-6-23.png) | `\sec` | !["Sin"](/tex/images/java/tutorial/latex-ams-math-foper-6-36.png) | `\sin` |
| !["Sinh"](/tex/images/java/tutorial/latex-ams-math-foper-6-11.png) | `\sinh` | !["Sup"](/tex/images/java/tutorial/latex-ams-math-foper-6-24.png) | *`\sup`* | !["Tan"](/tex/images/java/tutorial/latex-ams-math-foper-6-37.png) | `\tan` |
| !["Tanh"](/tex/images/java/tutorial/latex-ams-math-foper-6-12.png) | `\tanh` | !["Varinjlim"](/tex/images/java/tutorial/latex-ams-math-foper-6-25.png) | ***`\varinjlim`*** | !["Varliminf"](/tex/images/java/tutorial/latex-ams-math-foper-6-38.png) | ***`\varliminf`*** |
| !["Varlimsup"](latex-ams-math-foper-6-13.png) | ***`\varlimsup`*** | !["Varprojlim"](/tex/images/java/tutorial/latex-ams-math-foper-6-26.png) | ***`\varprojlim`*** |  |  |


```tex
\usepackage[fleqn]{amsmath}
\newcommand\abs[1]{\lvert#1\rvert}
\setlength\mathindent{0pt}
% -------------------------------------------------------------------------------
\begin{gather*}
\lim_{x \rightarrow 0} \frac{ \sin^2(x) }{ x^2 } = 1 \\
\varliminf_{n \rightarrow \infty}
\abs{a_{n+1}} / \abs{a_n} = 0 \\
\varinjlim (m_i^\lambda \cdot M)^* \le
\varprojlim_{A/p \rightarrow \lambda(A)}A_p \le 0
\end{gather*}
```

![函数与运算符](/tex/images/java/tutorial/latex-ams-math-6-2.png)

通常会发现此列表并不足够。`amsmath` 宏包定义了一种通用方法来定义新的“运算符名称”。

```tex
\DeclareMathOperator*{cmd}{text}
```

`\DeclareMathOperator` 命令定义 `cmd` 以在适当的“文本运算符”字体中生成 `text`。如果新运算符在显示公式中需要在极限位置拥有下标/上标，则应使用带星号的形式 `\DeclareMathOperator*`。除了使用正确的字体外，`\DeclareMathOperator` 还会在运算符名称两侧设置良好的间距。其文本参数采用一种“伪文本模式”进行处理，其中：

 - 连字符会作为普通文本连字符打印（而不是减号），（参见下一个示例中的 `\supminus`）。
 - 星号字符 `*` 会作为上标的文本星号打印（而不是居中）。
 - 否则，文本在数学模式下处理，空格会被忽略，并且可以使用下标、上标以及其他元素。

下面的示例展示了如何为新函数名 “meas”（measure）提供命令 `\meas`，以及运算符函数 `\esssup` 和 `\supminus`（它们都可以在极限位置拥有下标/上标）。

```tex
\usepackage[fleqn]{amsmath}
\DeclareMathOperator \meas {meas}
\DeclareMathOperator*\esssup {ess \, sup}
\DeclareMathOperator*\supminus{sup - minus*}
\newcommand\abs [1]{\lvert#1\rvert}
\newcommand\norm[1]{\lVert#1\rVert}
% -------------------------------------------------------------------------------
\begin{gather*}
  \norm{f}_\infty = \esssup_{x \in R^n} \abs{f(x)} \\
  \meas_1 \{ u \in R_+^1 \colon f^*(u)>\alpha \} \\
  \quad \esssup_{x \in R^i} \; \meas_i
  \{ u \in R^n \colon \abs{f(u)} \geq \alpha \} \\
  \quad (\forall \alpha \in \supminus_{f^*} R_{*+})
\end{gather*}
```

![新的函数名和运算符名](/tex/images/java/tutorial/latex-ams-math-6-3.png)

此类声明必须写在导言区，且无法临时更改。严格来说，`\DeclareMathOperator` 只能用于尚未使用过的命令名。若要替换已有命令，必须先取消先前的定义，然后再重新声明。

```tex
\usepackage{amsmath}
%% Low-level TeX needed here to cancel the old the definition of \csc:
\let \csc \relax
\DeclareMathOperator\csc{cosec}
\newcommand\calQ{\mathcal{Q}}
% -------------------------------------------------------------------------------
\[
\varlimsup_{n\to\infty} \calQ (u_n, u_n - u^{\#})
  \ge \csc (\calQ' (u^{\#}))
\]
```

![重新定义函数名](/tex/images/java/tutorial/latex-ams-math-6-4.png)
