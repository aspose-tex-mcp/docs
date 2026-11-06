---
translation: true
template: /templates/_template-python-net.md
title: メインのTEX入力ファイルを提供する代替方法| .NET経由でPython用のAspose.TeX
linktitle: メインのTex入力ファイルを提供する他の方法
weight: 14
url: /python-net/other-ways-of-main-input/
description: Python用のAspose.TeX APIソリューションには、最初の引数としてストリームを受け入れるコンストラクターが含まれ、変換機能を提供します。
lastmod: "2025-06-09"
---

{{<section overview>}}

## ストリームを使用してメイン入力ファイルをTexエンジンに提供する

これまでのところ、[メイン入力ファイル](/tex/{{lang.url-fragment}}net/tex-io/#tex-input)をTEXエンジンにファイル名として提供する方法を学びました。ただし、最初の引数としてストリームを受け入れる[Texjob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/)クラスで利用可能な[別のコンストラクター](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#io.RawIOBase-aspose.tex.presentation.Device-aspose.tex.TeXOptions)があります。これは、何らかの理由で、メインの入力ファイルがディスクファイルシステム上のファイルの形式でない場合に役立ちます。これがどのように実装できるかの例です。

`ASPOSE_TEX_OUTPUT_DIR` に出力ディレクトリを指定します（既定値：`output`）。事前にライセンスを適用してください。 [Licensing](/tex/ja/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputStream.py" >}}

完全な LaTeX 文書をバイナリ `BytesIO` ストリームに変換し、`TeXConfig.object_latex` を設定した `TeXJob` に渡します。ジョブ中はストリームを開いたままにします。出力は `texput.xps` と `texput.log` です。

すべての出力ファイルには「Texput」という名前が付けられていることに注意してください。これは、エンジンが他の名前にアクセスできないためです。 「Texput」はデフォルトのジョブ名です。ジョブ名[Tex Output](/tex/{{lang.url-fragment}}net/tex-io/#tex-output)および[ジョブ名の設定方法](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name)の段落に関する詳細情報を見つけることができます。

## 端末からメインのTEX入力ファイルを入力します

[Texjob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/)クラスで利用可能な[もう1つのコンストラクター](https://reference.aspose.com/tex/python-net/Aspose.TeX/texjob/__init__/#Aspose.TeX.presentation.Device-Aspose.TeX.TeXOptions)があり、入力をまったく指定できません。あなたはそのようなTexの仕事が何を処理するのか疑問に思っているかもしれません。この場合、入力端子を使用する必要があります。 TEXエンジンは、端末からファイル名を入力するように促します。

これがコードです：

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

次の plain TeX を `hello-world.tex` として `ASPOSE_TEX_INPUT_DIR`（既定値：`input`）に保存してください。例は `TeXConfig.object_tex()` を使用します。入力を求められたら `hello-world.tex` と入力して Enter を押すか、標準入力からファイル名を渡します。出力は `hello-world.xps` と `hello-world.log` です。

```tex
Hello, World!
\end
```
