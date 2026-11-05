---
translation: true
template: /templates/_template-java.md
title: 外部ラテックスパッケージ| Aspose.TeX for Java 入門
linktitle: 外部ラテックスパッケージ
weight: 30
url: /java/external-latex-packages/
description: Java用のAspose.TeX APIでは、外部パッケージ、つまりFancyBoxやPGFPlotsパッケージなどのライブラリ自体に含まれていないパッケージを使用できます。
lastmod: "2025-06-09"
---

{{<section overview>}}

## 外部ラテックスパッケージ

Javaの**Aspose.TeX**ライブラリには、[一般的なラテックスパッケージ](/tex/{{lang.url-fragment}}net/embedded-packages/)が含まれています。したがって、これらのパッケージをライブラリのTexエンジンに提供する方法に注意する必要はありません。しかし、(おそらく)ラテックスファイルには、パッケージの「ネイティブにサポートされている「バンドル」を超えたパッケージが必要になる場合があります。この場合、[setRequiredInputDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#setRequiredInputDirectory-com.Aspose.TeX.IInputWorkingDirectory-)[texoptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/)クラスインスタンスのメソッドを使用して、必要な入力、つまり必要なパッケージのソースファイルを提供することを試みることができます。これが2つの例でどのように機能するかを確認します。

`inputFile` に対応する LaTeX 文書の完全なパスを、`outputDirectory` に既存の出力フォルダーを指定します。両方の変換例は 150 DPI の PNG を生成します。選択した例の Aspose.TeX クラス、`com.aspose.tex.rendering.ImageDevice`、`com.aspose.tex.rendering.PngSaveOptions`、ZIP 入力用の `java.io.InputStream` と `java.nio.file.Files` をインポートします。呼び出し元のメソッドは例外を処理するか宣言します。[ライセンスガイド](/tex/{{lang.url-fragment}}java/licensing/)に従ってライセンスを適用してください。

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
  \begin{Beqnarray}
  y & = & x^2 \\
  a^2 + 2ab + b^2 & = & (a + b)^2 \\
  \int_0^\infty e^{-ax} dx & = & \frac{1}{a}
  \end{Beqnarray}
}
\end{document}
```

3 行目では外部パッケージ `fancybox` が必要です。`packagesDirectory` に `fancybox.sty` とその依存ファイルを含むローカルフォルダーを指定します。以下の完全な例はこのフォルダーを `RequiredInputDirectory` に設定し、PNG 画像を生成します。デバイスと作業ディレクトリはジョブ終了まで開いたままにし、その後に解放または閉じます。

![出力ドキュメント](/tex/images/java/Conversion-RequiredInputFs.png)

これが例の完全なソースコードです。

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RequiredInput-FileSystem.java" >}}

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

`packagesZip` に、パッケージの generic と LaTeX のソースを含むアーカイブへの `java.nio.file.Path` を指定します。以下の完全な Java 例は `Files.newInputStream(...)` で開き、`InputZipDirectory` を `RequiredInputDirectory` に設定します。空のベースパス引数はアーカイブ全体を選択します。TeX ジョブが終了するまで ZIP ストリームとディレクトリを開いたままにし、その後に閉じます。結果は 2 つのグラフを含む PNG 画像です。

![出力ドキュメント](/tex/images/java/Conversion-RequiredInputZip.png)

これが例の完全なソースコードです。

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RequiredInput-Zip.java" >}}

> **_注意:_** この結果は `pgfplots` パッケージのバージョン 1.18.1 を使用して検証されました。**Aspose.TeX** ライブラリに含まれる `pfg` パッケージのバージョンは 3.1.9a です。

### 外部フォントパッケージを使用します

通常、LaTeXディストリビューションには、タイプセッティングに使用できるデフォルトのフォントがいくつか付属しています。これらのフォントに加えて、**Aspose.TeX** は `amsfonts`、`eurosym`、`wasysym` といった非標準フォントパッケージも提供しています。前述の通り、**Aspose.TeX** は外部パッケージの使用もサポートしていますが、ここでは主にフォントを含まないパッケージに焦点を当ててきました。

**Aspose.TeX** の *Object TeX* エンジン拡張機能には、フォント マップが必要です。フォント マップは、各 TeX の内部フォント名に対応する物理フォントを指定する、拡張子 `.map` を持つテキスト ファイルです。これらのフォント マップは、初期化フェーズで TeX のメモリに読み込む必要があり、パッケージ ファイルに含める必要があります。エンジンはすべてのフォント マップの名前を認識していないため、拡張子 `.map` を持つファイルを検索します。そのため、[RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--) オプションの値として使用される [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/) インターフェイスの実装では、拡張子に基づいてファイル名のコレクションにアクセスする方法を提供する必要があります。具体的には、この実装は[IFileCollector](https://reference.aspose.com/tex/java/com.aspose.tex/ifilecollector/)インターフェースも実装する必要があります。標準実装である[InputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputfilesystemdirectory/)と[InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/)は既にこの要件を満たしています。

以下のカスタム `RequiredInputDirectory` は両方のインターフェースを実装し、明示的に登録されたローカルファイルを読み込みます。含まれる import とともに `RequiredInputDirectory.java` として保存します。各ファイルを `storeFileName(...)` で登録し、`options.setRequiredInputDirectory(...)` でインスタンスを設定して、ジョブ終了後に閉じます。階層を持たないレジストリなので、完全なパスを指定せずに要求するファイル名は一意である必要があります。拡張子の比較は大文字と小文字を区別せず、任意の収集パスでファイルシステムのディレクトリを選択できます。必要なパッケージ、フォントマップ、メトリック、実際のフォントファイルをすべて登録します。ファイル収集によりマップを検出できますが、不足するフォントデータは提供されません。

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-RequiredInputDirectory.java" >}}

### 制限

ラテックスファイルに必要なパッケージは、 *LaTeX3e*カーネルの下で開発できます。このようなパッケージは、**Aspose.TeX**ライブラリで動作しない可能性が最も高くなります。後者は*latex2e*カーネルに基づいているためです。

また、ラテックスファイルが必要とするパッケージは、**Aspose.TeX**ライブラリの*オブジェクトtex*エンジンによってサポートされていないデバイス依存のプリミティブコマンドを直接呼び出すことができます。残念ながら、このようなパッケージは確かに機能しません。