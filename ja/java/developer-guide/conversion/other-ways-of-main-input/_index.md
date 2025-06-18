---
translation: true
template: /templates/_template-java.md
title: メインのTex入力ファイルを提供する他の方法| Java
linktitle: メインのTex入力ファイルを提供する他の方法
weight: 14
url: /java/other-ways-of-main-input/
description: JavaのAspose.TeX APIソリューションの変換機能には、最初の引数としてストリームを受け入れるコンストラクターがあります。いくつかのコードの例を次に示します。
lastmod: "2025-06-09"
---

{{<section overview>}}

## メイン入力ファイルをTexエンジンにストリームとして提供する

この時点まで、[メイン入力ファイル](/tex/{{lang.url-fragment}}net/tex-io/#tex-input)をファイル名としてTEXエンジンに渡す方法、完全に指定されているか短い形式で、拡張機能であろうとそれなしで渡す方法を知っていました。しかし、最初の引数としてストリームを受け入れる「Texjob」クラスの別の[コンストラクター](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXJob#TeXJob-java.io.InputStream-com.Aspose.TeX.rendering.Device-com.Aspose.TeX.TeXOptions-)があります。これは、何らかの理由でディスクファイルシステム上のファイル以外のフォームにメインの入力ファイルがある場合に便利です。これに対処する方法は次のとおりです。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-InputStream.java" >}}

すべての出力ファイルには *texput*という名前が付いていることに注意してください。これは、エンジンが他の名前をどこにでも入手できないためです。 *texput*はデフォルトのジョブ名です。ジョブ名の詳細については、[ここ](/tex/{{lang.url-fragment}}net/tex-io/#tex-output)および[here](/tex/{{lang.url-fragment}}java/other-options/#how-to-set-the-job-name)を参照してください。

## ターミナルからメインTEX入力ファイルを入力します

「Texjob`クラスにはさらに別の[コンストラクター](https://reference.aspose.com/tex/java/com.Aspose.TeX/TeXJob#TeXJob-com.Aspose.TeX.rendering.Device-com.Aspose.TeX.TeXOptions-)がありますが、入力をまったく指定することはできません。それで、そのようなTexの仕事は何を処理しようとしているのでしょうか？今回は入力端子が必要です。 Texエンジンは、端末からファイル名を入力するように依頼します。

これがコードです：

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-MainInputTerminal.java" >}}

実行されるとすぐに、エンジンがスティックし、ファイル名を入力するのを待っています(パスの有無にかかわらず、拡張機能の有無にかかわらず)：


![端子ウィンドウ](/tex/images/java/Conversion-MainInputTerminal.png)

そして、これはコンソールである出力端末をどのように見えるかです：

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