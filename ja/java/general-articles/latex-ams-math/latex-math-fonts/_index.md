---
translation: true
template: /templates/_template-java.md
linktitle: LaTeX 数式フォント
title: 8. 数式フォント
weight: 80
url: /java/latex-math-fonts/
keywords: ams-latex、amsmath、amsfonts、amssymb、LaTeX 数式フォント、LaTeX 数式アルファベット、LaTeX bm パッケージ、LaTeX フォント、LaTeX 数式フォント
description: この記事では、標準的な LaTeX と amsmath パッケージ、および bm パッケージを使用した数式フォントの扱いについて説明します
lastmod: "2026-02-19"
---

{{<section overview>}}

## LaTeX フォントの概要

本文中のテキストとは異なり、数式ではフォント形状が自動的に変化する必要はほとんどありません。数学では形状に特定の意味が付随しています。たとえば、太字の立体（upright）文字はベクトルに使われることがあります。もし数式中の文字が周囲の条件によって変化したら、結果は正しくなくなります。そのため、数式中のフォント取り扱いは本文のフォント取り扱いとは異なるのです。

数式中の文字は **記号** と **アルファベット文字（数字を含む）** の二つに分けられます。実際には TeX は内部で八つのクラスを使って適切な間隔を決めていますが、ここでは二つのクラスに分けるだけで十分です。

`=` のようにキーボードから直接入力できる記号もありますが、`\leq` のようにコマンドで入力しなければならない記号もあります。数式中のもう一つの主要な文字群であるアルファベット文字は、キーボードから直接入力します。

標準 LaTeX だけでも 200 程度の記号が定義されており、ほぼすべての欲しい式を組むことができます。これらの記号はさまざまなフォントに収められていますが、内部表現を意識せずに使用できます。必要に応じて、追加の記号フォントも同様の方法で利用可能です。

記号とアルファベット文字の最大の違いは次のとおりです。**記号は同一数式内で常に同じグラフィック表現** を持ちますが、**アルファベット文字は外部からのコマンドで外観を変えることができる** という点です。数式中のアルファベット文字の外観を変えるコマンドは *math alphabet identifier* と呼ばれ、これに対応するフォントは *math alphabet* と呼ばれます。たとえば定理環境のようにデフォルトで斜体になる場所に数式を入れても、アルファベット識別子は数式外のフォントコマンドに影響されません。この振る舞いは、文字形が特定の意味を持ち、文書中どこに現れても変わってはならないため、非常に重要です。

## 8.1. Math alphabet identifiers

科学者にとって 1 つのアルファベットと多数の記号だけでは足りません。特別な概念を示すために、利用可能なすべての書体を使おうとします。たとえばギリシャ文字（`\alpha`、`\beta` など）は記号として扱われますが、行列用のサンセリフ体、ベクトル用の太字セリフ体、群・イデアル・体用のフラクトゥール体、集合用のカリグラフィ体など、さまざまな書体が利用されています。慣例は無限にあり、分野ごとに異なります。LaTeX はこれらをサポートし、**新しい math alphabet identifier** を宣言して任意のフォント形状に結び付けることが可能です。これらの識別子は数式中で使用され、引数に与えた任意のアルファベット文字を特定の書体で組版します。識別子は数式ごとに異なる書体を使用でき（後述）、同一数式内では常に同じ書体が選択されます。

### 事前定義された alphabet identifiers

LaTeX にはすでにいくつかの組み込み alphabet identifier が用意されています。以下の表に示します。最後の二行は、数式中の文字が `\mathnormal` から取られることを示しています。一方、`\mathit` が生成する文字は間隔が異なり、いくつかの分野でよく使われる単語型変数名に適しています。

| *Command* | *Example code* | *Result* |
|---|---|---|
| `\mathcal` | `$\mathcal{A}=a` | … |
| `\mathrm` | `$\mathrm{max}_i` | … |
| `\mathbf` | `$\sum x = \mathbf{v` | … |
| `\mathsf` | `$\mathsf{G}_1^2` | … |
| `\mathtt` | `$\mathtt{W}(a` | … |
| `\mathnormal` | `$\mathnormal{abc}=abc` | … |
| `\mathit` | `$differ\neq\mathit{differ}` | … |

