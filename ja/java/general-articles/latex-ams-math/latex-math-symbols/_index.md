---
translation: true
template: /templates/_template-java.md
linktitle: ラテックス数学記号
title: 9。数式のシンボル
weight: 90
url: /java/latex-math-symbols/
keywords: AMS-Latex、AMSMath、AMSFONTS、AMSSYMB、LATEX MATH SYBOLクラス、STMARYRDパッケージ、StMary Roadフォント
description: Texの数学記号の分類と、標準のTex(LaTex)とAMSSYMBパッケージのコマンドを使用して、さまざまなクラスのシンボルへのアクセスを学びます。
lastmod: "2025-06-09"
---

{{<section overview>}}

この記事の表には、各シンボルにアクセスするコマンドを含む、AMS-Latexパッケージが提供する数学記号の幅広い範囲がリストされています。また、アランジェフリーとジェレミーギボンズが設計した**セントメアリーロード**フォントの補足記号も含まれています。このパッケージは、**コンピューターモダン**およびAMSシンボルフォントコレクションを拡張し、通常は「Amssymb」に加えてロードする必要がありますが、常にその後です。機能プログラミング、プロセス代数、ドメイン理論、線形論理などのフィールドに追加のシンボルを提供します。

表には、各シンボルコマンドを使用するためにロードする必要がある追加パッケージが示されています。コマンド名が黒で表記されているシンボルは、標準 LaTeX で使用できます。コマンド名が青で表記されているシンボルは、`amsmath`、`amssymb`、または `stmaryrd` のいずれかをロードする必要があります。必要に応じて、マークによってさらに分類が示されます。<sup>(*StM*)</sup> は、表に他のパッケージのシンボルも含まれている場合に `stmaryrd` のシンボルを意味します。<sup>(*kernel*)</sup> は、標準 LaTeX で使用できるシンボルですが、指定されたパッケージには単一のグリフしか存在しません。 <sup>(*var*)</sup> は、[数式アルファベット識別子](/tex/{{lang.url-fragment}}java/latex-math-fonts/#81-math-alphabet-identifiers) のスコープ内で使用されると外観が変化する「アルファベット記号」（タイプ `\mathalpha`）を示します。

## 9.1。ラテックス数学記号クラス

数学記号の主要な分類は、技術的な使用におけるその意味に関連しています。数学タイポグラフィでは、この分類により式のレイアウトが定義されています。特に、Texの数学のフォーマッタは、数学クラスに従って各シンボルの両側の水平空間を調整します。また、この分類は、たとえば、アクセントとシンプルなシンボルとの間のいくつかのより細かい区別を作成し、 *関係 *シンボルの膨大なリストをいくつかのテーブルに分割します。

数学の設定では、各記号は*Ordinary* (Ord)、*Operator* (Op)、*Binary* (Bin)、*Relation* (Rel)、*Opening* (Open)、*Closing* (Close)、*Punctuation* (Punct) のいずれかのクラスに分類されます。記号のクラスは、`\mathord`、`\mathop`、`\mathbin`、`\mathrel`、`\mathopen`、`\mathopen`、`\mathpunct` コマンドを使用して明示的に変更できます。次の例では、`\#` と `\top` (どちらもデフォルトでは Ord) が Rel と Op に変更されています。

```tex
\usepackage[fleqn]{amsmath}
\[ a \# \top _x^\alpha x^\alpha_b \]
\[ a \mathrel{\#} \mathop{\top}_x^\alpha x^\alpha_b \]
```

![シンボルクラスを明示的に変更します](/tex/images/java/tutorial/latex-ams-math-9-1.png)

上記のクラスに加えて、特定のサブフォーミュラス - 最も重要なのは分数、および`\ left`および `\ right」によって生成される分数 - は *内側 *と呼ばれるクラスを形成します。

![シンボルクラスと間隔](/tex/images/java/tutorial/latex-ams-math-9-2.png)

> 表中の「0」は「スペースなし」、 「1」は`\thinmuspace`、 「2」は`\medmuskip`、 「3」は`\thickmuskip`、 「*」は「不可能」を意味します。太字で表示されている項目は、対応するスペースが数式スタイルで追加されないことを意味します。

Texは、フォーミュラ内の各オブジェクトのクラスを識別し、前のテーブルで定義されている隣接するオブジェクトの各ペア間にスペースを追加するだけで、式内の間隔を処理します。このテーブルは、Texの数学タイプセッティングルーチンにハードコーディングされているため、マクロパッケージで変更することはできません。

*バイナリ *シンボルは、前に行われず、バイナリ操作と互換性のある自然のシンボルが続くたびに *通常の *シンボルに変わります。そのため、テーブル内のいくつかのエントリが不可能としてマークされています。たとえば、 `$ +x $`は +*x*(unary plus)を与え、 +*x*ではありません。後者は `$ {}+x $`で生成できます。

次の式を考慮してください(デフォルト値が変更されて、追加されたスペースをより明確に表示します)：

```tex
thinmuskip=10mu \medmuskip=17mu \thickmuskip=30mu
% -------------------------------------------------------------------------------
\[
a - b = -\max \{ x , y \}
\]
```

![\ thinmuskip、\ medmuskip、および\ thickmuskip](/tex/images/java/tutorial/latex-ams-math-9-3.png)

Texは、オブジェクトをOrd、Bin、Ordなどとして識別し、次のようにスペースを挿入します。

```
 A      -      b      =      -    \max   \{   x    ,       y   \}
Ord \: Bin \: Ord \; Rel \; Ord \, Op   Open Ord Punct \, Ord Close
```

「\ max」の前のマイナスは、 *バイナリ *が *関係 *に従うことができないため、 *普通 *に変わります。

"`\left...\right`" 構文では、構文で区切られた部分式全体がクラス *Inner* の単一のオブジェクトになります。一方、`\Bigl` や `\Bigr` などのコマンドは、それぞれクラス *Opening* と *Closing* の個別のシンボルを生成します。これらの違いは、上記の間隔表に示されています。これらのコマンドは、垂直方向の区切り文字のサイズが同じになる場合もありますが、式内の隣接するオブジェクトによっては間隔に差が生じる場合があります。例えば、*Ordinary* の後に *Opening* が続く場合は間隔が空けられませんが、*Ordinary* の後に *Inner* が続く場合は、細いスペースで区切られます。"`\left...\right`" 構文内の部分式内のスペースは、*Opening* シンボルで始まり、*Closing* シンボルで終わるという、想定どおりに生成されます。


```tex
\thinmuskip=10mu \medmuskip=17mu \thickmuskip=30mu
% -------------------------------------------------------------------------------
\[ a \Bigl( \sum x \Bigr) \neq a \left( \sum x \right) \]
```

![\左... \右および\ bigl ... \ bigr](/tex/images/java/tutorial/latex-ams-math-9-4.png)

要約すると、シンボルが次のテーブルで調べるだけでなく、シンボルが目的のクラスに属していることを確認することをお勧めします。

## 9.2。文字、数字、およびその他の *通常の *シンボル

アクセントのないASCIIラテン文字とアラビア語の数字はすべて「アルファベットのシンボル」と呼ばれます。タイプされているフォントはさまざまです。数式のフォーミュラでは、ラテン文字のデフォルトのフォントは斜体ですが、アラビア語の数字では直立/ローマです。アルファベットのシンボルはすべてクラス *普通 *です。

![クラスのシンボル\ mathord(ギリシャ語)](/tex/images/java/tutorial/latex-ams-math-9-5.png)

ラテン文字とは異なり、数学的なギリシャ文字は、通常のギリシャ語のテキストを整理するために使用されるグリフと密接に関連していません。好奇心が強い18世紀の出来事により、数学のタイポグラフィの主要なヨーロッパの伝統では、数学の小文字ギリシャ文字のデフォルトのフォントは斜体ですが、大文字のギリシャ文字の場合は直立/ローマです。 (たとえば、物理学と化学では、誤植の伝統はわずかに異なります。)

以下の表の最初の行にあるギリシャ語の大文字もアルファベット記号であり、フォントは様々ですが、デフォルトは直立/ローマン体です。ギリシャ語の大文字の中には、ラテン文字と似た外観を持つものがあります（例：*A*と*Alpha*、*B*と*Beta*、*K*と*Kappa*、*O*と*Omicron*）。これらの文字は表には含まれていません。同じ理由で、小文字のオミクロンもありません。実際には、ラテン文字のように見えるギリシャ文字は数式では使用されません。

![ギリシャの手紙](/tex/images/java/tutorial/latex-ams-math-9-6.png)

> 青色の記号には `amssymb` パッケージが必要です。<sup>(*var*)</sup> は変数のアルファベット記号を示します。

次のテーブルには、クラス *普通 *の他の文字型のシンボルがリストされています。最初の4つはヘブライ語の手紙です。

![クラス\ mathord(文字形式)のシンボル](/tex/images/java/tutorial/latex-ams-math-9-7.png)

> 青色のシンボルには `amssymb` パッケージが必要です

次のテーブルには、一般的な句読点を含む *通常の *クラスの残りの記号がリストされています。これらは文字や数字のように振る舞うので、周囲に余分なスペースを確保することはありません。

![クラス\ mathordのシンボル(その他)](/tex/images/java/tutorial/latex-ams-math-9-8.png)

> 青色で表示されている記号は、`amssymb` パッケージ、または <sup>(*StM*)</sup> フラグが付いている場合は `stmaryrd` パッケージのいずれかが必要です。

> 数式では、感嘆符、ピリオド、疑問符は句読点として扱われないことに注意してください。

> 同義語：論理否定 - `\lnot`、`\neg`; `|` - `\vert`、`|`; `||` - `\Vert`、`\|`。

よくある間違いは、これらのシンボルを、そのタイプに適切に定義された数学記号コマンドを使用せずに、 *バイナリ *演算子または * ellation *シンボルとして直接使用することです。したがって、 `\＃`、 `\ square`、または` \＆ `などのコマンドを使用する場合は、正しいシンボル間スペースを取得するか、さらに良いことに独自のシンボルコマンドを定義することを注意深く確認してください。

```tex
\usepackage[fleqn]{amsmath} \usepackage{amssymb}
\DeclareMathSymbol\bneg {\mathbin}{symbols}{"3A}
\DeclareMathSymbol\rsquare{\mathrel}{AMSa}{"03}
% -------------------------------------------------------------------------------
\[ a \neg b \qquad x \square y + z \]
\[ a \mathbin{\neg} b \qquad x \mathrel{\square} y + z \]
\[ a \bneg b \qquad x \rsquare y + z \]
```

![数学記号を宣言します](/tex/images/java/tutorial/latex-ams-math-9-9.png)

`\ decraremathsymbol`コマンドは、独自のシンボル名を宣言するために使用されます。

```tex
\DeclareMathSymbol{cmd}{type}{symbol-font}{slot}
```

最初の引数は選択したコマンド名です。2番目の引数は、シンボルクラスに対応するコマンドの1つです。3番目の引数は、シンボルを取得するシンボルフォントを指定します。4番目の引数は、フォントエンコーディングにおけるシンボルの位置を、10進数、8進数、または16進数で指定します。引数の正しい値は、ファイル `amssymb.sty` または `fontmath.ltx` (コアシンボルの場合) の定義を参照することで簡単に見つけることができます。例えば、`\neq` と `\square` を検索し、それぞれ `\mathord` を置き換え、最終的に結果のシンボルに新しい名前を付けました。

## 9.3。数学のアクセント

以下の表には、式で使用可能なアクセントコマンドを示します。それらのほとんどは、標準のTexで定義されています。拡張可能なアクセントについては[こちら](/tex/{{lang.url-fragment}}java/latex-math-extensible-symbols/#52-symbols-that-are-horizontally-extensible)を参照してください。シンボルに数学のアクセントを追加すると、結果はクラス *普通 *のシンボルです。

![数学的アクセント、クラス\ Mathordのサブ形式を与えます](/tex/images/java/tutorial/latex-ams-math-9-10.png)

> 青色のアクセントには `amsmath` パッケージが必要です。

> 最後の 2 つのアクセントはさまざまな幅で利用可能で、最も適切な幅が自動的に使用されます。

```tex
\usepackage{amstext}
% -------------------------------------------------------------------------------
\[ a = b \text{ but } a \tilde{=} b
\text{ which is not } a \mathrel{\tilde{=}} b \]
```

![アクセントされたシンボルから関係記号を作成します](/tex/images/java/tutorial/latex-ams-math-9-11.png)

*関係*記号の上に記号を配置する他の方法については、[こちら](/tex/{{lang.url-fragment}}java/latex-math-decorations/#47-other-decorations)を参照してください。数式中の*i*または*j*にアクセント記号を付ける場合は、ドットなしのバリエーションである`\imath`と`\jmath`を使用するのが最適です。

## 9.4。 *バイナリ*演算子シンボル

選択するクラス *バイナリ *のシンボルを100以上あります。それらのほとんどは次の表にリストされています。それらのいくつかは、異なる名前ではありますが、 *関係 *シンボルとしても利用できます。

![クラス\ mathbinのシンボル(その他)](/tex/images/java/tutorial/latex-ams-math-9-12.png)

> 青色で表示されているシンボルは、`amssymb` パッケージ、または <sup>(*StM*)</sup> フラグが付いている場合は `stmaryrd` パッケージのいずれかが必要です。

> 左三角形と右三角形は、*関係* シンボルとしても使用できます。

> `stmaryrd` パッケージは、*二項* シンボル `\bigtriangleup` と `\bigtriangledown` を *演算子* に変換してしまい、*二項* 演算子形式には同義語 `\varbigtriangleup` と `\varbigtriangledown` のみを残してしまうため、混乱を招きます。

`amssymb`パッケージは、 *バイナリ *演算子として使用するためのいくつかのボックスシンボルを提供します。 「stmaryrd」によってさらに多くが追加されます。次のテーブルを参照してください。

![クラス\ mathbin(ボックス)のシンボル](/tex/images/java/tutorial/latex-ams-math-9-13.png)

> すべてのシンボルには、`amssymb` パッケージ、または <sup>(*StM*)</sup> フラグが付いている場合は `stmaryrd` パッケージが必要です。

`stmaryrd`パッケージをオプション「heavycircles」でロードできます。その結果、「var」なしで「\ var」から始まる次のテーブルからの各円記号コマンドが次のテーブルから始まります。たとえば、シンボル「\ varodot」は「\ odot」になり、その逆になります。

![クラス\ mathbin(円)のシンボル](/tex/images/java/tutorial/latex-ams-math-9-14.png)

> 青色で表示されているシンボルは、`amssymb` パッケージ、または <sup>(*StM*)</sup> フラグが付いている場合は `stmaryrd` パッケージのいずれかが必要です。

> `stmaryrd` パッケージのオプション `heavycircles` は、`\var` で始まるすべてのコマンドとその通常のバリエーションに影響します。

## 9.5。関係記号

バイナリ *関係 *シンボルのクラスは、 *バイナリ *演算子のクラスよりも大きくなっています。次のテーブルには、平等と順序のシンボルがリストされています。 「\ not」コマンドを使用して、任意の * ellation *シンボルにスラッシュを配置できます。否定されたシンボルは、関係の補体(または否定)を表します。

![クラス\ mathrel(平等と順序)のシンボル](/tex/images/java/tutorial/latex-ams-math-9-15.png)

> 青色のシンボルには、`amssymb` パッケージが必要です。または、<sup>(*StM*)</sup> フラグが付いている場合は、`stmaryrd` パッケージが必要です。

```tex
$ u \not< v$ or $a \not\in \mathbf{A} $
```

![関係を否定します](/tex/images/java/tutorial/latex-ams-math-9-16.png)

スラッシュは常に同じサイズ、位置、勾配になるため、 *関係 *シンボルを否定するこの一般的な方法は、特により大きなシンボルでは常に良い結果をもたらすとは限りません。このため、いくつかの特別に設計された「否定されたシンボル」も利用可能です。次の表のリストを参照してください。

![クラス\ mathrelのシンボル(平等と秩序の否定)](/tex/images/java/tutorial/latex-ams-math-9-17.png)

> 青色のシンボルには `amssymb` パッケージが必要です。

選択肢がある場合は、通常、特別に設計されたグリフを使用することが望ましいです。理由を確認するには、次の例のシンボルを比較してください。

```tex
\usepackage{amssymb}
% -------------------------------------------------------------------------------
$ \not\leq \ \not\succeq \ \not\sim $ \par
$ \nleq \ \nsucceq \ \nsim $
```

![化合物で特別に設計された否定された関係記号](/tex/images/java/tutorial/latex-ams-math-9-18.png)

次のテーブルには、セットとインクルージョンの *関係 *記号を示します。

![クラス\ mathrelのシンボル(セットと包含)](/tex/images/java/tutorial/latex-ams-math-9-19.png)

> 青色のシンボルには、`amssymb` パッケージが必要です。または、<sup>(*StM*)</sup> のフラグが付いている場合は、`stmaryrd` パッケージが必要です。

そして今、セットと包含のための *関係 *記号の否定。

![クラス\ mathrelのシンボル(セットと包括的関連)](/tex/images/java/tutorial/latex-ams-math-9-20.png)

> 青色のシンボルには `amssymb` パッケージが必要です。

次のテーブルには、矢印型 *関係 *シンボルを示します。化合物 *関係 *記号を生成するいくつかの拡張可能な矢印構造は、[ここ](/tex/{{lang.url-fragment}}java/latex-math-extensible-symbols/#52-symbols-that-are-horizontally-extensible)に記載されています。

![クラス\ mathrel(矢印)のシンボル](/tex/images/java/tutorial/latex-ams-math-9-21.png)

> 青色のシンボルには、`amssymb` パッケージが必要です。または、<sup>(*StM*)</sup> のフラグが付いている場合は、`stmaryrd` パッケージが必要です。

そして、ここに否定された矢印形の *関係 *シンボルがあります。

![クラス\ mathrelのシンボル(矢印関連)](/tex/images/java/tutorial/latex-ams-math-9-22.png)

> 青色のシンボルには `amssymb` パッケージが必要です。

矢印のようなシンボルを無効または拡張するように特別に設計された他の要素(一般的な *関係 *シンボルを無効にするために使用されていない)があります。次のテーブルを参照してください。

![クラス\ mathrelのシンボル(否定と矢印の拡張))](/tex/images/java/tutorial/latex-ams-math-9-23.png)

> 青色のシンボルは `stmaryrd` パッケージが必要です。

> これらのシンボルは、主に矢印と組み合わせて使用​​します。例: `\longarrownot\l​​ongleftarrow`。

> 関係シンボルを「接着」するには、`\joinrel` を使用します。例: `\lhook\joinrel\longrightarrow`。

> これらのシンボルはサイズが大きいため、他の用途には適していません。

```tex
\usepackage{stmaryrd}
% -------------------------------------------------------------------------------
$\Longarrownot\longleftrightarrow \qquad \arrownot \hookleftarrow$
```

![矢印の否定](/tex/images/java/tutorial/latex-ams-math-9-24.png)

最後に、以下は他のその他の *関係 *シンボルです。

![クラスのシンボル\ mathrel(その他)))](/tex/images/java/tutorial/latex-ams-math-9-25.png)

> 青色で表示されている *関係* 記号には `amssymb` パッケージが必要です。

> `\therefore` は *関係* 記号であるため、一般的な使用法では期待どおりの間隔にならない場合があります。
