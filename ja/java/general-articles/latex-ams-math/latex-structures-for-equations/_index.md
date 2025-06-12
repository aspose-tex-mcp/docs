---
translation: true
template: /templates/_template-java.md
linktitle: ラテックス方程式は調整され、表示されます
title: 2。ラテックス方程式の表示とアライメント|ラテックスアライメント *
weight: 10
url: /java/latex-structures-for-equations/
keywords: AMS-Latex、AMSMATH、AMSMATHオプション、ラテックス方程式アライメント、LEQNO、EQNO、FLEQN、LATEX方程式タグ、ラテックス方程式ラベル、ラテックスアライン方程式
description: これは、AMS-Latexパッケージを使用したタイプセットラテックス方程式の紹介であり、いくつかの例とその説明を提供します。ラテックスは方程式を調整します。
lastmod: "2025-06-09"
---

{{<section overview>}}


*amsmath*パッケージには、表示された数式のタイピングのための多くの環境定義が含まれています。それらは、材料ラインの数(単一または複数)とアライメントポイントの数によって分類できます。

> このセクションでは、「*方程式*」という用語を、数式表示における*論理的な*独立した部分を指すために使用します。数式表示には、参照のために番号が付けられることが多く、ラベル（例えば括弧内の番号）も付けられます。このようなラベルは*タグ*とも呼ばれます。

次のリストには、最も人気のあるディスプレイ環境が含まれています。必要に応じて、それらは方程式のタグ付けがないフォームを主演しています。

||
| --- | --- | --- |
| 「方程式」| `式*` | 1つの行、1つの方程式|
| `multline` | `multline*` | 1つの整列されていない複数行方程式、1つの方程式番号|
| 「集まってください」| `集まる*` |アライメントのないいくつかの方程式|
| 「align」| `align*` |複数のアライメントを持ついくつかの方程式|
| `flalign` | `flalign*` |いくつかの方程式：「align」の水平方向に広がります|
| 「スプリット」| |複数行方程式内の単純なアライメント|

この章のすべての例は、右側の数学資料と方程式数(タグ)を備えたタイプセットです。ポジショニングを視覚化するために、左右のマージンと中心線を表す出力に青い垂直線を表示します。 LaTexソースコードでは、「％-----...」を使用して、ドキュメントの前文に配置する必要がある別々の行から体内に配置する必要があります。


```tex
\usepackage[leqno]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![leqno](/tex/images/java/tutorial/latex-ams-math-2-1.png)

テキスト列の中央ではなく、左マージンからの固定インデントに数学を配置する場合は、「fleqn」オプションが利用可能です。ゴムの長さ「\ mathindent」の値を設定することにより、プリアンブルのインデントのサイズを指定できます。そのデフォルト値は、第1レベルのリストのインデントと同じです。この値に満足している場合は、「Mathindent」の長さの設定をスキップできます。


```tex
\usepackage[fleqn,reqno]{amsmath}
\setlength\mathindent{0.2in}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![fleqn、reqno](/tex/images/java/tutorial/latex-ams-math-2-2.png)

ここで「reqno`オプションを渡す必要はありません(デフォルトであるため)が、ドキュメントクラス設定をオーバーライドするため、方程式番号は何でも右に強制されます。

標準のラテックスでは、 `＆`および `\\`は、表示されたアライメント内の列と線の分離に使用されます。 `Amsmath`環境での使用の詳細。

## 2.1。標準のラテックスとの比較

マルチラインディスプレイ環境の一部を使用すると、式の一部を整列できます。標準のラテックス環境「eqnarray」および `eqnarray*`と比較して、`amsmath`パッケージで定義されている構造は、アライメントポイントをマークするわずかに異なる単純な方法を提供します。標準のラテックスでは、 `eqnarray*`は、 `{rcl}`を備えた「配列」環境に似ています。つまり、2つのアライメントポイントを示すために2つの `＆` charが必要です。 `amsmath`パッケージでは、同等の構造には単一のアライメントポイントしかありません(` array`には `{rl}` preambleがあるかのように)。したがって、シンボルの左に1つの `＆` char(通常は関係)を配置する必要があります。

「eqnarray」環境は、「配列」のパラメーター設定に応じて、アライメントポイントに余分なスペースを生成します。 `amsmath`構造は、同時に、固定間隔を与えます。違いは、次の例で明確に示されています。同じ方程式は、「方程式」、「Align」、および「eqnarray」環境を使用してタイプセットです。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
x^2 + y^2 = z^2
\end{equation}
\begin{align}
x^2 + y^2 &= z^2 \\
x^3 + y^3 &< z^3
\end{align}
\begin{eqnarray}
x^2 + y^2 &=& z^2 \\
x^3 + y^3 &<& z^3
\end{eqnarray}
```