（画像は英語版と同一です）

LaTeX2e では、math alphabet identifier は **1 つの引数（単一文字または単語）** を取るコマンドです。

```tex
Therefore, $\mathsf{G}$ can be computed as
\begin{equation}
\mathsf{G} = \mathcal{A} +
             \sum_{i=1}^{n} \mathcal{B}_{i}
\end{equation}
```

![Predefined math alphabet identifiers](/tex/images/java/tutorial/latex-ams-math-8-8.png)

***デフォルトの math alphabet***

明示的に alphabet identifier を指定しなかった場合、文字はどの alphabet から取られるのでしょうか？ すなわち、デフォルトの math alphabet は何でしょうか？ 実は、**単一のデフォルト** は存在しません。LaTeX システムは、ユーザーが特に指定しない限り、文字はさまざまな alphabet から取得されるよう設定できます。以下の例がその様子を示しています。

```tex
\begin{eqnarray}
x &=& 12345 \\
\mathrm{x} &=& \mathrm{12345} \\
\mathnormal{x} &=& \mathnormal{12345}
\end{eqnarray}
```

![No default math alphabet](/tex/images/java/tutorial/latex-ams-math-8-9.png)

ここで `\mathrm` は数字の形を変えず、`\mathnormal` は文字の形を変えないことが分かります。したがって、標準設定では数字は `\mathrm`、文字は `\mathnormal` がデフォルトとなります。この振る舞いは `\DeclareMathSymbol` コマンドで制御できます。

### LaTeX が数式で使用するフォントは？

LaTeX の数式モードのデフォルトフォントは通常 **Computer Modern** です。ただし、プリアンブルでパッケージを指定すれば別のフォントも使用できます。

### カスタム alphabet identifiers

`\DeclareMathAlphabet` コマンドを使って新しい math alphabet identifier を定義できます。たとえば、斜体サンセリフ体を math alphabet として利用したい場合、`\msfsl` という新しいコマンド名を決め、下表のフォント分類表から適切なフォント形状を選びます。

![Classification of the Computer Modern font families](/tex/images/java/tutorial/latex-ams-math-8-10.png)

たとえば **Computer Modern Sans** ファミリは、medium 系列の upright と slanted の形があります。slanted 形を使用したい場合は次のように宣言します。

```text
\DeclareMathAlphabet{cmd}{encoding}{family}{series}{shape}
```

```tex
\DeclareMathAlphabet{\msfsl}{OT1}{cmss}{m}{sl}
% -------------------------------------------------------------------------------
We demonstrate this with the formula
\begin{equation}
\sum \msfsl{A}_{i} = a \tan \beta
\end{equation}
```

![Declaring a custom math alphabet identifier](/tex/images/java/tutorial/latex-ams-math-8-11.png)

既存の math alphabet identifier もパッケージファイルやプリアンブルで再定義できます。たとえば

```tex
\DeclareMathAlphabet{\mathsf}{OT1}{pag}{m}{n}
```

とすれば、`\mathsf` は **Adobe Avant Garde** に置き換わります。

> ただし、対象の math alphabet がすでに他の理由で LaTeX に読み込まれているシンボルフォントの一部である場合（例：`\mathcal`）、`\DeclareSymbolFontAlphabet` を使用した方がリソースの無駄が少なくなります。

## ベストな数式フォント

標準の *Computer Modern* に加えて、LaTeX には組み込みの 7 つのフォントがあり、追加パッケージなしで数式のフォントをカスタマイズできます。以下は代表的な 8 種類のフォントです。

| **フォント** | **用途** | **コマンド** |
|---|---|---|
| Upright Roman | 標準の立体ローマン体 | `\mathrm{}` |
| Calligraphic | 通常の数学記号用 | `\mathnormal{}` |
| Calligraphic | 大文字を特別なカリグラフィ体で | `\mathcal{}` |
| Italic letters | 斜体文字 | `\mathit{}` |
| Upright [Sans Serif](/font/net/what-is-font/sans-serif-fonts/) | 立体サンセリフ体 | `\mathsf{}` |
| Upright Roman boldface | 立体ローマン太字 | `\mathbf{}` |
| Typewriter type | 等幅タイプライタ体 | `\mathtt{}` |

