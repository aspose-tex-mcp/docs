---
translation: true
template: /templates/_template-java.md
linktitle: LaTeX 数学記号
title: 9. 数式における記号
weight: 90
url: /java/latex-math-symbols/
keywords: ams-latex、amsmath、amsfonts、amssymb、LaTeX 数学記号クラス、stmaryrd パッケージ、st mary road フォント
description: LaTeXの数式記号を網羅した辞書です。標準TeX（LaTeX）のコマンドとamssymbパッケージを使用して、ギリシャ文字、二項演算子、関係式、区切り文字をプログラムでレンダリングする方法を学びましょう。
lastmod: "2026-05-29"
---

{{<section overview>}}

この記事の表は、AMS‑LATEX パッケージが提供する多数の数学記号と、各記号にアクセスするコマンドを一覧にしたものです。さらに、Allan Jeffrey と Jeremy Gibbons がデザインした **St Mary Road** フォントからの補助記号も含まれています。このパッケージは **Computer Modern** と AMS 記号フォントコレクションを拡張し、通常は `amssymb` と一緒に、ただし `amssymb` の後にロードする必要があります。関数型プログラミング、プロセス代数、領域理論、線形論理などの分野で追加記号が利用できます。

表では、各記号コマンドを使用するために必要な追加パッケージが示されています。黒字で書かれたコマンド名は標準 LaTeX で利用可能です。青字で書かれたコマンド名は `amsmath`、`amssymb`、または `stmaryrd` のいずれかのロードが必要です。必要に応じて、以下のマークが付加されています：<sup>(*StM*)</sup> は同じ表に他のパッケージの記号も含まれる場合の `stmaryrd` 由来記号、<sup>(*kernel*)</sup> は標準 LaTeX でも利用できるが二つ以上のグリフを組み合わせて得られる記号、<sup>(*var*)</sup> は [数学アルファベット識別子](/tex/{{lang.url-fragment}}java/latex-math-fonts/#81-math-alphabet-identifiers) のスコープ内で外観が変わる「アルファベット記号」を示します。

## 9.1. LaTeX 数学記号クラス

数学記号の一次分類は、技術的な使用目的に関連しています。数学組版において、この分類は数式のレイアウトを決定します。特に、TeX の数式フォーマッタは各記号の「数学クラス」に応じて左右の水平スペースを自動的に調整します。この分類は、アクセントと単なる記号の区別や、膨大な *Relation* 記号のリストをいくつかの表に分割するなど、より細かな区別も行います。

数学では記号は次のクラスのいずれかに分類されます：*Ordinary*（Ord）、*Operator*（Op）、*Binary*（Bin）、*Relation*（Rel）、*Opening*（Open）、*Closing*（Close）、*Punctuation*（Punct）。クラスは `\mathord`、`\mathop`、`\mathbin`、`\mathrel`、`\mathopen`、`\mathclose`、`\mathpunct` コマンドで明示的に変更できます。次の例では、既定で Ord である `\#` と `\top` を Rel と Op に変更しています。

```tex
\usepackage[fleqn]{amsmath}
\[ a \# \top _x^\alpha x^\alpha_b \]
\[ a \mathrel{\#} \mathop{\top}_x^\alpha x^\alpha_b \]
```

![Explicitly changing the symbol class](/tex/images/java/tutorial/latex-ams-math-9-1.png)

さらに、分数や `\left`、`\right` によって生成されるサブ式は *Inner* というクラスに属し、`\mathinner` コマンドで明示的に利用できます。

![Symbol classes and spacing](/tex/images/java/tutorial/latex-ams-math-9-2.png)

> 表では「0」は「スペースなし」、「1」は `\thinmuspace`、「2」は `\medmuskip`、「3」は `\thickmuskip`、「*」は「不可能」を意味します。太字のエントリは数式スクリプトスタイルではその間隔が追加されないことを示しています。

TeX は数式内の各オブジェクトのクラスを判別し、前表で定義された隣接オブジェクト間にスペースを自動的に挿入します。この表は TeX の数式組版ルーチンにハードコードされており、マクロパッケージで変更することはできません。

*Binary* 記号は、前後に二項演算に適合しない記号がある場合 *Ordinary* 記号に変換されます。そのため表のいくつかのエントリは「不可能」とマークされています。例えば、`$+x` は単項プラス（unary plus）であり `+ x` ではありません。後者は `${}+x` と書くことで得られます。

---

以下の式ではデフォルト値を変更して追加されたスペースをより明確に示しています。

```tex
thinmuskip=10mu \medmuskip=17mu \thickmuskip=30mu
% -------------------------------------------------------------------------------
\[
a - b = -\max \{ x , y \}
\]
```

![\thinmuskip, \medmuskip, and \thickmuskip](/tex/images/java/tutorial/latex-ams-math-9-3.png)

TeX はオブジェクトを Ord、Bin、Ord と識別し、以下のようにスペースを挿入します。

```
 A      -      b      =      -    \max   \{   x    ,       y   \}
Ord \: Bin \: Ord \; Rel \; Ord \, Op   Open Ord Punct \, Ord Close
```

`\max` の前のマイナスは *Relation* の後に続くことができないため *Ordinary* に変換されます。

`\left … \right` 構文では、構文で区切られたサブ式全体が *Inner* クラスの単一オブジェクトになります。一方、`\Bigl` や `\Bigr` はそれぞれ *Opening* と *Closing* の個別シンボルを生成します。これらの違いは上記のスペーシング表に現れます。垂直サイズが同じであっても、隣接オブジェクトに応じてスペースが変化します。たとえば *Ordinary* の後に *Opening* が来るとスペースはありませんが、*Ordinary* の後に *Inner* が来ると細いスペースが入ります。`\left … \right` の内部スペースは期待通りに生成され、*Opening* 記号で始まり *Closing* 記号で終わります。

```tex
\thinmuskip=10mu \medmuskip=17mu \thickmuskip=30mu
% -------------------------------------------------------------------------------
\[ a \Bigl( \sum x \Bigr) \neq a \left( \sum x \right) \]
```

![\left...\right and \Bigl...\Bigr](/tex/images/java/tutorial/latex-ams-math-9-4.png)

要約すると、表で記号を探すだけでなく、目的のクラスに属しているかを確認したほうが安全です。

## 9.2. 文字、数字、およびその他の *Ordinary* 記号

アクセントの付いていない ASCII ラテン文字とアラビア数字はすべて「アルファベット記号」と呼ばれます。使用されるフォントは可変です。数式中ではラテン文字は斜体、数字は立体（ローマン体）がデフォルトです。すべてのアルファベット記号は *Ordinary* クラスです。

![Symbols of class \mathord (Greek)](/tex/images/java/tutorial/latex-ams-math-9-5.png)

ラテン文字とは異なり、数学用ギリシア文字は通常のギリシア文字とはフォントが異なります。18 世紀の偶然によって、欧州数学組版の主流では小文字ギリシア文字は斜体、 大文字ギリシア文字は立体（ローマン体）になっています（物理学や化学では若干違う伝統があります）。

以下の表の最上段にある大文字ギリシア文字もフォントが可変で、デフォルトは立体（ローマン体）です。ラテン文字と形が同じギリシア文字（例：*A* と *Alpha*、*B* と *Beta*、*K* と *Kappa*、*O* と *Omicron*）は表に含まれていません。小文字のオミクロンも同様に存在しません。実際にラテン文字に似たギリシア文字は数式では使用されません。

![Greek letters](/tex/images/java/tutorial/latex-ams-math-9-6.png)

> 青字の記号は `amssymb` パッケージが必要です。<sup>(*var*)</sup> は可変なアルファベット記号を示します。

次の表は *Ordinary* クラスの文字形状記号をまとめたものです。最初の 4 つはヘブライ文字です。

![Symbols of class \mathord (letter-shaped)](/tex/images/java/tutorial/latex-ams-math-9-7.png)

> 青字の記号は `amssymb` パッケージが必要です。

次の表は残りの *Ordinary* 記号（句読点を含む）を示します。これらは文字や数字と同様に扱われ、余分なスペースが付加されません。

![Symbols of class \mathord (miscellaneous)](/tex/images/java/tutorial/latex-ams-math-9-8.png)

> 青字の記号は `amssymb` パッケージ、または <sup>(*StM*)</sup> が付いた場合は `stmaryrd` パッケージが必要です。

> 感嘆符、句点、疑問符は数式中では句読点として扱われません。

> 同義語: 論理否定 – `\lnot`, `\neg`; `|` – `\vert`, `|`; `||` – `\Vert`, `\|`.

よくある誤りは、これらの記号を *Binary* 演算子や *Relation* 記号として直接使用し、適切な数学記号コマンドを介さないことです。たとえば `\#`、`\square`、`\&` などのコマンドを使う場合、正しい記号間スペースが得られるか注意し、可能であれば自分で記号コマンドを定義した方が良いでしょう。

```tex
\usepackage[fleqn]{amsmath} \usepackage{amssymb}
\DeclareMathSymbol\bneg {\mathbin}{symbols}{"3A}
\DeclareMathSymbol\rsquare{\mathrel}{AMSa}{"03}
% -------------------------------------------------------------------------------
\[ a \neg b \qquad x \square y + z \]
\[ a \mathbin{\neg} b \qquad x \mathrel{\square} y + z \]
\[ a \bneg b \qquad x \rsquare y + z \]
```

![Declaring math symbols](/tex/images/java/tutorial/latex-ams-math-9-9.png)

`\DeclareMathSymbol` コマンドは独自の記号名を宣言するために使用します。

```tex
\DeclareMathSymbol{cmd}{type}{symbol-font}{slot}
```

第1引数は希望するコマンド名、第2引数は記号クラスを表すコマンドのいずれか、第3引数は記号が格納されているフォント、第4引数はフォントエンコーディング中の位置（10 進、8 進、16 進のいずれか）です。正しい値は `amssymb.sty` や `fontmath.ltx`（コア記号向け）を参照すると簡単に見つかります。たとえば `\neq` と `\square` を調べ、`\mathord` をそれぞれ置き換えて新しい名前を付けました。

## 9.3. 数学アクセント

下表は数式で使用できるアクセントコマンドを列挙しています。ほとんどは標準 TeX で定義されています。拡張可能なアクセントに関する情報は [ここ](/tex/{{lang.url-fragment}}java/latex-math-extensible-symbols/#52-symbols-that-are-horizontally-extensible) を参照してください。アクセント付き記号は *Ordinary* クラスの記号になります。

![Mathematical accents, giving sub-formulas of class \mathord](/tex/images/java/tutorial/latex-ams-math-9-10.png)

> 青字のアクセントは `amsmath` パッケージが必要です。

> 最後の 2 つのアクセントは幅のバリエーションがあり、最も適した幅が自動的に選択されます。

```tex
\usepackage{amstext}
% -------------------------------------------------------------------------------
\[ a = b \text{ but } a \tilde{=} b
\text{ which is not } a \mathrel{\tilde{=}} b \]
```

![Making a Relation symbol from an accented symbol](/tex/images/java/tutorial/latex-ams-math-9-11.png)

他の *Relation* 記号上にシンボルを配置する方法は [ここ](/tex/{{lang.url-fragment}}java/latex-math-decorations/#47-other-decorations) にあります。*i* や *j* にアクセントを付ける場合は、ドットなしのバリアント `\imath` と `\jmath` を使用するのが最良です。

## 9.4. *Binary* 演算子記号

*Binary* クラスの記号は 100 種類以上あり、以下の表に主に掲載しています。一部は別名で *Relation* 記号としても利用可能です。

![Symbols of class \mathbin (miscellaneous)](/tex/images/java/tutorial/latex-ams-math-9-12.png)

> 青字の記号は `amssymb` パッケージ、または <sup>(*StM*)</sup> が付いた場合は `stmaryrd` パッケージが必要です。

> 左右の三角形は *Relation* 記号としても利用できます。

> `stmaryrd` パッケージは *Binary* 記号 `\bigtriangleup` と `\bigtriangledown` を *Operator* に変換し、*Binary* 版は `\varbigtriangleup`、`\varbigtriangledown` となります。

`amssymb` パッケージは箱記号をいくつか提供し、`stmaryrd` がさらに多くを追加します。次の表をご覧ください。

![Symbols of class \mathbin (boxes)](/tex/images/java/tutorial/latex-ams-math-9-13.png)

> これらの記号はすべて `amssymb` パッケージ、または <sup>(*StM*)</sup> が付いた場合は `stmaryrd` パッケージが必要です。

`stmaryrd` パッケージを `heavycircles` オプション付きでロードすると、次の表で `\var` で始まる円記号コマンドは対応する非 `\var` バリアントと定義が入れ替わります。例として `\varodot` は `\odot` になり、逆も同様です。

![Symbols of class \mathbin (circles)](/tex/images/java/tutorial/latex-ams-math-9-14.png)

> 青字の記号は `amssymb` パッケージ、または <sup>(*StM*)</sup> が付いた場合は `stmaryrd` パッケージが必要です。

> `stmaryrd` の `heavycircles` オプションは `\var` で始まるすべてのコマンドとその通常形に影響します。

## 9.5. Relation 記号

*Relation* 記号は *Binary* 演算子よりもさらに多数あります。次の表は等号と順序に関する記号を列挙しています。任意の *Relation* 記号の前に `\not` を付けることで斜線を入れた否定形を作れます。否定形は元の関係の補集合（または否定）を表します。

![Symbols of class \mathrel (equality and order)](/tex/images/java/tutorial/latex-ams-math-9-15.png)

> 青字の記号は `amssymb` パッケージ、または <sup>(*StM*)</sup> が付いた場合は `stmaryrd` パッケージが必要です。

```tex
$ u \not< v$ or $a \not\in \mathbf{A} $
```

![Negating a relation](/tex/images/java/tutorial/latex-ams-math-9-16.png)

この汎用的な否定方法は特に大きな記号では見た目が良くないことがあります。斜線のサイズ・位置・傾きが一定のためです。そのため、特別にデザインされた「否定記号」も用意されています。次の表をご参照ください。

![Symbols of class \mathrel (equality and order‑negated)](/tex/images/java/tutorial/latex-ams-math-9-17.png)

> 青字の記号は `amssymb` パッケージが必要です。

選択肢がある場合は、特別にデザインされたグリフを使用する方が望ましいです。以下の例で違いをご確認ください。

```tex
\usepackage{amssymb}
% -------------------------------------------------------------------------------
$ \not\leq \ \not\succeq \ \not\sim $ \par
$ \nleq \ \nsucceq \ \nsim $
```

![Compound and specially designed negated Relation symbols](/tex/images/java/tutorial/latex-ams-math-9-18.png)

次の表は集合や包含に関する *Relation* 記号を示します。

![Symbols of class \mathrel (sets and inclusion)](/tex/images/java/tutorial/latex-ams-math-9-19.png)

> 青字の記号は `amssymb` パッケージ、または <sup>(*StM*)</sup> が付いた場合は `stmaryrd` パッケージが必要です。

続いて、集合・包含に対する否定形を示します。

![Symbols of class \mathrel (sets and inclusion‑negated)](/tex/images/java/tutorial/latex-ams-math-9-20.png)

> 青字の記号は `amssymb` パッケージが必要です。

次の表は矢印形の *Relation* 記号です。合成矢印記号を生成する拡張可能矢印構文は [ここ](/tex/{{lang.url-fragment}}java/latex-math-extensible-symbols/#52-symbols-that-are-horizontally-extensible) に記載されています。

![Symbols of class \mathrel (arrows)](/tex/images/java/tutorial/latex-ams-math-9-21.png)

> 青字の記号は `amssymb` パッケージ、または <sup>(*StM*)</sup> が付いた場合は `stmaryrd` パッケージが必要です。

以下は矢印形の否定記号です。

![Symbols of class \mathrel (arrows‑negated)](/tex/images/java/tutorial/latex-ams-math-9-22.png)

> 青字の記号は `amssymb` パッケージが必要です。

*Relation* 記号全般を否定・拡張するために特別に設計された他の要素もあります。次の表をご覧ください。

![Symbols of class \mathrel (negation and arrow extensions))](/tex/images/java/tutorial/latex-ams-math-9-23.png)

> 青字の記号は `stmaryrd` パッケージが必要です。

> これらは主に矢印と組み合わせて使用します。例：`\longarrownot\longleftarrow`。

> `\joinrel` を使って関係記号を「接合」できます。例：`\lhook\joinrel\longrightarrow`。

> これらの記号はサイズが大きく、他の用途には不向きです。

```tex
\usepackage{stmaryrd}
% -------------------------------------------------------------------------------
$\Longarrownot\longleftrightarrow \qquad \arrownot \hookleftarrow$
```

![Arrow negations](/tex/images/java/tutorial/latex-ams-math-9-24.png)

最後に、その他の雑多な *Relation* 記号を示します。

![Symbols of class \mathrel (miscellaneous))](/tex/images/java/tutorial/latex-ams-math-9-25.png)

> 青字の *Relation* 記号は `amssymb` パッケージが必要です。

> `\therefore` は *Relation* 記号であるため、一般的な使用において期待どおりの間隔が取れないことがあります。
