---
translation: true
template: /templates/_template-java.md
linktitle: 装飾されたシンボルと複合構造
title: 4。装飾されたシンボルと複合構造
weight: 40
url: /java/latex-math-decorations/
keywords: AMS-Latex、AMSMATH、AMSXTRA、ラテックス積分、ラテックス画分、ラテックス装飾、ラテックス矢印、ラテックス制限、ラテックスモジュラー関係
description: この記事では、AMSMATHパッケージを使用してさまざまな中規模の数学構造を生成する多くのコマンドについて説明します。
lastmod: "2025-06-09"
---

{{<section overview>}}

`Amsmath`パッケージは、分数のようなオブジェクトや装飾されたシンボルなどの構造を作成するためのいくつかのコマンドを提供します。これで説明しています。


## 4.1。一般的な分数

`amsmath`パッケージは、一般化された画分を生成する`\ genfrac`コマンドを定義します。

```tex
\genfrac{ldelim}{rdelim}{thick}{style}{num}{denom}
```

最初の2つの引数は、それぞれ左右の区切り文字を定義します。 3番目の引数を使用して *厚く *、分数ルールのデフォルトの厚さをオーバーライドできます。たとえば、二項係数(以下を参照)は、この引数の値「0pt」を使用して、線を見えないようにします。ラインの厚さのデフォルト値(空のままになっている場合)は、数学タイプセット用の現在のフォントセットアップによって決定されます。次のリストには、この記事の例で使用されるデフォルトが含まれています。

| ***スタイル*** | ***デフォルトの厚さ*** |
|:---:|:---:|
| text/display | 0.4pt |
| script | 0.34pt |
| scriptscript | 0.24pt |

4番目の引数 *スタイル *は、レイアウトの数学スタイルと使用されるフォントサイズの数学スタイルをオーバーライドします。値は、0-3：0  -  `\ displaystyle`、1-` \ textStyle`、2- `\ scriptStyle`、3-` \ scriptscriptStyle`。この引数が空のままである場合、スタイルは分数の通常のルールに従って選択されます。最後の2つの引数は、分子と分母です。

> 標準の LaTeX が TeX から継承した古い分数コマンド `\over`、`\overwithdelims`、`\atop`、`\atopwithdelims`、`\above`、および `\abovewithdelims` は、`amsmath` パッケージで使用すると警告を発します。

### 4.1.1。単純な分数

「genfrac」コマンドを持つ`amsmath`パッケージは、3つのコマンドを便利な速記として定義します： `\ frac`、` \ dfrac`、および `\ tfrac`。

```tex
\newcommand\frac [2]{\genfrac{}{}{}{}{#1}{#2}}
\newcommand\dfrac[2]{\genfrac{}{}{}{0}{#1}{#2}}
\newcommand\tfrac[2]{\genfrac{}{}{}{1}{#1}{#2}}
```

以下の例は、これらのコマンドの使用を示しています。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \frac{1}{k} \log_2 c(f)
  \quad \tfrac{1}{k} \log_2 c(f)
\end{equation}
Text: $ \sqrt{ \frac{1}{k} \log_2 c(f) } \quad
        \sqrt{ \dfrac{1}{k} \log_2 c(f) }\, $.

