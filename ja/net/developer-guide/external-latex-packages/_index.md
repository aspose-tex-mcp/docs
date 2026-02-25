---
translation: true
template: /templates/_template-net.md
title: 外部 LaTeX パッケージ | Aspose.TeX for .NET
linktitle: 外部 LaTeX パッケージ
weight: 20
url: /net/external-latex-packages/
description: Aspose.TeX API for .NET では、fancybox パッケージや pgfplots パッケージなど、ライブラリ自体に含まれていない外部パッケージを使用できます。
keywords: 外部 LaTeX パッケージ、Aspose Tex、.NET Tex、LaTeX パッケージ、fancybox、pgfplots、必要な入力ディレクトリ、入力 zip、カスタム入力ディレクトリ、Tex 変換
lastmod: "2026-02-25"
---

{{<section overview>}}

## 外部 LaTeX パッケージ

**Aspose.TeX** ライブラリには、[common LaTeX packages](/tex/{{lang.url-fragment}}net/embedded-packages/) が多数含まれています。そのため、これらのパッケージをライブラリの TeX エンジンに提供する方法を心配する必要はありません。ただし、時には（あるいは頻繁に） LaTeX ファイルが「ネイティブに」サポートされているパッケージバンドルに含まれていないパッケージを必要とすることがあります。その場合は、[TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) クラスインスタンスの [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) オプションを使用して、必要なパッケージのソースファイル（必須入力）を提供できます。2 つの例でその方法を見てみましょう。

### アンパックされた必須入力（`fancybox` パッケージ）

次のシンプルな LaTeX ファイル（例のソリューションからの `required-input-fs.tex`）があるとします。

```tex
\documentclass{article}
\usepackage[a6paper,landscape]{geometry}
\usepackage{fancybox}
\begin{document}
Test: \fbox{
  \begin{Bitemize}[b]
  \item First item
  \item A second one\\ on two lines
  \item(2pt) A third with extra space
  \end{Bitemize}
}
\par\bigskip
Test: \fbox{
  \begin{Beqnarray}[t]
  y & = & x^2 \\
  a^2 + 2ab + b^2 & = & (a + b)^2 \\
  \int_0^\infty e^{-ax} dx & = & \frac{1}{a}
  \end{Beqnarray}
}
\end{document}
```

3 行目で `fancybox` パッケージが必要であることが分かりますが、これは「ネイティブに」サポートされていません。また、`fancybox` パッケージのソースファイルがあると仮定します。このパッケージはシンプルで、実際には単一ファイルで構成されています。このファイルをファイルシステム上の任意の場所に配置し、以下のようにディレクトリパスを指定できます。

```C#
options.RequiredInputDirectory = new InputFileSystemDirectory("path-to-directory-where-fancybox.sty-located");
```

このオプションで TeX ジョブを実行すると（他のオプションを必要に応じて調整するのを忘れずに）、出力ドキュメント（PNG 画像）が得られます。

![Output Document](/tex/images/net/Conversion-RequiredInputFs.png)

以下はサンプルの完全なソースコードです。

{{< gist "aspose-com-gists" "03f720960e15bd497ed26ce2eb9c03b2" "Example-RequiredInput-FileSystem.cs" >}}

### アーカイブされた必須入力（`pgfplots` パッケージ）

次に、同様にシンプルな LaTeX ファイル（例のソリューションからの `required-input-zip.tex`）があるとします。

```tex
\documentclass{article}
\usepackage[margin=0.25in]{geometry}
\usepackage{pgfplots}
\pgfplotsset{width=10cm,compat=1.18}
\begin{document}

最初の例は、2D と 3D の数式を並べてプロットしたものです。

%Here begins the 2D plot
\begin{tikzpicture}
\begin{axis}
\addplot[color=red]{exp(x)};
\end{axis}
\end{tikzpicture}
%Here ends the 2D plot
\hskip 5pt
%Here begins the 3D plot
\begin{tikzpicture}
\begin{axis}
\addplot3[
    surf,
]
{exp(-x^2-y^2)*x};
\end{axis}
\end{tikzpicture}
%Here ends the 3D plot

\end{document}
```

3 行目で `pgfplots` パッケージが必要であることが分かりますが、これも「ネイティブに」サポートされていません。再び、`pgfplots` パッケージのソースファイルがあると仮定します。これは多数のファイルから構成されており、任意の LaTeX タイプセットアプリケーションのインストールディレクトリ内の `\tex\generic` と `\tex\latex` フォルダーに分かれています。これら両方のフォルダーの内容を Aspose.TeX ライブラリに必須入力として提供する必要があります。ソースファイルは ZIP アーカイブにパッケージ化したいので、以下がアーカイブのレイアウトです。

![Archive’s Layout](/tex/images/net/pgfplots-zip-layout.png)

そして、これらのソースファイルへのアクセスは次のように指定します。

```C#
using (Stream zipStream = File.Open("path-to-zip-with-pgfplots-sources", FileMode.Open))
{
    ...
    options.RequiredInputDirectory = new InputZipDirectory(zipStream);
    ...
}
```

このオプションで TeX ジョブを実行すると、出力ドキュメントが得られます。

![Output Document](/tex/images/net/Conversion-RequiredInputZip.png)

以下はサンプルの完全なソースコードです。

{{< gist "aspose-com-gists" "03f720960e15bd497ed26ce2eb9c03b2" "Example-RequiredInput-Zip.cs" >}}

> **_NOTE:_** 結果は `pgfplots` パッケージ バージョン 1.18.1 を使用して検証しました。**Aspose.TeX** ライブラリに含まれる `pfg` パッケージのバージョンは 3.1.9a です。

### 外部フォントパッケージの利用

一般的に、LaTeX 配布には組版用に利用できるデフォルトフォントのセットが提供されています。これらのフォントに加えて、**Aspose.TeX** には多数の非標準フォントパッケージ（例: `amsfonts`、`eurosym`、`wasysym`）が含まれています。上記で見たように、Aspose.TeX は外部パッケージの使用もサポートしていますが、主にフォントを含まないパッケージについて説明しています。

**Aspose.TeX** の *Object TeX* エンジン拡張は、フォントマップ（拡張子が `.map` のテキストファイル）を必要とします。フォントマップは、物理フォントが TeX の内部フォント名にどのように対応するかを決定するために使用され、初期化フェーズで TeX のメモリにロードされます。したがって、マップファイルはパッケージに含まれている必要があります。エンジンはすべての `.map` 拡張子のファイルを検索するため、[RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) オプションの値として使用される [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/) インターフェイスの実装は、拡張子別にファイル名のコレクションにアクセスする方法を提供しなければなりません。具体的には、この実装は [IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/) インターフェイスも実装する必要があります。標準実装である [InputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) と [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) は既にこの機能を備えています。

以下に、[IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/) インターフェイスも実装したカスタム必須入力ディレクトリの例を示します。拡張子別にファイル名を収集することに焦点を当て、ファイルの実際の保存・取得の詳細は省略しています。

{{< gist "aspose-com-gists" "03f720960e15bd497ed26ce2eb9c03b2" "Example-RequiredInputDirectory.cs" >}}

### 制限事項

LaTeX ファイルが *LaTeX3e* カーネル向けに開発されたパッケージを要求する場合、そのパッケージは **Aspose.TeX** ライブラリ（*LaTeX2e* カーネルに基づく）では動作しない可能性が高いです。

また、LaTeX ファイルが直接デバイス依存のプリミティブコマンドを呼び出すパッケージを要求する場合、**Aspose.TeX** の *Object TeX* エンジンはそれらをサポートしていないため、該当パッケージは確実に動作しません。