## 8.2. 数式中のテキストフォントコマンド

`\rmfamily` のようなテキストフォント宣言は数式中では使えませんが、`\textrm` などのフォント切り替えコマンドは数式でも使用できます。これらを使うと、数式の途中でテキストコンテキストに一時的に切り替えて、式の中に周囲のテキストと同様の文字列を組むことができます。使用例は次のとおりです。

```tex
\sffamily The result will be
\[ x = 10 \textbf{ and thus } y = 12 \]
```

![Text font commands in math](/tex/images/java/tutorial/latex-ams-math-8-12.png)

この例では **Sans** ファミリが保持され、シリーズが太字に変わっています。`amstext` パッケージ（`amsmath` が自動で読み込む）で提供される `\text` コマンドは、現在のエンコーディング・ファミリ・シリーズ・シェイプをそのまま引き継ぐので便利です。

## 8.3. Math formula versions

数式全体の外観を変更することもできます。数式は常に特定の *math version* で組版され、`\mathversion` コマンドで数式モード外からバージョンを切り替えることができます。

標準では *normal* と *bold* の二つのバージョンが用意されています。パッケージによってはさらに多くのバージョンが提供されます。たとえば *mathtime* パッケージは *heavy* バージョンを定義し、**MathTime** フォントの超太字シンボルで式を組版できます。

デフォルトの math version は `\mathversion{normal}` です。`bold` バージョンは文字や記号を太くしますが、`\sum` のような大きな演算子はデフォルトでは変わりません。以下の例は同一式を normal と bold で比較したものです。

```tex
\begin{equation}
  \sum_{j=1}^{z} j = \frac{z(z+1)}{2}
\end{equation}
\mathversion{bold}
\begin{equation}
  \sum_{j=1}^{z} j = \frac{z(z+1)}{2}
\end{equation}
```

![Math versions](/tex/images/java/tutorial/latex-ams-math-8-13.png)

`\mathversion` は見出しなどで有用ですが、バージョンを変えると式全体の外観・意味が変わる可能性があることに留意してください。個々の記号や文字だけを太くしたい場合は `\mathbf` や `\bm` パッケージの `\bm` コマンドを使用すべきです。

バージョン変更時、LaTeX は内部テーブルを参照して新しいバージョン用のシンボルを探します。その過程で、各 math alphabet identifier が別のフォント形状に再割り当てされることがあります。

カスタム identifier（例：`\msfsl`）は、`\DeclareMathAlphabet` で定義していればすべての math version で同じままです。特定のバージョンで別フォントにしたい場合は `\SetMathAlphabet` を使用します。たとえばデフォルト設定では次のようになっています。

```tex
\DeclareMathAlphabet{\mathsf}{OT1}{cmss}{m}{n}
\SetMathAlphabet{\mathsf}{bold}{OT1}{cmss}{bx}{n}
```

1 行目は *normal* と *bold* 両方のバージョンで **Computer Modern Sans** medium をデフォルトにします。2 行目は *bold* バージョンで **Computer Modern Sans** bold extended に切り替える指示です。

`\SetMathAlphabet` の書式は

```tex
\SetMathAlphabet{cmd}{version}{encoding}{family}{series}{shape}
```

です。`math alphabet identifier` を `\DeclareMathAlphabet` で再定義すると、以前の `\SetMathAlphabet` 設定はすべて削除され、以降は新しい定義がすべてのバージョンで適用されます。

## 8.4. AMS‑LATEX パッケージでのフォント調整

*amsfonts*（および *amssymb*）パッケージは二つの math alphabet を定義します：Euler フラクトゥール alphabet（`\mathfrak`） と Blackboard Bold alphabet（`\mathbb`）。例を示します。

```tex
\usepackage{amsfonts}
% -------------------------------------------------------------------------------
$ \forall n \in \mathbb{N} : \mathfrak{M}_n \leq \mathfrak{A} $
```

![amsfonts math alphabet identifiers](/tex/images/java/tutorial/latex-ams-math-8-14.png)

## 5. 太字数式フォントスタイル — `bm` パッケージ

ラテン文字だけであれば `\mathbf` を使えますが、その他の文字は `bm` パッケージを利用します。`\bm` をロードすれば、利用可能なフォントで式全体を太字にできます。