```

![\ frac、\ dfrac、および\ tfrac](/tex/images/java/tutorial/latex-ams-math-4-1.png)

### 4.1.2。二項係数

別の分数様構造は、二項係数です。それらをタイプセットするのを助けるために、`amsmath`パッケージは、同様のコマンド`\ binom`、`\ dbinom`、および `\ tbinom`を提供します。

これは、彼らが`\ genfrac`コマンドを省略する方法です。


```tex
\newcommand\binom[2]{\genfrac{(}{)}{0pt}{}{#1}{#2}}
\newcommand\dbinom[2]{\genfrac{(}{)}{0pt}{0}{#1}{#2}}
\newcommand\tbinom[2]{\genfrac{(}{)}{0pt}{1}{#1}{#2}}
```

そして、これが例です：

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \binom{k}{2} 2^{k - 1} + \tbinom{k - 1}{2} 2^{k - 2}
\end{equation}
Text: $ \binom{k}{2} 2^{k - 1} + \dbinom{k - 1}{2} 2^{k - 2} $.
```

![\ binom、\ dbinom、および\ tbinom](/tex/images/java/tutorial/latex-ams-math-4-2.png)

### 4.1.3。継続的な分数

「継続的な画分」とも呼ばれる本質的に無限の分数である分数配列を整形する必要がある場合、`amsmath`パッケージには`\ cfrac`コマンドがあります。オプションの引数 `[l]`または `[r]`を渡します。分子を左または右に並べます。これはデフォルトで中央にあります。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation*}
\cfrac {1}{\sqrt{2} +
  \cfrac {1}{\sqrt{3} +
    \cfrac {1}{\sqrt{4} +
      \cfrac[r] {1}{\sqrt{5} +
        \cfrac[l] {1}{\sqrt{6} + \dotsb }
}}}}
\end{equation*}
```

![継続的な分数](/tex/images/java/tutorial/latex-ams-math-4-3.png)

## 4.2。箱入り数学

`amsmath`パッケージは、`\ fbox`に似た`\ boxed`コマンドを提供し、数学モードのコンテンツをボックスに入れます。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
  \boxed { f(x_0 - x) \leq f(x_0) \leq f(x_0 + x) }
\end{equation}
```

![箱入りフォーミュラ](/tex/images/java/tutorial/latex-ams-math-4-4.png)

## 4.3。制限の配置

統合、合計、製品、またはその他の演算子に関する添え字および上付き文字は、数学演算子(「制限位置」)の上または下のいずれか、または演算子の右側の添え字/上記の位置に配置できます。通常、制限はテキストでは使用されません(そうでなければ、行が広がる可能性があります)。表示された式では、配置は演算子に依存します。次の例は、ラテックスのデフォルトの配置を示しています。

```tex
\[
\sum_{n=1}^N \qquad \int_{-\infty}^\infty \qquad \lim_{x \to x_0}
\]
Text: $\sum_{n=1}^N$, $\int_{-\infty}^\infty$, $\lim_{x \to x_0}$.
```

![LaTexの添え字/SuperScriptsのデフォルトの配置](/tex/images/java/tutorial/latex-ams-math-4-5.png)

`Amsmath`パッケージは、ポジショニングを制御するためのオプションを提供します。これらは以下にリストされています。ここでは、`amsmath`パッケージが標準のLaTexドキュメントクラスで使用されているが、これらのオプションはありません。

|||
|:---:|---|
| `intlimits`, `nointlimits` | 積分記号の上付き文字/下付き文字を、それぞれ上と下、または横 (デフォルト) に配置します。表示数式でのみ使用されます。 |
| `sumlimits`, `nosumlimits` | *大きな演算子* (和、積など) の上付き文字/下付き文字を、それぞれ上と下 (デフォルト) または横に配置します。表示数式でのみ使用されます。 |
| `namelimits`, `nonamelimits` | `sumlimits` または `nosumlimits` と似ていますが、`inf`、`sup`、`lim`、`min`、`max` などの特定の演算子または「演算子名」に対して使用されます。これらの演算子は、少なくとも表示数式に出現する場合は、伝統的に下付き文字を付けて表記されます。 |

Texには、記号または演算子名の直後に表示された3つの原始コマンドがあり、添え字/Superscriptsの位置を制御します： `\ limits`、` \ nolimits`、および `\ displaylimits`。 `\ displaylimits`コマンドは、現在の数学スタイルがディスプレイスタイルである場合、限界位置に添え字/上付き文字を生成します。これは、クラス *オペレーター *のシンボルが表示される場合、または `\ mathop`コマンドが使用される場合はいつでもデフォルトの動作です。ディスプレイの外側の制限位置に添え字/上付き文字を使用してオペレーターを整形する必要がある場合は、 `\ limits`コマンドを使用して個別に宣言する必要があります。

次の例を前の例と比較してください。

```tex
\[
\sum\nolimits_{n=1}^N \qquad \int\limits_{-\infty}^\infty \qquad \lim\displaylimits_{x \to x_0}
\]
Text: $\sum\nolimits_{n=1}^N$, $\int\limits_{-\infty}^\infty$, $\lim\displaylimits_{x \to x_0}$.
```

![Tex Primitivesを使用したサブスクリプト/サッパースクリプトの配置を制御します](/tex/images/java/tutorial/latex-ams-math-4-6.png)

## 4.3。複数の積分

テキストとディスプレイの両方で、適切に調整されたスペースを持つ複数の積分標識をタイプセットするには、`\ iint`、 `\ iiint`、および` \ iiiint`コマンドを使用します。 `\ idotsint`は、それらの間に楕円のドットを含む2つの不可欠な兆候を生成します。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather*}
\iint \limits _V f(x,y) \,dx \,dy \\
\iiint \limits _V f(x,y,z) \,dx \,dy \,dz \\
\iiiint \limits _V f(t,x,y,z) \,dt \,dx \,dy \,dz \\
\idotsint \limits _V f(x_1, \dots, x_k) \,\mathbf{dx}
\end{gather*}
```

![複数の積分](/tex/images/java/tutorial/latex-ams-math-4-7.png)

## 4.4。モジュラー関係

整数の等価クラスの` mod`表記は、特別な間隔の規則に準拠しています。それに対処するために、`amsmath`パッケージは、`\ mod`、 `\ bmod`、` \ pmod`、および `\ pod`コマンドを提供します。次の例は、これらのコマンドの使用を示しています。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align*}
u & \equiv v + 1 \mod{n^2} \\
u & \equiv v + 1 \bmod{n^2} \\
u & = v + 1 \pmod{n^2} \\
u & = v + 1 \pod{n^2}
\end{align*}
The in-text layout: $ u = v + 1 \pmod{n^2} $
\begin{gather*}
(m \bmod n) = k^2 \, ; \quad x \equiv y \pmod b \, ; \\
x \equiv y \mod c \, ; \quad x \equiv y \pod d\, .
\end{gather*}
```

![モジュラー関係](/tex/images/java/tutorial/latex-ams-math-4-8.png)

> With `amsmath`, the spacing of `\pmod` is decreased within a non-displayed formula.

## 4.5。数学的ドットアクセント

`\ dot`および` \ ddot` Math Accentsに加えて、 `amsmath`パッケージは、それぞれトリプルと4倍のドットアクセントを生成するコマンド`\ dddot`と` \ ddddot`を提供します。

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
$ \dot{A} \quad \ddot{B} \quad \dddot{C} \quad \ddddot{D} $
```

![ドットアクセント](/tex/images/java/tutorial/latex-ams-math-4-9.png)

## 4.6。アクセントから上付き文字を作成する：「Amsxtra」パッケージ

`amsxtra`パッケージは、サブフォーミュラへの上甘文字としてアクセントを配置するための簡単なコマンドのコレクションである便利な機能を提供します。

```tex
\usepackage{amsxtra}
% -------------------------------------------------------------------------------
$(abc)\spdddot$ \quad $(abc)\spddot$ \quad $(abc) \spdot$ \\
$(abc)\spbreve$ \quad $(abc)\spcheck$ \\
$(abc)\sphat$ \quad $(abc)\sptilde$
```

![上付き文字としてのアクセント](/tex/images/java/tutorial/latex-ams-math-4-10.png)

## 4.7。他の装飾

標準のLaTexには、上付き文字を *関係 *シンボルの上に配置する `\ stackrel`コマンドがあります。さらに、 `amsmath`パッケージは、`\ overset`および` \ underset`コマンドを定義します。それを使用して、材料を上下または下または下に配置します。

`\ sideset`コマンドは、通常の制限に加えて、任意の *operator*シンボル(合計、製品など)に装飾を追加します。これらは、 *演算子 *の左右に添え字と上付きの位置に配置されます。

```tex
\[ \overset{*}{X} > \underset{*}{X}
\iff \sideset{}{'}\sum_{a,b \in \mathbf{R^*}}
\overset{a}{\underset{b}{X}} = X \]
```

![より多くの装飾](/tex/images/java/tutorial/latex-ams-math-4-11.png)