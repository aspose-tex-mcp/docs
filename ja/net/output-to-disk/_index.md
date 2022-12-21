---
translation: true
template: /_templates/_output-to-disk-net.md
title: TeX 出力をディスクに書き込む | .NET API ソリューション
url: /net/output-to-disk/
description: "TeX で動作する .NET API ソリューション。数行の C# コードで TeX ファイルのカスタム出力を作成する方法を例で学びます。Aspose"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: TeX 出力をディスクに書き込む
h2: "TeX ファイル変換の結果を C# .NET 経由でディスクとして保存する"
---

{{<section overview>}}
---
p1: "TeX は組版言語として知られています。つまり、ドキュメント内のテキストをフォーマットするのではなく、コマンドと共にプレーン テキストを入力します。ドキュメントの [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) の記事からわかるように、TeX ジョブは明示的に指定された TeX ファイルで実行されます。そこには、TeX の入力と出力に関連する TeX の対話モードとプリミティブに関する情報も記載されています。"
p2: "TeX の主な用途は、数学的または技術的な文章の作成を支援することです。しかし、ファイルが既に作成されていて、それ以上操作したくない場合は、別のより一般的な形式に変換することをお勧めします。"
p3: "このページでは、入力と出力にファイル システム ディレクトリを使用する方法、XPS デバイスに出力する方法、ジョブ名をオーバーライドする方法、ターミナル出力をディスクに書き込む方法を説明するコード例を示します。簡単に言えば、出力をディスクに書き込む変換です。このような操作を実行するには、次のものが必要です。"
p4: "Aspose.TeX for .NET API は、C# プラットフォーム向けの機能豊富で強力で使いやすいドキュメント操作および変換 API です。"
p5: "NuGet パッケージ マネージャーを開き、Aspose.TeX を検索してインストールします。パッケージ マネージャー コンソールから次のコマンドを使用することもできます。"
---

{{<section feature1>}}
---
title: "端末出力をディスク C# に書き込む手順:"
h3: "TeX を変換して出力をディスクに書き込むための C# コード"
item1: "[*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) クラス。"
item2: "TeXJobコンストラクターの第一引数をジョブ名とみなしたくない場合は、ジョブ名を指定してください。"
item3: "入力用のファイル システム作業ディレクトリを指定します。 [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) クラスを使用します。"
item4: "[*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) クラスのエンティティを使用して、出力用のファイル システム作業ディレクトリを指定します。"
item5: "端末出力を出力作業ディレクトリ内のファイルに書き込む必要があることを指定します。"
item6: "ジョブを実行 [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)。"
---