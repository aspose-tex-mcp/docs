---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: ディスクから TeX をロードする | .NET API ソリューション
url: /net/load-tex-from-disk/
description: "TeX で動作する .NET API ソリューション。この例では、数行の C# コードでディスクから TeX ファイルをロードする方法を学びます。"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: TeX ソース ファイルをディスクからロードする
h2: "ディスクから TeX/LaTeX ファイルをロードする .NET API ソリューション"
---

{{<section overview>}}
---
p1: "TeX は組版言語として知られています。これは、ドキュメント内のテキストをフォーマットせずに、プレーン テキストをコマンドと共に入力することを意味します。出力として、必要な (指定された) 形式のフォーマット済みファイルが得られます。 [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) は、パブリケーション セット システム (コンピューター組版) の中心的なコアです。 TeX ジョブは、明示的に指定された TeX ファイルで実行されます。 TeX の入力と出力の理解を深めるには、ドキュメントの [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) を学習してください。"
p2: "知られているように、TeX の主な目的は、数学的または技術的なテキストの作成を支援することです。ただし、操作の前に、ファイルを最初にロードする必要があります。ここでは、入力と出力にファイル システム ディレクトリを使用してディスクから TeX ソース ファイルをロードする方法、XPS デバイスに出力する方法、端末出力をコンソールに書き込む方法を説明するコード スニペットがあります。"
p3: "必要な例を実行するには:"
p4: "Aspose.TeX for .NET API は、C# プラットフォーム向けの機能豊富で強力で使いやすいドキュメント操作および変換 API です。"
p5: "NuGet パッケージ マネージャーを開き、Aspose.TeX を検索してインストールします。パッケージ マネージャー コンソールから次のコマンドを使用することもできます。"
---

{{<section feature1>}}
---
title: ディスク C# から TeX をロードする手順。
h3: "TeX をロードするための C# コード"
item1: "[*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) のメソッド [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) クラス。"
item2: "入力用のファイル システム作業ディレクトリを指定します。 [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) クラスを使用します。"
item3: "[*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) クラスを使用して、出力用のファイル システム作業ディレクトリを指定します。"
item4: "[*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) クラスを使用して、コンソールを出力ターミナルとして指定します。"
item5: "必要に応じてメモリ端子を出力端子として指定してください。このために [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/) クラスを使用します。"
item6: "ジョブを実行 [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)。"
item7: 出力を絞り込みます。
---