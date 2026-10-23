---
translation: true
template: /templates/_template-java.md
linktitle: LaTeX 方程式の整列と表示
title: 2. LaTeX 方程式の表示と整列
weight: 10
url: /java/latex-structures-for-equations/
keywords: ams-latex, amsmath, amsmath options, latex equation alignment, leqno, eqno, fleqn, latex equation tag, latex equation label, latex align equations
description: AMS‑LaTeX パッケージを用いた LaTeX 方程式の組版入門と、いくつかの例とその解説を提供します。LaTeX の align 系の方程式。
lastmod: "2026-02-19"
---

{{<section overview>}}


*amsmath* パッケージには、表示用数式を入力するための環境が多数定義されています。これらは、行数が単一か複数か、また整列ポイントの数で分類できます。

> 本節では、*equation* という用語を次のように定義します。数学的ディスプレイの **論理的に distinct な部分** を指し、参照用に番号が付けられ、タグ（例えば括弧で囲まれた番号）でラベル付けされることが多いものです。このようなラベルは *tag* とも呼ばれます。

以下の表に、最も一般的な表示環境を示します。適切な場合は、タグ付けが行われない starred 形も併記しています。

||
|---|---|---|
| `equation` | `equation*` | 1 行、1 つの方程式 |
| `multline` | `multline*` | 整列せずに複数行の方程式、1 つの番号 |
| `gather` | `gather` | 整列なしで複数の方程式 |
| `align` | `align*` | 複数の整列ポイントを持つ方程式 |
| `flalign` | `flalign*` | `align` の水平に広げた形 |
| `split` |  | 複数行方程式内部の簡易整列 |

本章のすべての例は、数式素材を中央揃えにし、方程式番号（タグ）を右側に配置して組版しています。配置を視覚化するために、出力画像には左・右余白と中心線を示す青い垂直線を表示しています。LaTeX ソースコード中では、`% -----...` コメントを使って、プリアンブルに置くべき行と本文に置くべき行を区別しています。

```tex
\usepackage[leqno]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![leqno](/tex/images/java/tutorial/latex-ams-math-2-1.png)

左余白から固定インデントで数式を配置したい場合、`fleqn` オプションが利用できます。インデント幅はプリアンブルで `\mathindent` の長さを設定して変更できます。既定値は第 1 レベルリストのインデントと同じです。この値に満足しているなら、`\mathindent` を設定する必要はありません。

```tex
\usepackage[fleqn,reqno]{amsmath}
\setlength\mathindent{0.2in}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![fleqn,reqno](/tex/images/java/tutorial/latex-ams-math-2-2.png)

`reqno` オプションはデフォルトで有効ですが、ここで指定すると文書クラスの設定を上書きし、番号が常に右側に強制されます。

標準 LaTeX では、`&` と `\\` が列と行の区切りに使われますが、`amsmath` 環境ではその使い方が若干変わります。

## 2.1. 標準 LaTeX との比較

いくつかの複数行表示環境は、式の一部を整列させることができます。標準 LaTeX の `eqnarray` 系と比較すると、`amsmath` が提供する構造は少し異なり、よりシンプルに整列ポイントを指定できます。標準 LaTeX の `eqnarray*` は `{rcl}` 前置子を持つ `array` 環境に相当し、2 つの `&` が必要です。一方、`amsmath` の同等構造は `{rl}` 前置子に相当し、左側に 1 つの `&` だけで整列できます。

`eqnarray` 環境は `array` のパラメータ設定により整列ポイントで余分な空白が生じますが、`amsmath` の構造は一定の間隔を保ちます。次の例で違いを確認してください。同じ式を `equation`、`align`、`eqnarray` 環境で組版しています。

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

![Amsmath compared to standard LaTeX](/tex/images/java/tutorial/latex-ams-math-2-3.png)

`eqnarray` 環境の空白は、従来の数式組版基準としては広すぎます。

標準 LATEX と同様に、`amsmath` のディスプレイでも行の区切りは `\\`（または環境の終了）で行います。数式ディスプレイの改行は式構造を深く理解する必要があり、現在のソフトウェアでは自動化が難しいとされています。

