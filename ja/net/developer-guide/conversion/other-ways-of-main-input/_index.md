---
translation: true
template: /templates/_template-net.md
title: メイン TeX 入力ファイルを提供するその他の方法 | .NET
linktitle: メイン TeX 入力ファイルを提供するその他の方法
weight: 14
url: /net/other-ways-of-main-input/
description: Aspose.TeX API ソリューション for .NET の変換機能は、最初の引数としてストリームを受け取るコンストラクタを持っています。いくつかのコード例を示します。
lastmod: "2026-02-25"
---

{{<section overview>}}

## TeX エンジンへのメイン入力ファイルをストリームとして提供する

これまで、[メイン入力ファイル](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) をフルパスでも短縮形でも、拡張子の有無に関わらず、ファイル名として TeX エンジンに渡す方法しか知りませんでした。しかし、`TeXJob` クラスには別の[コンストラクタ](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) があり、最初の引数としてストリームを受け取ります。ディスク上のファイル以外の形でメイン入力ファイルを保持している場合に便利です。実装例は次のとおりです:

{{< gist "aspose-com-gists" "4e3bae6ecbe041bcb411e0cf4c98dc71" "Example-StreamInput-LaTeX.cs" >}}

すべての出力ファイルは名前 *texput* になります。これはエンジンが他の名前を取得できないためです。*texput* はデフォルトのジョブ名です。[ここ](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) と[ここ](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name) にジョブ名に関する詳細があります。

## ターミナルからメイン TeX 入力ファイルを入力する

`TeXJob` クラスの別の[コンストラクタ](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) は、入力を全く指定できません。では、こうした TeX ジョブは何を処理するのかと疑問に思うかもしれません。この場合、入力ターミナルが必要です。TeX エンジンはターミナルからファイル名の入力を求めます。

{{< gist "aspose-com-gists" "4e3bae6ecbe041bcb411e0cf4c98dc71" "Example-MainInputTerminal.cs" >}}

実行すると、エンジンはファイル名の入力（パスの有無、拡張子の有無）を待機します。


![ターミナルウィンドウ](/tex/images/net/Conversion-MainInputTerminal.png)

そして、コンソール上の出力ターミナルは次のようになります:


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