![標準のラテックスと比較したAMSmath](/tex/images/java/tutorial/latex-ams-math-2-3.png)

「eqnarray」環境のスペースは、数学のタイプセットの従来の基準には広すぎることに注意してください。
標準のラテックスと同様に、`amsmath`ディスプレイのラインには「\\」(または環境の終わり)がマークされています。数学的なディスプレイでのライン破壊には通常、式の構造を深く理解する必要があるため、一般的に今日のソフトウェア機能を超えていると考えられています。

## 2.2。 1つの行の単一の方程式

「方程式」環境によって単一の方程式を生成できます。タグが自動的に生成され、使用中のオプションに従って左端または右に配置されます。 「方程式*」環境は、タグなしで同じ方程式を生成します。標準のラテックスには「方程式」もありますが、「方程式*」はありません。後者は標準の表示される数学環境に似ているためです。

注目すべき事実は、タグの存在が内容の位置に影響しないということです。 1つの行に十分なスペースがない場合にタグが上下にシフトされます。方程式タグが左にある場合は、タグが右側にあるときの次の行に前の行に。


```tex
\usepackage[leqno]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation*}
n^2 + m^2 = k^2
\end{equation*}
\begin{equation}
n^p + m^p \neq k^p \qquad p > 2
\end{equation}
```

![1つのラインの単一の等量](/tex/images/java/tutorial/latex-ams-math-2-4.png)

## 2.3。アライメントなしのいくつかの行の単一の方程式

「方程式」環境のバリエーションは、「マルチライン」環境です。単一の行に適合しない方程式にのみ使用されます。 `\\` charは、自動的に見つからないため、ラインブレークをマークするために使用する必要があります。

「マルチライン」の最初の行は、左マージンからのインデンテーションに合わせられ、最後の行は右マージンからの同じインデンテーションに合わせられます。 `\ multlinegap`長さの値は、このインデントのサイズを定義します。

最初と最後以外の各ラインは、ディスプレイ幅内に個別に中心にされます(「fleqn」オプションが使用されない限り)。ただし、「\ shoveleft」または「\ shoveright」コマンドのいずれかを行内に追加すると、その行は左または右に強制されます。

「Multline」環境には、論理的には単一の方程式であるため、単一のタグがあります。したがって、「\ tag」または `\ notag`を使用して、個々の線を変更することはできません。タグは、存在する場合、「reqno」/`leqno`オプションが使用されると、最後/最初の行に右折/左に左に配置されます。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{multline}
\text{First line of a multline} \\
\text{Centered Middle line} \\
\shoveright{\text{A right Middle}} \\
\text{Another centered Middle} \\
\text{Yet another centered Middle} \\
\shoveleft{\text{A left Middle}} \\
\text{Last line of the multline}
\end{multline}
```

![いくつかの線の単一の等量](/tex/images/java/tutorial/latex-ams-math-2-5.png)

次の例は、「\ multlinegap」が結果にどのように影響するかを示しています。最初のケースでは、式の最初の行からタグが欠落しているように見える「*dy*」のラインアップがあります。 「\ multhlinegap」が「0」に設定されると、2行目の左側のスペースはタグのために変更されませんが、最初の行は左マージンにシフトされ、これが単一の方程式であることを明らかにします。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{multline} \tag{2}
\sum_{t \in \mathbf{T}} \int_a^t \biggl\lbrace \int_a^t f(t - x)^2 \, g(y)^2 \,dx \biggr\rbrace \,dy \\
= \sum_{t \notin \mathbf{T}} \int_t^a \biggl\lbrace g(y)^2 \int_t^a f(x)^2 \,dx \biggr\rbrace \,dy
\end{multline}
\setlength\multlinegap{0pt}
\begin{multline} \tag{2}
\sum_{t \in \mathbf{T}} \int_a^t \biggl\lbrace \int_a^t f(t - x)^2 \, g(y)^2 \,dx \biggr\rbrace \,dy \\
= \sum_{t \notin \mathbf{T}} \int_t^a \biggl\lbrace g(y)^2 \int_t^a f(x)^2 \,dx \biggr\rbrace \,dy
\end{multline}
```

