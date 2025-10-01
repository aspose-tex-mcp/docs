---
translation: true
template: /templates/_template-java.md
linktitle: レイアウトの調整を提示します
title: 7.レイアウトの調整を推進
weight: 70
url: /java/latex-math-fine-tuning/
keywords: AMS-Latex、AMSMATH、LATEX MATH SPACING、LATEX MATH STYLES、LATEX MATH DELIMITERS、LATEX MATH PARENTES、LATEX MATH ALIGNMENT
description: この記事では、数学レイアウトの微調整 - 自動サイジングと間隔、大規模なデリミター、正確なアライメントについて説明します。
lastmod: "2025-06-09"
---

{{<section overview>}}

通常、LaTexは数式をレイアウトするという素晴らしい仕事をします。ただし、ポジショニングのより細かい調整が必要な場合があります。この記事では、レイアウトを微調整して数式を少し良くするためのいくつかの手法について説明します。

## 7.1。自動サイジングと間隔

数学のシンボルと文字は、通常、分数、添え字、または上付き文字に表示されるときに(そしてより厳しい間隔で)小さくなります。数式の式は、8つのTex Math Styleでレイアウトできます。

||||
|---|---|---|
| *D、D'* | `\displaystyle`| 行に単独で表示 |
| *T、T'* | `\textstyle`| テキストに埋め込まれる |
| *S、S'* | `\scriptstyle`| 上付き文字または下付き文字内 |
| *SS、SS'* | `\scriptscriptstyle`| すべての高次の上付き文字または下付き文字内 |

テキストスタイル (*T*) は、本文中に設定される数式の最上位レベル（`$` の間、または `\(` と `\)` の間）で使用され、表示スタイルは、表示される数式の最上位レベル（`$$` の間、または `\[` と `\]` の間）で使用されます。サブ数式については、以下の表からスタイルを決定できます。

||||||
|---|---|---|---|---|
| *D* | *S* | *S'* | *T* | *T'* |
| *D'* | *S'* | *S'* | *T'* | *T'* |
| *T* | *S* | *S'* | *S* | *S'* |
| *T'* | *S'* | *S'* | *S'* | *S'* |
| *S, SS* | *SS* | *SS'* | *SS* | *SS'* |
| *S', SS'* | *SS'* | *SS'* | *SS'* | *SS'* |

次の例は、さまざまなスタイルを示しています。

```tex
\normalsize                 %% Style:
\[ b                        %% D
    ^0                      %% S
   +                        %% D
   \frac{(k + p)            %% T
          _{j'}             %% S'
         % \displaystyle
         \pm                %% T [D]
         \frac{(f + q)      %% S [T]
                ^{(pk)      %% SS [S]
                   ^y       %% SS
                   _{j'}}}  %% SS'
              {(h + y)}}    %% S' [T']
        {(l + q)            %% T'
          ^{(pk)}}          %% S'
\]
```

![さまざまな数学スタイル](/tex/images/java/tutorial/latex-ams-math-7-1.png)

`\ displaystyle`の前にコメントchar( `％`)を削除し、括弧内のスタイルの一部にどのように変更されたかを確認できます。

![数学スタイルを明示的に変更しました](/tex/images/java/tutorial/latex-ams-math-7-2.png)

各パートで使用するスタイルを明示的に指定する方法を示しています。

## 7.2。サブ式

テキストでは、一対のブレースがグループ、または範囲を示しており、宣言が有効になっています。数学の式では、それらはさらに、サブフォーマーを区切ります。サブフォーマーは、常に外側のフォーミュラに追加された別のエンティティとして版画されています。結果として、サブフォーマーは常に自然幅でタイプセットされ、Texが式に合わせて段落を構築するときに水平に伸びたり縮小したりしないでください。単純なブレースグループのサブフォーマーは、単一のシンボルであるかのように処理されていることをすでに示しています。これは、空のグループが間隔を変更できる目に見えないシンボルを生成することを意味します。