## 2.2. 1 行だけの単独方程式

`equation` 環境で単一の方程式を作成できます。タグは自動生成され、オプションに応じて左または右に配置されます。`equation*` 環境はタグなしで同じ式を組版します。標準 LaTeX には `equation` はありますが `equation*` はなく、後者は標準ディスプレイ数式環境に相当します。

タグの有無は内容の配置に影響しません。タグが左側の場合は上に、右側の場合は下にずれることがあります。

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

![A single equiation on one line](/tex/images/java/tutorial/latex-ams-math-2-4.png)

## 2.3. 整列なしの複数行単独方程式

`equation` 環境の変形版が `multline` 環境です。1 行に収まらない方程式に使用し、改行は `\\` で明示的に指定します。

`multline` の最初の行は左余白からインデントされ、最後の行は右余白から同じインデントになります。インデント幅は `\multlinegap` で決まります。

最初と最後以外の行は、`fleqn` オプションが無い限り、表示幅の中央に配置されます。行内で `\shoveleft` または `\shoveright` を使用すれば、左または右に強制できます。

`multline` 環境は単一のタグを持ちます（論理的には単一方程式です）。`\tag` や `\notag` で個々の行のタグを変更することはできません。`reqno` / `leqno` オプションに応じて、タグは最後の行（右）または最初の行（左）に寄ります。

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

![A single equiation on several lines](/tex/images/java/tutorial/latex-ams-math-2-5.png)

次の例は `\multlinegap` が結果に与える影響を示します。最初のケースでは `*dy*` が揃って見え、まるで最初の行にタグがないかのようです。`\multlinegap` を `0` に設定すると、2 行目左側の余白は変わらず、最初の行は左余白へシフトし、単一方程式であることが明確になります。

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

![The \multlinegap effect](/tex/images/java/tutorial/latex-ams-math-2-6.png)

## 2.4. 整列付きの複数行単独方程式

単一の複数行方程式を整列させたい場合は、`split` 環境を利用します。各行に 1 つの `&` を置くだけで整列ポイントを指定できます。

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

![A single equiation with simple alignment](/tex/images/java/tutorial/latex-ams-math-2-7.png)

`split` 自体はタグを生成しない（スター付き形は不要）ため、外側の環境（例: `equation`）に入れて使用します。

デフォルトでは、タグは `split` 全体の高さの中央に垂直配置されます（`centertags` オプションに相当）。`tbtags` オプションを指定すると、タグは右側の場合は `split` の最終行、左側の場合は最初の行に配置されます。

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

![A single equiation with simple alignment and the tag on the last line](/tex/images/java/tutorial/latex-ams-math-2-8.png)

## 2.5. 整列なしの方程式グループ

複数の方程式を整列せずに同一ディスプレイにまとめたい場合は、`gather` 環境を使用します。各方程式は個別に中央揃えされ、必要に応じて個別のタグが付与されます。`gather` の各行は論理的に単一の方程式です。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
(a + b)^2 = a^2 + 2ab + b^2 \\
(a + b) \cdot (a - b) = a^2 - b^2
\end{gather}
```

![Equation group without alignment](/tex/images/java/tutorial/latex-ams-math-2-9.png)

特定の行で番号を抑制したい場合は、論理行内に `\notag` を入れます。`gather` 環境自体はタグ付けしません。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
D(a,r) \equiv \{ z \in \mathbf{C} \colon |z - a| < r \} \notag \\
\operatorname{seg} (a, r) \equiv \{ z \in \mathbf{C} \colon \Im z < \Im a, \ |z - a| < r \} \\
C (E, \theta, r) \equiv \bigcup_{e \in E} c (e, \theta, r)
\end{gather}
```

![Equation group with omited tags](/tex/images/java/tutorial/latex-ams-math-2-10.png)

## 2.6. 整列付きの方程式グループ

複数の方程式を同一ディスプレイに並べて縦に整列させたい場合は、`align` 環境が便利です。最もシンプルな形では、各行に 1 つの `&` を置くだけで整列ポイントを指定します。

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

