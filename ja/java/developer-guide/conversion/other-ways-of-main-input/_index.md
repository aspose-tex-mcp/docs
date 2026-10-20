---
translation: true
template: /templates/_template-java.md
title: メインのTex入力ファイルを提供する他の方法| Java
linktitle: メインのTex入力ファイルを提供する他の方法
weight: 14
url: /java/other-ways-of-main-input/
description: JavaのAspose.TeX APIソリューションの変換機能には、最初の引数としてストリームを受け入れるコンストラクターがあります。いくつかのコードの例を次に示します。
lastmod: "2026-04-21"
---

{{<section overview>}}

## メイン入力ファイルをTexエンジンにストリームとして提供する

この時点まで、[メイン入力ファイル](/tex/{{lang.url-fragment}}net/tex-io/#tex-input)をファイル名としてTEXエンジンに渡す方法、完全に指定されているか短い形式で、拡張機能であろうとそれなしで渡す方法を知っていました。しかし、最初の引数としてストリームを受け入れる「Texjob」クラスの別の[コンストラクター](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.io.InputStream-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-)があります。これは、何らかの理由でディスクファイルシステム上のファイル以外のフォームにメインの入力ファイルがある場合に便利です。これに対処する方法は次のとおりです。

`outputDirectory` に既存の出力フォルダーを指定します。例で使用する Aspose.TeX クラス、`com.aspose.tex.rendering.XpsDevice`、`com.aspose.tex.rendering.XpsSaveOptions`、ストリーム入力用の `java.io.ByteArrayInputStream` と `java.nio.charset.StandardCharsets` をインポートします。呼び出し元のメソッドは例外を処理するか宣言する必要があります。評価版の制限を避けるため、[ライセンスガイド](/tex/{{lang.url-fragment}}java/licensing/)に従ってライセンスを適用してください。ストリームの例には完全な LaTeX 文書が含まれるため、入力作業ディレクトリは不要です。ストリームとデバイスはジョブ終了まで開いたままにし、その後に閉じるか解放します。

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-StreamInput-LaTeX.java" >}}

ストリーム入力でジョブ名を明示的に指定しない場合、エンジンはデフォルト名 *texput* を使用します。この例は `texput.xps` と `texput.log` を作成します。別のジョブ名を選ぶには `options.setJobName(...)` を使用します。ジョブ名の詳細は [ここ](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) と [here](/tex/{{lang.url-fragment}}java/other-options/#how-to-set-the-job-name) を参照してください。

## ターミナルからメインTEX入力ファイルを入力します

「Texjob`クラスにはさらに別の[コンストラクター](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) がありますが、入力をまったく指定することはできません。それで、そのようなTexの仕事は何を処理しようとしているのでしょうか？今回は入力端子が必要です。 Texエンジンは、端末からファイル名を入力するように依頼します。

`inputDirectory` に `hello-world.ltx` という完全な LaTeX 文書を含むフォルダーを、`outputDirectory` に既存の出力フォルダーを指定します。コンソールで例を実行し、`**` プロンプトで `hello-world.ltx` を入力して Enter キーを押します。`hello-world.xps` が作成され、端末出力はコンソールに書き込まれます。両方の例は処理に `NonstopMode` を使用しますが、端末のコンストラクターは最初のファイル名を必要とします。無人実行には `IInputTerminal` の実装を提供するか、ファイルまたはストリーム入力を使用します。

これがコードです：

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-MainInputTerminal.java" >}}

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