`\frac` や `\mathrel` など、多くの（ただしすべてではない）コマンドの下付き文字/上付き文字の内容や引数も、部分式です。したがって、これらも同様に特別な扱いを受けます。例えば、`\bm` の引数は必ずしも部分式として設定する必要はなく、これは重要な例外の一つです。数式において、宣言のスコープを限定したいだけの場合は、`\begingroup` と `\endgroup` を使用してグループを定義します。スタイル変更などの特殊な数式宣言は、他のグループの有無にかかわらず、現在の部分式の最後まで適用されることに注意してください。

## 7.3. 大きな区切り文字

LaTeX は、拡張可能な区切り文字のサイズを直接制御するために、`\big`、`\Big`、`\bigg`、`Bigg` という 4 つのコマンドを定義しています。これらは、拡張可能な区切り文字である単一の引数を取り、基本サイズの 1.2 倍から 3 倍までの区切り文字のより大きなバージョンを生成します。

4つのコマンドにはそれぞれ3つのバリエーションがあり、*開始記号*（`\bigl`、`\Bigl`、`\biggl`、`\Biggl`）の4つのサイズ、*関係記号*（`\bigm`、`\Bigm`、`\biggm`、`\Biggm`）の4つのサイズ、そして*終了記号*（`\bigr`、`\Bigr`、`\biggr`、`\Biggr`）の4つのサイズが存在します。これら16個のコマンドはすべて、`\left`、`\right`、または（eTeXの場合）`\middle` の後に続く任意の記号で使用する必要があります（この[表](/tex/{{lang.url-fragment}}java/latex-math-extensible-symbols#53-symbols-that-are-vertical-extensible)を参照してください）。 

これらの区切り文字のサイズは、標準のラテックスで固定されています。ただし、`Amsmath`パッケージを使用すると、使用中のフォントサイズと数学スタイルに応じて、サイズが周囲の素材のサイズに適応します。これを以下の例に示します。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\[ \biggl( \mathbf{E}_{y} \int_0^{t_\varepsilon}
   L_{x, y^x(s)} \varphi(x)\, ds \biggr) \]
\Large
\[ \biggl( \mathbf{E}_{y} \int_0^{t_\varepsilon}
   L_{x, y^x(s)} \varphi(x)\, ds \biggr) \]
```

![現在のフォントサイズと数学スタイルに適応する区切り文字](/tex/images/java/tutorial/latex-ams-math-7-3.png)

## 7.4。ラジカルでインデックスを調整します

標準的なLaTeXでは、根号記号上のインデックスの配置が必ずしも適切とは限りません。しかし、`amsmath`パッケージで定義されているコマンド`\leftroot`と`\uproot`を使えば、このインデックスの位置を調整できます。これらのコマンドに正の整数引数を与えると、インデックスはそれぞれ左と上に移動し、負の引数を与えると右と下に移動します。これらの引数は非常に小さい数式単位で与えられるため、これらのコマンドは微​​調整に適しています。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\[
  \sqrt[\beta]{k} \qquad
  \sqrt[\leftroot{2}\uproot{4} \beta]{k} \qquad
  \sqrt[\leftroot{1}\uproot{3} \beta]{k}
\]
```

![ラジカルサインのインデックスの調整](/tex/images/java/tutorial/latex-ams-math-7-4.png)

## 7.5。ストラットとファントムで微調整

数式における行間や配置を「完璧に」組版したい場合は、プリミティブTeX独自の高度な機能を活用するのが最善です。これらの機能は、`\phantom`と`\smash`に関連するいくつかのコマンドによって利用できます。これらのコマンドは、数式内でも本文中でも使用できます。

次の例を見てみましょう。

```tex
\usepackage{amsmath}
\newcommand\relphantom[1]{\mathrel{\phantom{#1}}}
\newcommand\ve{\varepsilon} \newcommand\tve{t_{\varepsilon}}
\newcommand\vf{\varphi} \newcommand\yvf{y_{\varphi}}
\newcommand\bfE{\mathbf{E}}
% -------------------------------------------------------------------------------
\begin{equation} \begin{split}
  f_{h, \ve}(x, y)
    &= \ve \bfE_{x, y} \int_0^{\tve} L_{x, \yvf(\ve u)} \vf(x) \,du  \\
    &= h \int L_{x, z} \vf(x) \rho_x(dz)                             \\
    &\relphantom{=} {} + h \biggl[
       \frac{1}{\tve}
       \biggl( \bfE_{y} \int_0^{\tve}  L_{x, y^x(s)} \vf(x) \,ds
               - \tve \int L_{x, z} \vf(x) \rho_x(dz)      \biggr) + \\
    &\relphantom{=} \phantom{{} + h \biggl[ }
       \frac{1}{\tve}
       \biggl( \bfE_{y} \int_0^{\tve}  L_{x, y^x(s)} \vf(x) \,ds
               - \bfE_{x, y} \int_0^{\tve} L_{x, \yvf(\ve s)}
                                            \vf(x) \,ds    \biggr) \biggr]
\end{split} \end{equation}
```

![フォーミュラのファントム](/tex/images/java/tutorial/latex-ams-math-7-5.png)

ここで、`\phantom` コマンドは水平位置を調整します。プリアンブルでは、引数（この例では `=`）と同じ幅を持つ非表示の関係記号を定義しています。数式環境では、特定の行を「ファントム」、つまり非表示の部分式で開始することで、行の位置を揃えるために使用されます。空の括弧 `{}` は `\mathord{}` と同じで、これは "+ *h*" の正しい間隔を確保するために必要な、幅がゼロの非表示記号を生成します（`{}` がない場合、プラス記号は *h* の前に不適切な間隔を持つ単項プラス記号を生成します）。

`\phantom` とは対照的に、コマンド `\smash` は内容を（LR ボックス内に）タイプセットしますが、高さと幅の両方をゼロであるかのように無視します。標準 LaTeX で定義されているコマンド `\hphantom` は、これら 2 つの組み合わせです。これは `\smash{\phantom{some phantom contents}}` と同等のもの、つまり高さと奥行きがゼロで幅がファントム コンテンツと同じ非表示のボックスを生成します。

`\vphantom` コマンドも同様ですが、ファントムの幅をゼロにして、高さと奥行きの合計を維持します。`\mathstrut` コマンドは `\vphantom(` として定義され、高さと奥行きが括弧と同じ幅ゼロのボックスを生成します。

`amsmath` パッケージを使用すると、`\smash` コマンドはオプションの引数を取ることができます。`\smash[t]{...}` はボックスの内容の高さを無視して奥行きを維持しますが、`\smash[b]{...}` は奥行きを無視して高さを維持します。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
$\sqrt{x} + \sqrt{y} + \sqrt{z}$ \\
$\sqrt{x} + \sqrt{\mathstrut y} + \sqrt{z}$ \\
$\sqrt{x} + \sqrt{\smash{y}} + \sqrt{z}$ \\
$\sqrt{x} + \sqrt{\smash[b]{y}} + \sqrt{z}$
```

![根本的な表現を破壊します](/tex/images/java/tutorial/latex-ams-math-7-6.png)

*y* に支柱で高さを少し加えると、部首が似て見えるように見えます。しかし、実際には、部首の見た目が異なり、全体的に醜く見えるだけです。結局、*y* の下部を潰すのが最善の方法であることがわかりました。

次の例は、潰しの非常に一般的な使用例を示しています。`\smash` コマンドは、周囲の区切り文字の高さを細かく制御するために使用されています。また、行の実際の高さを知る必要があるため、潰しが問題を引き起こす可能性があることも示しています。これは `\vphantom` によって修正されます。`\Hmjd` は、次のように定義される複合記号です。


```tex
\newcommand\Hmjd{\widetilde{\mathcal{H}^2}_{MJD}(\chi)}
```

結果の垂直スペースを表示するには、ルールを追加しました。

| *Appearance* | `Code` | *Comment* |
|:---:|:---:|---|
| !["Outer Brackets Too Large"](/tex/images/java/tutorial/latex-ams-math-smashing-7-1.png) | `\left( {\Hmjd } \right)` | *Outer brackets too large* |
| !["Outer Brackets Too Small and Rules Too Close"](/tex/images/java/tutorial/latex-ams-math-smashing-7-2.png) | `\left( \smash{\Hmjd } \right)` | *Outer brackets too small and rules too close* |
| !["Just Right"](/tex/images/java/tutorial/latex-ams-math-smashing-7-3.png) |
| *外観* | `コード` | *コメント* |
|:---:|:---:|---|
| !["外側の括弧が大きすぎます"](/tex/images/java/tutorial/latex-ams-math-smashing-7-1.png) | `\left( {\Hmjd } \right)` | *外側の括弧が大きすぎます* |
| !["外側の括弧が小さすぎ、罫線が近すぎます"](/tex/images/java/tutorial/latex-ams-math-smashing-7-2.png) | `\left( \smash{\Hmjd } \right)` | *外側の括弧が小さすぎ、罫線が近すぎます* |
| !["ちょうどいい"](/tex/images/java/tutorial/latex-ams-math-smashing-7-3.png) | `\left( \smash[t]{\Hmjd } \right) \vphantom{\Hmjd}` | *ちょうどいい！* |
| !["Vphantom と部分的スマッシュの両方が必要"](/tex/images/java/tutorial/latex-ams-math-smashing-7-4.png) | `\left( \smash[t]{\Hmjd } \right)` | *`\vphantom` と部分的スマッシュの両方が必要です* |

> 一部の箇所では、低レベルのTeX処理の欠陥により、組版の細部にエラーが発生する可能性があります。これは、(a) 部分式（分数の分子/分母、または下付き/上付き文字）が1つのLRボックス、または同様の構成の数式ボックスで構成され、(b) そのボックスが自然なサイズではない場合（`\makebox`、スマッシュ、および一部のファントムなどのより複雑な形式の場合など）に発生する可能性があります。

これを見るには、次の例を見てみましょう。


```tex
\[
\sqrt{ \frac{a+b}{x_j} } \quad
\sqrt{ \frac{a+b}{\smash{x_j}} } \quad
\sqrt{ \frac{a+b}{{}\smash{x_j}} } \quad
\sqrt{ \frac{a+b}{\smash{x_j+b}} }
\]
```

![スマッシュによって引き起こされる問題](/tex/images/java/tutorial/latex-ams-math-7-7.png)

ラジカルの深さを減らすために、2番目のラジカルに`\ smash`が追加されましたが、これは効果がありませんでした。 3番目のラジカルでは、空のブレースグループと連携しました。  しかし、4番目の過激派では、空のブレースグループは必要ありませんでした。要約すると、`\ smash`が機能しないことがわかったときはいつでも、孤独な箱の前に空の数学サブフォーマー( `{}`)を追加して、それを正しく扱うようにしてください。

## 7.6。水平間隔

より細かく、より困難なチューニングには、次の表に示す明示的な間隔コマンドが必要です。

![水平間隔コマンド](/tex/images/java/tutorial/latex-ams-math-7-8.png)

これらのコマンドの完全なフォームと短いフォームの両方は堅牢であり、通常のテキストでは数式の外で使用することもできます。それらは、20世紀半ばの数学をタイプセットするために使用される機械で利用できる薄く、中程度の、厚いスペースに関連しています。

3つのTeXパラメータ `\thinmuskip`、`\medmuskip`、`\thickmuskip` の現在の値は、これらの `\..space` コマンドによって追加されるスペースの量を定義します。`amsmath` におけるこれらのパラメータのデフォルト値は表に記載されています。これらの低レベルパラメータは、数式単位（*mu*）での値を必要とします。したがって、これらのパラメータは低レベルTeXの代入によってのみ設定でき、`\setlength` などのメソッドでは設定できません。また、これらの値はTeXの数式組版処理で内部的に使用されるため、通常は変更しないでください（次の表を参照）。

![シンボル間の間隔](/tex/images/java/tutorial/latex-ams-math-7-9.png)

> 表中の 0 は「スペースなし」、1 は `\thinmuspace`、2 は `\medmuskip`、3 は `\thickmuskip`、* は「不可能」を意味します。太字で表示されている項目は、対応するスペースが数式フォントスタイルで追加されないことを意味します。

1数式単位（`1mu`）は、現在の数式フォントサイズにおける *em* の 1/18 に相当します。したがって、*mu* の絶対値は数式スタイルによって異なり、使用するスタイルに関わらず一貫したスペースが確保されます。