![Equation groups with simple alignment](/tex/images/java/tutorial/latex-ams-math-2-11.png)

## 2.7. 複数の整列ポイント

`align` 環境は複数の整列ポイントを定義できます。必要なだけ列ペアを増やせば、`array` の `{rlrl...}` に相当するレイアウトになります。`n` 個の `rl` 列ペアがあるとすると、各行の `&` の数は `2n‑1` です（各列ペアで 1 つ、列ペア間で `n‑1` 個）。

`align` は素材をディスプレイ幅全体に均等に配置します。余白が余る場合は、隣接列ペア間と左右の余白に均等に分配されます。

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

![Multiple alignments](/tex/images/java/tutorial/latex-ams-math-2-12.png)

`flalign` のレイアウトも同様ですが、余白がありません。次の例では、(3) 式が 1 行に収まることが分かります（(2) はまだ改行が必要です）。

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

![flalign](/tex/images/java/tutorial/latex-ams-math-2-13.png)

両ケースとも、列ペア間の最小間隔は `\minalignsep` を変更することで設定できます。既定値は `10pt` で、`\renewcommand` により変更可能です（長さパラメータではなくマクロです）。次の例は `\minalignsep` の変更効果を示します。

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

![\minalignsep effect](/tex/images/java/tutorial/latex-ams-math-2-14.png)

次の例は `align` の非常に一般的な使用例です。`\text` を使って数式内部に通常のテキストを入れています。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
     x &= y        &&   \text{by hypothesis} \\
    x' &= y'       &&   \text{by definition} \\
x + x' &= y + y'   &&   \text{by Axiom 1}
\end{align}
```

![The use of \text](/tex/images/java/tutorial/latex-ams-math-2-15.png)

## 2.8. ディスプレイの途中でテキストを挿入: `\intertext`

ディスプレイの行間に短いテキストを入れたい場合は、`\intertext` コマンドを使用します。整列特性はテキストによって影響されず、テキストはディスプレイ幅に合わせた普通の段落として組版されます。`\`（または `\\*`）の直後に続けて書く必要があります。

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

![The \intertext command](/tex/images/java/tutorial/latex-ams-math-2-16.png)

> 「and finally」という語は左余白に配置され、3 つすべての式は揃っています。

## 2.9. 方程式番号とタグ

LaTeX では、方程式のタグは通常自動生成され、内部的には `equation` カウンタの値が使われます。生成は次の 3 段階で行われます。① カウンタの値設定、② タグの書式設定、③ 右位置へ出力。

最初の 2 段階は密接に結びついており、`equation` カウンタはタグが自動で出力されたときにだけインクリメントされます。スター付きと非スター付きの両方の形を持つ環境を例にとると、非スター付き形だけがカウンタを増やします。

特定の論理方程式でタグの設定を抑制したい場合は、`\\` の **前** に `\notag`（または `\nonumber`）を置きます。`\tag` を使えば、`\\` の **前** に任意のテキストを括弧付きでタグとして挿入できます。

`\tag` を使用するとカウンタのインクリメントも抑制されます。`\tag*` は括弧なしでテキストだけを出力します（他のクラス固有の付加情報も無い）。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
x^2+y^2 &= z^2 \label{eq:A} \\
x^3+y^3 &= z^3 \notag \\
x^4+y^4 &= r^4 \tag{$*$} \\
x^5+y^5 &= r^5 \tag*{$*$} \\
x^6+y^6 &= r^6 \tag{\ref{eq:A}$} \\
A_1 &= N_0 (\lambda ; \Omega') - \phi ( \lambda ; \Omega') \\
A_2 &= \phi (\lambda ; \Omega') \, \phi (\lambda ; \Omega) \tag*{ALSO (\theequation)} \\
A_3 &= \mathcal{N} (\lambda ; \omega)
\end{align}
```

![\tag, \tag*, \notag, \label and \ref](/tex/images/java/tutorial/latex-ams-math-2-17.png)