以下の例は `\bm` と `\mathbf` の多様な使い方を示し、` \newcommand` と `\bmdefine` によるショートカット定義も紹介しています。`\mathbf{xy}` と `\bm{xy}` は同一ではなく、前者は太字ローマン **xy**、後者は **bold math italic** の ***xy*** を生成します。

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

![Using the bm package](/tex/images/java/tutorial/latex-ams-math-8-15.png)

この例では `bm` が個々のシンボルや文字の太字化を試みますが、必ずしも完璧ではありません。たとえば和・積演算子は *poor man's bold*（微小なオフセットで 3 回重ね印刷）で実装され、波括弧は全く太字化されません。これは **Computer Modern** 数式フォントに太字バリアントが存在しないためです。

`\bm` がシンボルを太字にする際のルールは次の通りです。まず `\boldmath` で利用できる **bold math version** を確認し、対象シンボルのフォントが *normal* バージョンと異なる場合はその太字フォントを直接使用します。フォントが同一の場合は *poor man's bold* を適用します。

> `bm` パッケージは、フォント設定を変更するパッケージの **後** にロードしてください！

デリミタ（例：`\biggl\lbrace`）は特に複雑です。TeX は要求された高さに合わせたグリフをサイズ系列から選びますが、サイズごとに太字バリアントが存在しないことがあります。**Computer Modern** では最小サイズだけが太字で、他は太字がないフォントから取得されます。

```tex
\usepackage{bm}
% -------------------------------------------------------------------------------
$\bm{\Biggl\lbrace\biggl\lbrace\Bigl\lbrace\bigl \lbrace \lbrace
  \mathcal{Q}
  \rangle \bigr\rangle\Bigr\rangle\biggr\rangle
\Biggr\rangle}$
```

![Delimiters made (and not made) bold by the \bm command](/tex/images/java/tutorial/latex-ams-math-8-16.png)

`\bm` の引数に別の引数付きコマンドが含まれる場合、そのコマンド全体を `\bm` の引数に入れる必要があります。部分的にだけ太字にしたい場合は、太字にしたくないシンボルを `\mbox` で囲み、内部で `\unboldmath` を使って math version をリセットします。`\mbox` は *Ordinary* クラスのシンボルとみなされるため、間隔が正しくなるように `\mathbin`、`\mathrel`、`\mathop` で囲む必要があります。

```tex
\usepackage{amsmath,bm}
% -------------------------------------------------------------------------------
$ \bm{\sqrt[2]{x \times \alpha}} $ but
$ \bm{\sqrt[2]{x \mathbin{\mbox{\unboldmath$\times$}} \alpha}} $
or the similar
$ \bm{\sqrtsign}{\bm{x} \times \bm{\alpha}} $
```

![\bm with commands that take arguments](/tex/images/java/tutorial/latex-ams-math-8-17.png)

実務上はこのように複雑にする必要はまれです。引数を持つコマンドが `\bm` に入る場合でも、必要な部分だけを太字にすれば十分です。たとえば `\sqrtsign` のように、アクセントの引数だけを外側に出すことが許可されています。頻繁に使用するアクセントは独自のショートカットを定義すると便利です。

***パフォーマンス向上***

`\bmdefine\bpi{\pi}` は単なる `\newcommand\bpi{\bm{\pi}}` の省略形に見えますが、実際は逆です。`\bmdefine` は内部で隠しコマンドを生成し、すぐにそのコマンドで太字シンボルを出力します。したがって、`\bm{\alpha}` のように頻繁に使用する場合は、プリアンブルで `\bmdefine\balpha{\alpha}` を定義しておくと、毎回新たに重い処理を行う必要がなくなります。

```tex
\usepackage{bm}
\bmdefine\bhat{\hat}
% -------------------------------------------------------------------------------
$\hat a \neq \bm{\hat a} \neq \bm\hat a = \bhat a\neq \bm\widehat a$
```

![Optimized making accents bold with the \bm command](/tex/images/java/tutorial/latex-ams-math-8-18.png)

この例は、可変幅アクセント（`\widehat` など）もデリミタと同様に、**Computer Modern** の設定では太字バリアントが存在しないことを示しています。