![\マルチラインギャップ効果](/tex/images/java/tutorial/latex-ams-math-2-6.png)

## 2.4。アライメント付きのいくつかの行の単一の方程式

単一のマルチライン方程式を整列する必要がある場合、「スプリット」環境はサービスにあります。各行で単一の `＆` charを使用して、アライメントポイントをマークするだけです。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
\begin{split}
(a + b)^4 &= (a + b)^2 (a + b)^2 \\
          &= (a^2 + 2ab + b^2)(a^2 + 2ab + b^2) \\
          &= a^4 + 4a^3b + 6a^2b^2 + 4ab^3 + b^4
\end{split}
\end{equation}
```

![単純なアライメントを伴う単一の等量](/tex/images/java/tutorial/latex-ams-math-2-7.png)

「split」自体は方程式タグを作成するわけではありません(したがって、星付きバリアントは必要ありません)。これは常に単一の方程式の内容として使用されているためです。この目的のために、あなたはそれを外側の環境に入れることができます。

デフォルトでは、タグ(および「スプリット」外の方程式の任意の部分)は、「分割 '環境材料の総高さの垂直方向に中心にあります。この動作は、「Centertags」オプションに対応します。 「tbtags」オプションを指定すると、タグは右側にあるときに「分割」の最後の行に、タグが左側にあるときの最初の行に配置されます。


```tex
\usepackage[tbtags]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
\begin{split}
(a - b)^3 &= (a - b) (a - b)^2 \\
          &= (a - b)(a^2 - 2ab + b^2) \\
          &= a^3 - 3a^2b + 3ab^2 - b^3
\end{split}
\end{equation}
```

![単純なアラインメントと最後の行のタグを備えた単一の等しい](/tex/images/java/tutorial/latex-ams-math-2-8.png)

## 2.5。整列のない方程式グループ

方程式間のアラインメントなしに2つ以上の方程式を単一のディスプレイに配置する必要がある場合、「nectry」環境を使用できます。また、ディスプレイ幅内の各方程式を個別に中心にし、必要に応じて個々のタグを装備します。 「集まり」の各行は、論理的に単一の方程式です。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
(a + b)^2 = a^2 + 2ab + b^2 \\
(a + b) \cdot (a - b) = a^2 - b^2
\end{gather}
```

![整列なしの方程式グループ](/tex/images/java/tutorial/latex-ams-math-2-9.png)

特定の行の方程式数を抑制する必要がある場合があります。 「\ notag`コマンドは、論理行に入れられますが、答えです。 `gracks*`環境は方程式にまったくタグ付けされません。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
D(a,r) \equiv \{ z \in \mathbf{C} \colon |z - a| < r \} \notag \\
\operatorname{seg} (a, r) \equiv \{ z \in \mathbf{C} \colon \Im z < \Im a, \ |z - a| < r \} \\
C (E, \theta, r) \equiv \bigcup_{e \in E} c (e, \theta, r)
\end{gather}
```

![挿入されたタグを持つ方程式グループ](/tex/images/java/tutorial/latex-ams-math-2-10.png)

## 2.6。単純なアライメントを持つ方程式グループ

単一のディスプレイで複数の方程式を整備し、それらを垂直に整列する必要がある場合、「Align」環境が救助になります。最も単純な場合、各行に単一の `＆`を使用してアライメントポイントをマークします。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
(a - b)^3 &= (a - b) (a - b)^2 \\
          &= (a - b)(a^2 - 2ab + b^2) \\
          &= a^3 - 3a^2b + 3ab^2 - b^3
\end{align}
\begin{align}
x^2 + y^2 &= 1 \\
        y &= \sqrt{1-x^2}
