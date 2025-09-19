---
translation: true
template: /templates/_template-java.md
linktitle: 数式のテキスト
title: 6。数式のテキスト
weight: 60
url: /java/latex-text-in-math-formula/
keywords: AMS-Latex、AMSMATH、LATEX MATH OPERATORS、LATEX MATH FUNCTIONS、LATEX MATH TEXT
description: この記事では、テキストの挿入をLaTex MATHフォーミュラに挿入します。また、数学機能と演算子、およびそれらを定義する方法についても説明しています。
lastmod: "2025-06-09"
---

{{<section overview>}}

## 6.1。 `\ text`コマンド

通常のテキストを数学の内部に配置するには、「\ mathrm」のようなコマンドよりも「\ text」コマンドを使用する方が良いです。 `\ text`コマンドは、正しいフォントサイズを使用してテキストが設定されていることを保証します。フォントは、現在の数学資料の外で使用されているテキストフォントになります。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
\text{Also, if } \Delta_{\text{max up}} = \Delta_{\text{min down}} \notag \\
\text{(for all ups and downs) then} \notag \\
\Delta_{\text{sum of ups}} = \Delta_{\text{sum of downs}}
\end{gather}
```

![数学内のテキスト](/tex/images/java/tutorial/latex-ams-math-6-1.png)

## 6.2。オペレーター名

一般的な数学関数名（例：*sin*、*log*）や演算子名（例：*min*、*sup*）は、通常、イタリック体で表記される変数名と区別することが望まれます。そのため、これらは伝統的にローマン体で表記されます。標準的なLaTeXには、最も一般的な関数と演算子用の定義済みコマンドが用意されています。`amsmath`パッケージは、そのようなコマンド群を十分に拡張します。次の表は、「標準」コマンドと`amsmath`が提供するコマンドの両方を示しています。後者は太字で強調表示されています。イタリック体で表記されているコマンドは、数式表示で使用する際に、極限位置に下付き文字/上付き文字が付く場合があります。

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

多くの場合、このリストでは十分ではないことがわかります。 `Amsmath`パッケージは、新しい「オペレーター名」を定義する一般的な方法を定義します。


```tex
\DeclareMathOperator*{cmd}{text}
```

`\ decleRemathoperator`」コマンドは、「CMD」を定義し、「テキスト演算子」の適切なフォントで「テキスト」を生成します。新しいオペレーターが限界位置に添え字/上付き文字を持っていると予想される場合(ディスプレイで使用する場合)、星付きフォーム `\ declaremathoperator*`を使用する必要があります。適切なフォントを使用することに加えて、 `\ decleRemathoperator`はオペレーター名の両側に適切な間隔を設定します。テキスト引数は、「擬似テキストモード」を使用して処理されます。

 - ハイフンチャーはテキストハイフンとして印刷されています(マイナスサインではありません)(次の例では「\ supminus」を参照)。
 - アスタリスクchar `*`は、上昇したテキストアスタリスクとして印刷されています(中心にありません)。
 - それ以外の場合、テキストは数学モードで処理されるため、スペースが無視され、サブスクリプト、上付き文字、その他の要素を使用できます。

次の例は、新しい関数名`\meas`(測定) にコマンド `\meas` と演算子関数 `\esssup` および `\supminus` (どちらも限界位置に下付き文字/上付き文字を持つことができます) を指定する方法を示しています。


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

そのような宣言は前文に表示されなければならず、それらを一時的に変更することは不可能です。厳密に言えば、「\ DecleRemathoperator」は、以前に使用されていなかったコマンド名にのみ使用できます。既存のコマンドを置き換えるには、最初に以前の定義を削除する前に削除する必要があります。


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