---
translation: true
template: /templates/_template-net.md
title: インストールと基本設定 | Aspose.TeX .NET
linktitle: インストールと設定
weight: 18
url: /net/tikz-installation-and-basic-configuration/
aliases: /net/installation-and-basic-configuration/
keywords: install tikz, configure tikz, setup tikz
description: TikZ をインストールし、TeX および LaTeX ドキュメントで使用できるように構成するためのステップバイステップガイド。
lastmod: "2026-04-22"
---

{{<section overview>}}

この章では、TeX と LaTeX 用の TikZ 拡張機能のインストールと基本設定について説明します。TikZ を使用したグラフィックス作成をすぐに始められるよう、明確な手順をご案内します。

## TikZ のインストール

TikZ は **TeX Live** や **MiKTeX** などの一般的な TeX ディストリビューションにあらかじめ同梱されています。これらのディストリビューションを使用している場合、すでに TikZ がインストールされている可能性があります。まだの場合は、以下の手順に従ってください。

### TeX Live ユーザー

1. TeX Live Manager（`tlmgr`）を開きます。  
2. パッケージリストを更新します:
   ```bash
   tlmgr update --self --all
   ```
3. TikZ（`pgf` パッケージの一部）をインストールします:
   ```bash
   tlmgr install pgf
   ```

### MiKTeX ユーザー

1. MiKTeX コンソールを開きます。  
2. **Packages** タブに移動します。  
3. 検索バーに `pgf` と入力します。  
4. `pgf` パッケージがインストールされていない場合は選択してインストールします。

## インストールの確認

以下の簡単なテスト文書で TikZ のインストールが正常に行われたか確認できます:

```tex
\documentclass{article}
\usepackage{tikz}

\begin{document}

Testing TikZ:
\begin{tikzpicture}
  \draw (0,0) rectangle (2,1);
\end{tikzpicture}

\end{document}
```

この文書を `pdflatex` あるいは TeXworks や Overleaf などの LaTeX 対応エディタでコンパイルしてください。生成された PDF に小さな矩形が表示されれば成功です。

## TikZ の基本設定

TikZ の設定は最小限で済みますが、グラフィックの挙動を制御するためにグローバルオプションを設定することができます:

- **グラフィックを全体的にスケール**:
  ```tex
  \tikzset{every picture/.style={scale=1.5}}
  ```

- **デフォルトの色と線スタイルを設定**:
  ```tex
  \tikzset{
    every path/.style={thick, blue},
    every node/.style={font=\small}
  }
  ```

これらのコマンドを文書のプリアンブルに追加すれば、一貫したスタイリングが適用されます。

## 推奨エディタ

快適な編集とリアルタイムコンパイルのため、以下の LaTeX エディタを推奨します:

- **TeXstudio** – 無料で機能が豊富なエディタ。TikZ プレビューが統合されています。  
- **Overleaf** – クラウドベースの共同編集エディタで、TikZ のサポートが優れています。  
- **Visual Studio Code** + **LaTeX Workshop** 拡張機能 – モダンで軽量なエディタで、TikZ をサポートします。

ご自身の好みやワークフローに合わせてエディタを選択してください。

---

これらの手順に従えば、TikZ のセットアップが完了し、TeX および LaTeX 文書で魅力的なグラフィックを作成できるようになります。

**さらに、[無料の web アプリ](https://products.aspose.app/tex/conversion/latex/)（[Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) に基づく）を利用して、簡単に TeX の変換を行うことも可能です。**
