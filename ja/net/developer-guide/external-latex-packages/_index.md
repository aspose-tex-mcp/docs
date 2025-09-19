---
translation: true
template: /templates/_template-net.md
title: 外部ラテックスパッケージ| .NETのAspose.TeX
linktitle: 外部ラテックスパッケージ
weight: 20
url: /net/external-latex-packages/
description: .NETのAspose.TeX APIでは、外部パッケージ、つまりFancyBoxやPGFPlotsパッケージなどのライブラリ自体に含まれていないパッケージを使用できます。
lastmod: "2025-06-09"
---

{{<section overview>}}

## 外部ラテックスパッケージ

**asops.tex**ライブラリには、[一般的なラテックスパッケージ](/tex/{{lang.url-fragment}}net/embedded-packages/)が含まれています。したがって、これらのパッケージをライブラリのTexエンジンに提供する方法を心配する必要はありません。ただし、ラテックスファイルがパッケージの「ネイティブにサポートされている「バンドル」を超えるパッケージが必要になる場合があります。この場合、[Texoptions](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/)クラスインスタンスの[rebulyinputDirectory](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/requiredinputdirectory/)オプションを使用して、必要な入力、つまり必要なパッケージのソースファイルを提供するようにしてください。これが2つの例でどのように機能するかを確認します。

### 未解決の必要な入力(「ファンシーボックス」パッケージ)

次の単純なラテックスファイルがあるとしましょう。


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

3行目では、ファイルには「ネイティブに」サポートされていない「ファンシーボックス」パッケージが必要であることがわかります。また、「ファンシーボックス」パッケージソースファイルがあると仮定しましょう。シンプルなパッケージなので、実際には単一のファイルで構成されています。このファイルをファイルシステムのどこにでも配置し、以下に示すようにディレクトリパスを指定できます。


```C#
options.RequiredInputDirectory = new InputFileSystemDirectory("path-to-directory-where-fancybox.sty-located");
```

このオプションでTEXジョブを実行した後(必要に応じて他のオプションを調整することを忘れないでください)、出力ドキュメント(つまり、PNG画像)を取得します。

![出力ドキュメント](/tex/images/net/Conversion-RequiredInputFs.png)

これが例の完全なソースコードです。

{<<gist "Aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.examples-conversion-requiredinput-filesystem.cs">}}}

### 必要な入力( `pgfplots`パッケージ)アーカイブ

次に、次の非常にシンプルなラテックスファイルもあります。これは、「必要なZip.tex」です。


```tex
\documentclass{article}
\usepackage[margin=0.25in]{geometry}
\usepackage{pgfplots}
\pgfplotsset{width=10cm,compat=1.18}
\begin{document}

First example is 2D and 3D math expressions plotted side-by-side.

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


3行目では、ファイルには「PGFPlots」パッケージが必要であることがわかります。これは「ネイティブに」サポートされていません。繰り返しますが、「pgfplots」パッケージソースファイルがあると想定しています。 LaTexタイプセットアプリケーションのインストールディレクトリにそれらを見つけた場合、2つの場所に分割されたファイルが非常に多数です。 「\ tex \ generic」と `\ tex \ latex`フォルダーの両方で「pgfplots」フォルダーを見つけることができます。また、これらの両方のフォルダーのコンテンツは、Asoppes.texライブラリへの必要な入力として提供する必要があります。これらのソースファイルをzipアーカイブにパッケージ化することを望んでいるので、アーカイブのレイアウトは次のとおりです。

![アーカイブのレイアウト](/tex/images/net/pgfplots-zip-layout.png)

そして、これがこれらのソースファイルへのアクセスを指定する方法です。


```C#
using (Stream zipStream = File.Open("path-to-zip-with-pgfplots-sources"), FileMode.Open))
{
    ...
    options.RequiredInputDirectory = new InputZipDirectory(zipStream);
    ...
}
```

このオプションでTEXジョブを実行した後、出力ドキュメントを取得します。

![出力ドキュメント](/tex/images/net/Conversion-RequiredInputZip.png)

これが例の完全なソースコードです。

{<<gist "Aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.examples-conversion-requiredinput-zip.cs">}}}

> **_NOTE:_** The result was verified using the `pgfplots` package version 1.18.1. While the version of the `pfg` package included in the **Aspose.TeX** library is 3.1.9a.

### 外部フォントパッケージを使用します

原則として、LaTexディストリビューションは、版形セットに利用できる一連のデフォルトのフォントを提供します。これらのフォントを除き、**Asops.tex**には、標準以外のフォントパッケージが多数含まれています。たとえば、「amsfonts」、 `eurosym'、および` wasysym」。上で見たように、Aspose.TeXでは、外部パッケージを使用することもできます。しかし、ほとんどの場合、フォントが含まれていないパッケージについて話していました。
**Aspose.TeX** 'S*Object Tex*エンジン拡張機能は、各Texの内部フォント名に対応する物理フォントを判断するために、「.Map`拡張機能による特定の形式のテキストファイルです)を必要とします。これらのフォントマップは、初期化フェーズ中にTexのメモリにロードする必要があります。そして、もちろん、それらはあなたがプラグインしているパッケージのファイルに存在する必要があります。エンジンはすべてのフォントマップの名前がわからないため、 `.map`拡張子を持つすべてのファイルを探します。したがって、[IinputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/)インターフェイスの実装は、[rebysinginputDirectory](https://reference.aspose.com/tex/net/Aspose.TeX/texoptions/requiredinputdirectory/)オプションの値として使用されます。より具体的には、この実装は[ifileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/)インターフェイスも実装する必要があります。標準の実装 -  [inputFilesSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)および[inputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) - すでにそれを行います。

以下に、[ifileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/)インターフェイスを実装するカスタム要求の入力ディレクトリの例を示します。さらに、ファイル名の収集に焦点を当てながら、ファイルストレージと取得の詳細を意図的に省略します。

{<<gist "Aspose-com-gists" "76c7e5770ac8b3f6d409f6ec60f02030" "Aspose.TeX.examples-conversion-requiredinputdirectory.cs">}}}

### 制限

ラテックスファイルに必要なパッケージが * latex3e *カーネルの下で開発されていることがあります。このようなパッケージは、**Aspose.TeX**ライブラリで動作しない可能性が最も高くなります。後者は*latex2e*カーネルに基づいているためです。

また、LaTexファイルが必要とするパッケージは、**Aspose.TeX**ライブラリの*オブジェクトTex*エンジンによってサポートされていないデバイス依存のプリミティブコマンドを直接呼び出すことがあります。残念ながら、このようなパッケージは確かに機能しません。