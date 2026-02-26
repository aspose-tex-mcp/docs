---
translation: true
template: /templates/_template-net.md
title: TikZ の基本的な使用 | Aspose.TeX .NET
linktitle: TikZ の基本
weight: 19
url: /net/tikz-fundamentals-of-using-tikz/
aliases: /net/fundamentals-of-using-tikz/
keywords: tikz の基礎, tikz の基本, tikz チュートリアル
description: TikZ の基本原理と基本コマンドを学び、TeX および LaTeX 文書用のグラフィックを作成しましょう。
lastmod: "2026-02-26"
---

{{<section overview>}}

この章では、TikZ の基本原理とコマンドを探ります。これらの基礎を理解することで、文書に対して明確で表現力のあるグラフィックを作成できるようになります。

## TikZ の座標系

TikZ のグラフィックは座標を使用して作成されます。座標は描画内の位置を定義し、さまざまな方法で指定できます。

- **デカルト座標 (x,y)**:
```tex
\draw (0,0) -- (2,2);
```

- **極座標 (角度:半径)**:
```tex
\draw (0,0) -- (45:2);
```

座標は描画内で自由に混在させることができ、希望するグラフィック結果を得られます。

## 基本形状の描画

TikZ を使用すると、基本的な幾何形状を簡単に作成できます。

- **直線と折れ線**:
```tex
\draw (0,0) -- (1,1) -- (2,0);
```

- **矩形**:
```tex
\draw (0,0) rectangle (2,1);
```

- **円と楕円**:
```tex
\draw (1,1) circle (0.5);
\draw (3,1) ellipse (1 and 0.5);
```

## 色と塗りパターン

色と塗りは視覚的な明瞭さを大幅に向上させます。色は直接指定するか、事前定義された名前を使用できます。

```tex
\draw[red, thick] (0,0) rectangle (1,1);
\draw[fill=blue!20] (2,0) circle (0.5);
```

構文 `blue!20` は、20% の強さの青色を意味します。

## 線のスタイルと太さ

TikZ では、線のスタイルと太さを変更してグラフィックの表現を向上させることができます。

- **線の太さ**:
```tex
\draw[ultra thick] (0,0) -- (1,1);
\draw[thin] (1,0) -- (2,1);
```

- **破線と点線**:
```tex
\draw[dashed] (0,0) -- (2,2);
\draw[dotted] (2,0) -- (4,2);
```

## ノードとラベル

ノードを使用すると、テキスト注釈を簡単に追加できます。

```tex
\draw (0,0) -- (1,1) node[midway, above] {label};
```

ラベルをグラフィック要素に対して正確に配置でき、可読性が向上します。

## パスと曲線

TikZ のパスは直線または曲線にすることができます。曲線はシンプルな構文で作成します。

```tex
\draw (0,0) .. controls (1,2) and (3,-1) .. (4,1);
```

制御点は曲率を直感的に形作ります。

## 要素のグループ化

グラフィック要素をグループ化すると、変換（拡大縮小や回転など）が簡略化されます。

```tex
\begin{scope}[rotate=45, scale=1.5]
  \draw (0,0) rectangle (1,1);
  \draw (1,1) circle (0.5);
\end{scope}
```

`scope` 内の要素は一緒に回転・拡大縮小され、配置が維持されます。

---

これらの基本的な TikZ の概念とコマンドを習得することで、文書向けの高度なグラフィックを作成するための強固な基盤が築かれます。

**さらに、[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) をベースにした無料の [Web アプリ](https://products.aspose.app/tex/conversion/latex/) で、迅速かつ簡単な TeX 変換を体験してください。**
