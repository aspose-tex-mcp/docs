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

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-InputStream.py" >}}

すべての出力ファイルには「Texput」という名前が付けられていることに注意してください。これは、エンジンが他の名前にアクセスできないためです。 「Texput」はデフォルトのジョブ名です。ジョブ名[Tex Output](/tex/{{lang.url-fragment}}net/tex-io/#tex-output)および[ジョブ名の設定方法](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name)の段落に関する詳細情報を見つけることができます。

## 端末からメインのTEX入力ファイルを入力します

[Texjob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/)クラスで利用可能な[もう1つのコンストラクター](https://reference.aspose.com/tex/python-net/Aspose.TeX/texjob/__init__/#Aspose.TeX.presentation.Device-Aspose.TeX.TeXOptions)があり、入力をまったく指定できません。あなたはそのようなTexの仕事が何を処理するのか疑問に思っているかもしれません。この場合、入力端子を使用する必要があります。 TEXエンジンは、端末からファイル名を入力するように促します。

これがコードです：

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}


実行されるとすぐに、エンジンは一時停止し、ファイル名を入力するのを待ちます(パスの有無にかかわらず、延長の有無にかかわらず)：


![端子ウィンドウ](/tex/images/python-net/.png)

そして、これが出力端子(コンソール)にどのように表示されるかを次に示します。

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode
**<path_to_the_file>/hello-world.ltx
(<path_to_the_file>/hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.xps (1 page).
Transcript written on hello-world.log.
```