\end{align}
```

![単純なアライメントを持つ方程式グループ](/tex/images/java/tutorial/latex-ams-math-2-11.png)

## 2.7。複数のアライメント

「Align」環境は、複数のアライメントポイントを定義できます。レイアウトには、必要な数の列ペアが含まれており、 `{rlrl ...}` -like Preambleを使用した「配列」に似ています。 *n *そのような `rl`列ペアで構成されていると仮定すると、1行あたりの`＆ `'sの数は *2n-1 *になります。および * n -1 * `＆` 'sは列ペアを分離します。

「Align」環境は、材料を表示幅に均等に広げます。余分なスペースがある場合、隣接する列ペアと2つのディスプレイマージンの間に等しく分布しています。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\begin{align} \text{Compare }
x^2 + y^2 &= 1 &                      x^3 + y^3 &= 1 \\
x              &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{align}
This example has three column-pairs.
\begin{align}
     x &= y        &        X &= Y      &   a &= b+c \\
    x' &= y'       &       X' &= Y'     &  a' &= b \\
x + x' &= y + y'   &   X + X' &= Y + Y' & a'b &= c'b
\end{align}
```

![複数のアライメント](/tex/images/java/tutorial/latex-ams-math-2-12.png)

「Flalign」のレイアウトは似ていますが、マージンにはスペースがありません。次の例では、この事実のために方程式(3)が単一の行に適合していることがわかります(式(2)はまだそうではありません)。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\begin{flalign} \text{Compare }
x^2 + y^2 &= 1               &   x^3 + y^3 &= 1 \\
        x &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{flalign}
This example has three column-pairs.
\begin{flalign}
     x &= y        &        X  &= Y        &     a &= b+c \\
    x' &= y'       &       X'  &= Y'       &    a' &= b \\
x + x' &= y + y'   &   X + X'  &= Y + Y'   &   a'b &= c'b
\end{flalign}
```

![燃えるような](/tex/images/java/tutorial/latex-ams-math-2-13.png)

どちらの場合も、列ペア間の最小スペースは、「\ minalignsep」を変更することで設定できます。デフォルトの値は「10pt」で、長さパラメーターではなくマクロコマンドであるため、「\ renewcommand」で変更できます。次の例は、「\ minalignsep」を変更する効果を示しています。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\renewcommand\minalignsep{0pt}
\begin{align} \text{Compare }
x^2 + y^2 &= 1               &   x^3 + y^3 &= 1 \\
        x &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{align}
This example has three column-pairs.
\renewcommand\minalignsep{15pt}
\begin{flalign}
     x &= y        &        X  &= Y        &     a &= b+c \\
    x' &= y'       &       X'  &= Y'       &    a' &= b \\
x + x' &= y + y'   &   X + X'  &= Y + Y'   &   a'b &= c'b
\end{flalign}
```

![\ minalignsep効果](/tex/images/java/tutorial/latex-ams-math-2-14.png)

次の例は、「Align」の非常に一般的な使用を示しています。数学的資料内で通常のテキストを作成するために「\ text」の使用に注意してください。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
     x &= y        &&   \text{by hypothesis} \\
    x' &= y'       &&   \text{by definition} \\
