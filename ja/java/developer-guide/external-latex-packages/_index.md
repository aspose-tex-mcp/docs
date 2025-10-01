---
translation: true
template: /templates/_template-java.md
title: 外部ラテックスパッケージ| Java用のAspose.TeX
linktitle: 外部ラテックスパッケージ
weight: 30
url: /java/external-latex-packages/
description: Java用のAspose.TeX APIでは、外部パッケージ、つまりFancyBoxやPGFPlotsパッケージなどのライブラリ自体に含まれていないパッケージを使用できます。
lastmod: "2025-06-09"
---

{{<section overview>}}

## 外部ラテックスパッケージ

Javaの**Aspose.TeX**ライブラリには、[一般的なラテックスパッケージ](/tex/{{lang.url-fragment}}net/embedded-packages/)が含まれています。したがって、これらのパッケージをライブラリのTexエンジンに提供する方法に注意する必要はありません。しかし、(おそらく)ラテックスファイルには、パッケージの「ネイティブにサポートされている「バンドル」を超えたパッケージが必要になる場合があります。この場合、[setRequiredInputDirectory()](https://reference.aspose.com/tex/java/com.Aspose.TeX/texoptions/#setRequiredInputDirectory-com.Aspose.TeX.IInputWorkingDirectory-)[texoptions](https://reference.aspose.com/tex/java/com.Aspose.TeX/texoptions/)クラスインスタンスのメソッドを使用して、必要な入力、つまり必要なパッケージのソースファイルを提供することを試みることができます。これが2つの例でどのように機能するかを確認します。

### 未解決の必要な入力(`fancybox`パッケージ)

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

3行目では、ファイルには「ネイティブに」サポートされていない`fancybox`パッケージが必要であることがわかります。また、`fancybox`パッケージソースファイルがあると仮定します。シンプルなパッケージなので、実際には1つのファイルで構成されています。このファイルをファイルシステムのどこにでも配置し、次のようにディレクトリパスを指定できます。

```Java
options.setRequiredInputDirectory(new InputFileSystemDirectory("path-to-directory-where-fancybox.sty-located"));
```

このオプションでTEXジョブを実行した後(必要に応じて他のオプションを調整することを忘れないでください)、出力ドキュメント(つまり、PNG画像)を取得します。

![出力ドキュメント](/tex/images/java/Conversion-RequiredInputFs.png)

これが例の完全なソースコードです。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.java" >}}

### 必要な入力( `pgfplots`パッケージ)アーカイブ

次に、次の非常に単純なLaTexファイルもあります。これは、`required-input-zip.tex`です。


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

3行目では、このファイルが`pgfplots`パッケージを必要としていることがわかりますが、これも「ネイティブ」サポートされていません。ここでも、`pgfplots` パッケージのソースファイルが存在することを前提としています。これは、LaTeX 組版アプリケーションのインストールディレクトリで見つけると、2つの場所に分かれた非常に大きなファイルセットです。`pgfplots` フォルダは、`\tex\generic` フォルダと `\tex\latex` フォルダの両方にあります。そして、これら両方のフォルダの内容は、Aspose.TeX ライブラリへの必須入力として提供する必要があります。これらのソースファイルを ZIP アーカイブにパッケージ化したいので、アーカイブのレイアウトは以下のようになります。

![アーカイブのレイアウト](/tex/images/java/pgfplots-zip-layout.png)

そして、これらのソースファイルへのアクセスを指定する方法は次のとおりです。

```Java
final Stream zipStream = File.Open("path-to-zip-with-pgfplots-sources"), FileMode.Open))
try {
    ...
    options.setRequiredInputDirectory(new InputZipDirectory(zipStream));
    ...
} finally {
    if (zipStream != null)
        zipStream.close();
}

```

このオプションでTEXジョブを実行した後、出力ドキュメントを取得します。

![出力ドキュメント](/tex/images/java/Conversion-RequiredInputZip.png)

これが例の完全なソースコードです。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-RequiredInput-Zip.java" >}}

> **_注意:_** この結果は `pgfplots` パッケージのバージョン 1.18.1 を使用して検証されました。**Aspose.TeX** ライブラリに含まれる `pfg` パッケージのバージョンは 3.1.9a です。

### 外部フォントパッケージを使用します

通常、LaTeXディストリビューションには、タイプセッティングに使用できるデフォルトのフォントがいくつか付属しています。これらのフォントに加えて、**Aspose.TeX** は `amsfonts`、`eurosym`、`wasysym` といった非標準フォントパッケージも提供しています。前述の通り、**Aspose.TeX** は外部パッケージの使用もサポートしていますが、ここでは主にフォントを含まないパッケージに焦点を当ててきました。

**Aspose.TeX** の *Object TeX* エンジン拡張機能には、フォント マップが必要です。フォント マップは、各 TeX の内部フォント名に対応する物理フォントを指定する、拡張子 `.map` を持つテキスト ファイルです。これらのフォント マップは、初期化フェーズで TeX のメモリに読み込む必要があり、パッケージ ファイルに含める必要があります。エンジンはすべてのフォント マップの名前を認識していないため、拡張子 `.map` を持つファイルを検索します。そのため、[RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--) オプションの値として使用される [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/) インターフェイスの実装では、拡張子に基づいてファイル名のコレクションにアクセスする方法を提供する必要があります。具体的には、この実装は[IFileCollector](https://reference.aspose.com/tex/java/com.aspose.tex/ifilecollector/)インターフェースも実装する必要があります。標準実装である[InputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputfilesystemdirectory/)と[InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/)は既にこの要件を満たしています。

以下に、[IFileCollector](https://reference.aspose.com/tex/java/com.aspose.tex/ifilecollector/) インターフェースも実装した、カスタムの必須入力ディレクトリの例を示します。ここでは拡張子に基づいてファイル名を収集することに重点を置いており、ファイルの保存と取得の詳細については意図的に省略しています。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-RequiredInputDirectory.java" >}}

### 制限

ラテックスファイルに必要なパッケージは、 *LaTeX3e*カーネルの下で開発できます。このようなパッケージは、**Aspose.TeX**ライブラリで動作しない可能性が最も高くなります。後者は*latex2e*カーネルに基づいているためです。

また、ラテックスファイルが必要とするパッケージは、**Aspose.TeX**ライブラリの*オブジェクトtex*エンジンによってサポートされていないデバイス依存のプリミティブコマンドを直接呼び出すことができます。残念ながら、このようなパッケージは確かに機能しません。