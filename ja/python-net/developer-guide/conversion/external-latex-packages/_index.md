---
translation: true
template: /templates/_template-python-net.md
title: 外部ラテックスパッケージ| .NET経由でPython用のAspose.TeX
linktitle: 外部ラテックスパッケージ
weight: 19
url: /python-net/external-latex-packages/
description: PythonのAspose.TeX APIは、FancyBoxやPGFPlotsパッケージなど、ライブラリ自体に含まれていない外部パッケージの使用をサポートしています
lastmod: "2025-06-09"
---

{{<section overview>}}

## 外部ラテックスパッケージ

**Aspose.TeX**ライブラリには、さまざまな[一般的なラテックスパッケージ](/tex/{{lang.url-fragment}}net/embedded-packages/)が付属しているため、これらのパッケージをTexエンジンに手動で提供する必要はありません。ただし、ラテックスファイルには、ライブラリのパッケージの「バンドル」に含まれていないパッケージが必要な状況がある場合があります。そのような場合、[rebused_input_directory](https://reference.aspose.com/tex/python-net/Aspose.TeX/texoptions/required_input_directory/)[texoptions](https://reference.aspose.com/tex/python-net/Aspose.TeX/texoptions/)クラスインスタンスのオプションを介して、必要なパッケージのソースファイルなど、必要な入力を提供してみてください。これが2つの例でどのように機能するかを探ります。

まず[ライセンス](/tex/{{lang.url-fragment}}python-net/licensing/)を適用します。`ASPOSE_TEX_INPUT_DIR` に、2 つの `.tex` ファイルと `packages` サブフォルダーを含む `ExternalLaTeXPackages` の親フォルダーを指定します（既定値：`input`）。`ASPOSE_TEX_OUTPUT_DIR` に出力フォルダーを指定します（既定値：`output`）。

### 未梱包のフォーム(`fancybox`パッケージ)で提供される必要な入力。

「required-input-fs.tex」という名前の次の基本的なラテックスファイルがあるとします。これは[サンプルソリューション](https://GitHub.com/aspose-tex/Aspose.TeX-for-Python-.NET)の一部です。

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

ファイルの3行目は、「ネイティブ」サポートには含まれていない「Fancybox」パッケージが必要であることを示しています。 「Fancybox」パッケージのソースファイルがあると仮定しましょう。単一のファイルで構成される単純なパッケージであるため、このファイルをファイルシステムのどこにでも配置して、次のようにディレクトリパスを指定できます。


```Python
from aspose.tex.io import InputFileSystemDirectory

# Configure an existing TeXOptions instance.
options.required_input_directory = InputFileSystemDirectory('path-to-directory-where-fancybox.sty-located')
```

このオプションでTEXジョブを実行したら(必要に応じて他のオプションを調整することを忘れないでください)、この場合はPNG画像である出力ドキュメントを取得します。

![出力ドキュメント](/tex/images/python-net/Conversion-RequiredInputFs.png)

これが例の完全なソースコードです。

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.py" >}}

### アーカイブフォームで必要な入力を提供する(`pgfplots`パッケージ)

次に、「必要な入力Zip.tex」という名前の次のLaTexファイルがあるとします。これは、例のソリューションからの簡単なファイルでもあります。


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

3行目では、ファイルが「ネイティブに」サポートされていない`pgfplots`パッケージが必要であることが観察できます。繰り返しになりますが、`pgfplots`」パッケージのソースファイルを所有していると仮定すると、これらのファイルは非常に多く、LaTexタイプセットアプリケーションのインストールディレクトリ内の2つの異なるディレクトリにあります。 `pgfplots`フォルダーは、`\tex\generic`と` \ tex \ latex`ディレクトリの両方にあります。 Aspose.TeXライブラリが正しく機能するには、これらの両方のフォルダーの内容を入力として提供する必要があります。これを達成するために、これらのソースファイルをzipアーカイブにパッケージ化したいと考えています。以下は、アーカイブの目的のレイアウトです。

![アーカイブのレイアウト](/tex/images/python-net/pgfplots-zip-layout.png)

そして、これらのソースファイルへのアクセシビリティを定義する方法は次のとおりです。

```Python
from aspose.tex.io import InputZipDirectory

# Configure an existing TeXOptions instance and run the job while the stream is open.
with open("path-to-zip-with-pgfplots-sources", "rb") as zip_stream:
    options.required_input_directory = InputZipDirectory(zip_stream, "")
    # Run TeXJob here, as shown in the complete example below.
```

このオプションでTEXジョブを実行した後、出力ドキュメントを取得します。

![出力ドキュメント](/tex/images/python-net/Conversion-RequiredInputZip.png)

これが例の完全なソースコードです。

{{< gist "aspose-com-gists" "fce5c70784ba7a4d2597b459d63adbf1" "Aspose.TeX.Examples-Conversion-RequiredInput-Zip.py" >}}

> **_注意:_** この結果は `pgfplots` パッケージのバージョン 1.18.1 を使用して検証されました。**Aspose.TeX** ライブラリに含まれる `pfg` パッケージのバージョンは 3.1.9a です。

<!--
### 外部フォントパッケージの使用

通常、LaTeX ディストリビューションには、組版に使用できる定義済みのフォントセットが付属しています。しかし、**Aspose.TeX** には、これらのデフォルトフォントに加えて、`amsfonts`、`eurosym`、`wasysym` などの非標準フォントパッケージも含まれています。前述のように、Aspose.TeX は外部パッケージの使用もサポートしていますが、これまでの説明のほとんどはフォントを含まないパッケージに焦点を当てていました。

**Aspose.TeX** の *Object TeX* エンジン拡張機能では、各 TeX の内部フォント名に対応する物理フォントを決定するために、`.map` 拡張子を持つ特定の形式のテキスト ファイルであるフォント マップが必要です。これらのフォント マップは、初期化フェーズで TeX のメモリに読み込む必要があり、使用しているパッケージに含まれている必要があります。エンジンはすべてのフォント マップの名前を認識していないため、`.map` 拡張子を持つファイルを検索します。そのため、[required_input_directory](https://reference.aspose.com/tex/python-net/Aspose.TeX/texoptions/required_input_directory/) オプションに値を指定する場合、[IInputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/) インターフェイスの実装で、拡張子によるファイル名のコレクションへのアクセスを許可する必要があります。さらに、この実装では [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/) インターフェイスも実装する必要があります。[InputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputfilesystemdirectory/) や [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/) などの標準実装は、既にこれらの要件を満たしています。

以下は、[IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/) インターフェイスの実装方法を示す、カスタムの必須入力ディレクトリの例です。この例では、拡張子によるファイル名の収集に重点を置き、ファイルの保存と取得の詳細は意図的に省略しています。


-->

### 制限

*latex3e*カーネルANの下で開発されたパッケージに出くわした場合、LaTexファイルで必要とされている場合、**Aspose.TeX**ライブラリを使用する可能性は低いです。これは、ライブラリが * latex2e *カーネルに基づいているためです。

さらに、ラテックスファイルに必要なパッケージが、**Aspose.TeX**ライブラリの*オブジェクトtex*エンジンによってサポートされていないデバイス依存のプリミティブコマンドを直接使用する場合があります。そのような場合、パッケージはライブラリで動作しません。