x + x' &= y + y'   &&   \text{by Axiom 1}
\end{align}
```

![\テキストの使用](/tex/images/java/tutorial/latex-ams-math-2-15.png)

## 2.8。ディスプレイの中断： `\ intertext`

ディスプレイアライメントの行の間に小さなテキストを配置することをお勧めします。これは、「\ intertext」コマンドで行われます。すべてのアライメントプロパティがテキストの影響を受けないままにしておくことが非常に重要ですが、テキスト自体は表示幅に設定された通常の段落としてタイプセットです。ディスプレイを終了してからテキストの後に新しいものを開始するだけで、アライメントは機能しません。このコマンドは、常に「\\」または `\\*`コマンドに直後に従う必要があります。


``` tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
A_1 &= N_O (\lambda ; \Omega') - \phi ( \lambda ; \Omega') \\
A_2 &= \phi (\lambda ; \Omega') \phi (\lambda ; \Omega) \\
\intertext{and finally}
A_3 &= \mathcal{N} (\lambda ; \omega)
\end{align}
```

![\インターテキストコマンド](/tex/images/java/tutorial/latex-ams-math-2-16.png)

> The words "and finally" are outside the alignment, at the left margin, but all three equations are aligned.

## 2.9。方程式番号とタグ

ラテックスでは、方程式のタグは通常自動的に生成され、本質的にラテックスカウンター「方程式」の印刷された表現です。これは、LaTexによって3つのステップで行われます。「方程式」カウンターの値を設定します。タグのフォーマット。正しい位置に印刷します。

「方程式」のカウンター値は、対応するタグが自動的に印刷された場合にのみ増加するため、最初の2つのステップは密接にリンクされています。星とstarされていないフォームの両方があるディスプレイ環境を見てみましょう。星付きフォームは、星付きフォームが自動的にタグ付けされますが、星付きフォームはそうではないため、「式」カウンターの値を変更していないフォームのみが変更されます。

starされていないフォーム内の特定の論理方程式のタグの設定を抑制する必要がある場合、「\ notag`(または `\ nonumber」(` \ nonumber」 *を `\\`の前に配置します。 「\\ `の前に「\ tag」コマンド *を使用して、デフォルトのタグを独自のデザインのタグに置き換えることもできます。このコマンドの引数は、その方程式のタグとして、括弧内のタイプセットである任意の通常のテキストである可能性があります。
「\ tag」を使用すると、カウンター値の増分も抑制されることに注意してください。つまり、デフォルトのタグ設定は、「\ tag {\ the equation}」と視覚的にのみ同じであることを意味します。それらは同等ではありません。星付きのフォーム、 `\ tag*`は、括弧なしで(そして、特定のドキュメントクラスで追加される可能性のある他のものなしで、その引数のテキストを入力します)。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
x^2+y^2 &= z^2 \label{eq:A} \\
x^3+y^3 &= z^3 \notag \\
x^4+y^4 &= r^4 \tag{$*$} \\
x^5+y^5 &= r^5 \tag*{$*$} \\
x^6+y^6 &= r^6 \tag{\ref{eq:A}$'$} \\
A_1 &= N_0 (\lambda ; \Omega') - \phi ( \lambda ; \Omega') \\
A_2 &= \phi (\lambda ; \Omega') \, \phi (\lambda ; \Omega) \tag*{ALSO (\theequation)} \\
A_3 &= \mathcal{N} (\lambda ; \omega)
\end{align}
```

![\ tag、\ tag*、\ notag、\ label、\ ref](/tex/images/java/tutorial/latex-ams-math-2-17.png)

> Notice how the `\label` and `\ref` commands are used to provide some sort of "relative numbering" for equations.

## 2.10。下位番号付けシーケンス

*amsmath*パッケージは、いわゆる「方程式サブ番号」もサポートしています。 `subequations`環境は、フォーム(2a)、(2b)、(2c)などのタグを生成します。この番号付けスキームは、2つの通常のラテックスカウンターに基づいています：「Parent Equation」と「方程式」。 `subequations`環境内のすべてのタグ付き方程式は、このスキームを使用します。

次の例は、タグをある程度再定義できることを示していますが、「\ the Equation」の再定義は「サブエーケーション」環境に配置する必要があることに注意してください。


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{subequations} \label{eq:1}
\begin{align}
           f &= g \label{eq:1A} \\
          f' &= g' \label{eq:1B} \\
\mathcal{L}f &= \mathcal{L}g \label{eq:1C}
\end{align}
\end{subequations}

\begin{subequations} \label{eq:2}
\renewcommand\theequation{\theparentequation\roman{equation}}
\begin{align}
           f &= g \label{eq:2A} \\
          f' &= g' \label{eq:2B} \\
\mathcal{L}f &= \mathcal{L}g + K \label{eq:2C}
\end{align}
\end{subequations}
Note the relationship between~\eqref{eq:1}
and~\eqref{eq:2}: only~\ref{eq:1C} and~\ref{eq:2C} differ.
```

![下位番号付けシーケンス](/tex/images/java/tutorial/latex-ams-math-2-18.png)

> The `subequations` environment must appear *outside* the displays that it affects. It also shouldn't be nested within itself. The "main" equation counter is incremented with each use of this environment. A `\label` command within the `subequations` environment but outside any individual (logical) equation will produce a `\ref` to the parent number (e.g., to 2 rather than 2i).

## 2.11。方程式カウンターのリセット

フォーム(1.1)、(1.2)、...、(2.1)、(2.2)、...のタグを持つセクションまたは章内に方程式が番号付けされることは一般的な慣行です。 `amsmath`パッケージは、「\ numberwithin」宣言でこれを簡単に設定する簡単な方法を提供します。

たとえば、セクション番号を含む方程式タグを取得するには、各セクションの方程式カウンターが自動的にリセットされている場合、この宣言を前文に配置します。

## 付録A. Aspose.TeX APIを使用したラテックス方程式のレンダリング

次に、Aspose.TeX APIがラテックス方程式をスタンドアロンの数字として取得する方法を見ていきます。

式をラスター画像として取得して、テックス以外の出版物(たとえば、Webページなど)で使用できるようにする必要があるとしましょう。 Aspose.TeX APIを使用すると、次のように行うことができます。


```csharp
string equation = @"\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]";
Aspose.TeX.Features.PngMathRendererOptions options = new Aspose.TeX.Features.PngMathRendererOptions();
using (Stream stream = File.Open("your-file-name-and-path", FileMode.Create))
{
    new Aspose.TeX.Features.PngMathRenderer().Render(equation, stream, options, out System.Drawing.SizeF size);
    // Below is the short version for rendering with SVG
    // new Aspose.TeX.Features.SvgMathRenderer().Render(equation, stream, new Aspose.TeX.Features.SvgMathRendererOptions(), out System.Drawing.SizeF size);
}
```

ご覧のとおり、APIはラテックス方程式をSVGファイルに変換することもできます。そして、それは.netにAspose.TeXを使用する例でした。以下は、Javaバージョンの同等のコードです。


```java
String equation = "\\begin{equation} (a-b)^2 = a^2-2ab+b^2 \\end{equation}\r\n" +
		"\\[ \\cos2\\eta = \\cos^2\\eta-\\sin^2\\eta \\]";
Size2D size = new Size2D.Float();
com.Aspose.TeX.PngMathRendererOptions options = new com.Aspose.TeX.PngMathRendererOptions();
final OutputStream stream = new FileOutputStream(Helper.getOutputFile(Path.combine(getCurrentPath(), "doc.png")));
try
{
    new com.Aspose.TeX.PngMathRenderer().render(equation, stream, options, size);
}
finally {
    stream.close();
}
```

Rendererオプションの使用に関する詳細は、[.netのAspose.TeX](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/)または[asops.tex for java](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/)を使用して、ラテックス数学式のレンダリングに関する記事の使用に関する詳細を見つけることができます。しかし、それらの1つはここで私たちにとって重要です。このオプションを使用して、必要な結果を取得するために必要なLaTexドキュメントプリアンブルを指定できます。 (以下、ソースコードのC＃バージョンのみを提示します。)


```csharp
// The preamble for the very first example on this page
options.Preamble = @"\usepackage[leqno]{amsmath}";
```

また、デフォルトで定義されているラテックス「\ textWidth」よりも狭い領域でレイアウトされた方程式を取得する必要がある場合に、このオプションを使用することもできます。この目標を達成するための2つのオプションがあります。


```csharp
// The preamble for the 2.7 examples
options.Preamble = @"\usepackage[textwidth=232pt]{geometry}
\usepackage{amsmath}";
// or
options.Preamble = @"\usepackage{amsmath}
\setlength{\textwidth}{232pt}";
```

Aspose.TeX APIでは、次のプリアンブルがデフォルトで使用されているため、オプションを`amsmath`パッケージに渡すか、デフォルトの「\ textWidth」などを変更する必要がない限り、レンダラーのオプションでプリアンブルを指定する必要はありません。


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

## 付録B.アサプスラテックス方程式Webアプリを使用したラテックス方程式のレンダリング

また、[LaTex Equation Editor Web App](https://products.aspose.app/tex/equation-editor)もあります。これにより、LaTex方程式を編集および表示できます。テキストフィールドに方程式を入力し、[ *表示 *]ボタンをクリックして結果を確認できます。または、サブエクスペッションカテゴリを選択し、次にサブエクスペッションを選択してから、引数を編集することにより、フィールドの上のコントロールパネルを使用して方程式を構築できます。プリアンブルとその他のオプションは、 *式 *フィールドの下にあります。