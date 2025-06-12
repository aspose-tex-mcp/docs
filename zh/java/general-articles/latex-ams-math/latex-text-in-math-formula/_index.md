---
translation: true
template: /templates/_template-java.md
linktitle: 数学公式的文字
title: 6. 数学公式中的文字|乳胶手册
weight: 60
url: /java/latex-text-in-math-formula/
keywords: AMS-LATEX，AMSMATH，乳胶数学运营商，乳胶数学功能，乳胶数学文本
description: 本文讨论将文本插入乳胶数学公式中。它还描述了数学功能和运算符，以及定义它们的方法。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 6.1.  `\text`命令

要将普通文本放入数学中，最好使用`\text`命令而不是'\ mathrm'的命令。 `\text`命令确保使用正确的字体大小设置文本。该字体将是当前数学材料之外使用的文本字体。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
\text{Also, if } \Delta_{\text{max up}} = \Delta_{\text{min down}} \notag \\
\text{(for all ups and downs) then} \notag \\
\Delta_{\text{sum of ups}} = \Delta_{\text{sum of downs}}
\end{gather}
```

![数学中的文字](/tex/images/java/tutorial/latex-ams-math-6-1.png)

## 6.2. 操作员名称

普通数学功能(例如 *sin *and *log *)和运算符(例如 *min *and *sup *)的名称通常优先区分与斜体中设置的可变名称。因此，它们传统上被视为罗马类型的文本。标准乳胶中有预定义的命令，用于最常见的功能和操作员。 `amsmath`软件包足够扩展了此类命令的集合。下表列出了“标准”命令和'amsmath提供的命令。后者以粗体突出显示。当在显示的公式中使用时，斜体设置的那些在极限位置中可能具有下标/上标。

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

![功能和操作员](/tex/images/java/tutorial/latex-ams-math-6-2.png)

通常事实证明，此列表还不够。 `amsmath`软件包定义了定义新“操作员名称”的一般方法。


```tex
\DeclareMathOperator*{cmd}{text}
```

`\declaremathoperator`命令定义`cmd`以在“ textual operators”的适当字体中生成`text`。如果期望新运算符在限制位置(在显示中使用时使用)的下标/上标，则应使用星级`\declaremathoperator`。除了使用合适的字体外，`\declaremathoperator`在操作员名称的两侧设置了良好的间距。文本参数是使用“伪文本模式”处理的

- 连字符将打印为文本连字符（而不是减号）（请参阅下一示例中的 `\supminus`）。
- 星号字符 `*` 将打印为凸起的文本星号（不居中）。
- 否则，文本将以数学模式处理，以便忽略空格，并且您可以使用下标、上标和其他元素。

下面的示例显示了如何为新功能名称“ MES”(MEATE)和操作员函数提供命令`\sues's \esssup`和`\supminus`(两者都在限制位置具有下标/超级字样)。


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

![新功能名称和操作员名称](/tex/images/java/tutorial/latex-ams-math-6-3.png)

这样的声明必须出现在序言中，并且不可能暂时更改它们。严格来说，`\declaremathoperator“只能用于以前尚未使用的命令名称。要替换现有命令，您必须先删除先前的定义，然后再重新启动它。


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

![重新定义功能名称](/tex/images/java/tutorial/latex-ams-math-6-4.png)