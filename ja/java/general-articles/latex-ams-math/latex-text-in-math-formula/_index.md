---
translation: true
template: /templates/_template-java.md
linktitle: 数式内のテキスト
title: 6. 数式内のテキスト
weight: 60
url: /java/latex-text-in-math-formula/
keywords: ams-latex, amsmath, latex math operators, latex math functions, latex math text
description: この記事では、LaTeX の数式にテキストを挿入する方法について説明します。また、数学関数や演算子、そしてそれらの定義方法についても解説します。
lastmod: "2026-02-19"
---

{{<section overview>}}

## 6.1. `\text` コマンド

数式内に通常のテキストを入れるには、`\mathrm` などのコマンドよりも `\text` コマンドを使用した方がよいです。`\text` コマンドは、テキストが適切なフォントサイズで設定されることを保証します。フォントは、現在の数式外で使用されているテキストフォントになります。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
\text{Also, if } \Delta_{\text{max up}} = \Delta_{\text{min down}} \notag \\
\text{(for all ups and downs) then} \notag \\
\Delta_{\text{sum of ups}} = \Delta_{\text{sum of downs}}
\end{gather}
```

![数式内のテキスト](/tex/images/java/tutorial/latex-ams-math-6-1.png)

## 6.2. 演算子名

一般的な数学関数（例：*sin* や *log*）や演算子（例：*min* や *sup*）の名前は、イタリック体で設定される変数名と区別するために、ローマン体のテキストとして表記するのが一般的です。標準 LaTeX には、最も一般的な関数と演算子のための事前定義コマンドが用意されています。`amsmath` パッケージは、これらのコマンドセットを十分に拡張します。以下の表は、標準コマンドと `amsmath` が提供するコマンドの両方を一覧にしています。後者は太字で示されています。イタリック体で示されたものは、表示数式で使用した場合に下限/上限位置に添字/上添字が付くことがあります。

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

![関数と演算子](/tex/images/java/tutorial/latex-ams-math-6-2.png)

このリストだけでは十分でないことがよくあります。`amsmath` パッケージは、新しい「演算子名」を定義するための一般的な方法を提供しています。

```tex
\DeclareMathOperator*{cmd}{text}
```

`\DeclareMathOperator` コマンドは、`cmd` が「テキスト演算子」に適したフォントで `text` を生成するように定義します。新しい演算子が表示数式で下限/上限位置に添字/上添字を持つことが期待される場合は、スター付き形式 `\DeclareMathOperator*` を使用すべきです。適切なフォントを使用することに加えて、`\DeclareMathOperator` は演算子名の両側に適切な間隔を自動的に設定します。`text` 引数は「擬テキストモード」で処理され、次のような特徴があります。

 - ハイフン文字はテキストハイフンとして出力され（マイナス記号ではなく）、次の例の `\supminus` を参照してください。
 - アスタリスク文字 `*` は高さが上がったテキストアスタリスクとして出力されます（中央揃えではありません）。
 - それ以外の場合、テキストは数式モードで処理されるため、空白は無視され、添字・上添字やその他の要素を使用できます。

以下の例は、新しい関数名「meas」（measure）に対してコマンド `\meas` を、演算子関数 `\esssup` と `\supminus`（どちらも下限/上限位置に添字/上添字を持つことができる）を提供する方法を示しています。

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

![新しい関数名と演算子名](/tex/images/java/tutorial/latex-ams-math-6-3.png)

このような宣言はプリアンブルに記述する必要があり、途中で一時的に変更することはできません。厳密に言うと、`\DeclareMathOperator` はこれまでに使用されていないコマンド名に対してのみ使用できます。既存のコマンドを置き換える場合は、再宣言する前に以前の定義を削除する必要があります。

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

![関数名の再定義](/tex/images/java/tutorial/latex-ams-math-6-4.png)