> `\label` と `\ref` が「相対番号付け」に利用されていることに注意してください。

## 2.10. 従属番号系列

*amsmath* パッケージは「方程式の部分番号付け」もサポートします。`subequations` 環境は (2a), (2b), (2c) という形のタグを生成します。この番号付けは `parentequation` と `equation` の 2 つの標準 LaTeX カウンタに基づき、`subequations` 内のすべてのタグ付き方程式で使用されます。

以下の例は、`subequations` 内で `\theequation` を再定義できることを示しますが、再定義は必ず `subequations` 環境内部で行う必要があります。

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

![Subordinate numbering sequences](/tex/images/java/tutorial/latex-ams-math-2-18.png)

> `subequations` 環境は **表示全体の外側** に配置し、入れ子にしないでください。メインの方程式カウンタはこの環境が使用されるたびにインクリメントされます。`subequations` 内で個別の方程式以外に `\label` を置くと、親番号（例: 2）への参照が得られます。

## 2.11. 方程式カウンタのリセット

章や節ごとに (1.1), (1.2), …, (2.1), (2.2) のように番号付けしたいのは一般的です。`amsmath` では `\numberwithin` 宣言を用いて簡単に設定できます。

例: 各節の番号を含むタグを得るには、プリアンブルに次を記述します。

```
\numberwithin{equation}{section}
```

## Appendix A. Aspose.TeX API での LaTeX 方程式のレンダリング

ここでは Aspose.TeX API が LaTeX 方程式を単独画像として取得する方法を紹介します。

たとえば、ラスタ画像として方程式を取得したい場合（Web ページなど TeX 以外の媒体で使用する場合）には次のようにします。

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

上記のように、Aspose.TeX は LaTeX 方程式を SVG ファイルへ変換することもできます。以下は Java 版の同等コードです。

`outputFile` に既存のフォルダー内の `java.nio.file.Path`（例：`Paths.get(outputDirectory, "equations.png")`）を指定します。使用する `com.aspose.tex` のクラス、`java.awt.Color`、`java.io.ByteArrayOutputStream`、`java.io.OutputStream`、`java.nio.file.Files`、`java.nio.file.Paths` をインポートし、例外を処理または宣言してください。この例は両方の数式を白い背景に 150 DPI で描画し、最初の式の番号を保持します。3 引数の `render()` メソッドは `Size2D` を返します。ログはメモリに保存され、描画後に両方のストリームが閉じられます。

{{< gist "aspose-com-gists" "fc74664c51175ac402729283d0450d44" "Example-RenderEquationsToPNG.java" >}}

詳細は、[Aspose.TeX for .NET](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) または [Aspose.TeX for Java](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/) の記事をご参照ください。ここでは、レンダラオプションで LaTeX 文書のプリアンブルを指定できる点が重要です（以下は C# のコード例です）。

```csharp
// The preamble for the very first example on this page
options.Preamble = @"\usepackage[leqno]{amsmath}";
```

ページ幅より狭い領域に方程式を配置したい場合も、同様のオプションで実現できます。次の 2 つの方法があります。

```csharp
// The preamble for the 2.7 examples
options.Preamble = @"\usepackage[textwidth=232pt]{geometry}
\usepackage{amsmath}";
// or
options.Preamble = @"\usepackage{amsmath}
\setlength{\textwidth}{232pt}";
```

Aspose.TeX API のデフォルトプリアンブルは次の通りです。特別なオプションや `\textwidth` の変更が不要な限り、明示的にプリアンブルを指定する必要はありません。

```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

## Appendix B. Aspose LaTeX Equation Web アプリでのレンダリング

[LaTeX Equation Editor Web アプリ](https://products.aspose.app/tex/equation-editor) でも、LaTeX 方程式の編集と表示が可能です。テキストフィールドに式を入力し、*View* ボタンをクリックすると結果が得られます。また、上部のコントロールパネルでサブ式カテゴリ・サブ式を選択し、必要に応じて引数を編集して式を組み立てることもできます。プレアンブルやその他のオプションは *Formula* フィールド下部に表示されます。
