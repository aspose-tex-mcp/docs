---
translation: true
template: /_templates/_customize-output-net.md
title: カスタム出力 TeX を作成 | .NET API ソリューション
url: /net/customize-output/
description: "TeX で動作する .NET API ソリューション。数行の C# コードで TeX ファイルのカスタム出力を作成する方法の例を読んでください。"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: 出力をカスタマイズする
h2: "TeX ファイルの出力をカスタマイズする .NET API ソリューション"
---

{{<section overview>}}
---
p1: "TeX は組版言語として知られています。これは、ドキュメント内のテキストをフォーマットせずに、プレーン テキストをコマンドと共に入力することを意味します。"
p2: "ドキュメンテーションの [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) の記事では、TeX ファイルにはタイプセットするデータは含まれず、制御シーケンスのみが含まれる可能性があることを教えています。 .それでも、通常はそのようなデータが含まれており、ターゲット形式のファイルにはタイプセットされたテキストがあります。このファイルは、入力として指定されたファイルと同じ名前も持ち、メインの出力ファイルになります。元の TeX の場合、これは DVI 形式のファイルです。ジョブ名を拡張せずに、入力ファイルと出力ファイルの両方の名前を呼び出します。"
p3: "このページには、TeX ファイルの出力をカスタマイズする方法を確認できるカスタム TeX 形式ファイルの作成を説明するコード例があります。 .tex ファイルの出力をカスタマイズするには、次のものが必要です。"
p4: "Aspose.TeX for .NET API は、C# プラットフォーム向けの機能豊富で強力で使いやすいドキュメント操作および変換 API です。"
p5: "NuGet パッケージ マネージャーを開き、Aspose.TeX を検索してインストールします。パッケージ マネージャー コンソールから次のコマンドを使用することもできます。"
---

{{<section feature1>}}
---
title: "TeX 出力 C# をカスタマイズする手順:"
h3: "TeX 出力カスタマイズ用の C# コード"
item1: "[*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) [*TeXOptions*](https://reference.aspose) のメソッドの助けを借りて.com/tex/net/aspose.tex/texoptions/) クラス、ObjectTeX エンジン拡張時にフォーマットなしの TeX エンジン オプションを作成します。"
item2: "[*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) クラスを使用して、入力用のファイル システム作業ディレクトリを指定します。"
item3: "[*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) クラスを使用して、出力用のファイル システム作業ディレクトリを指定します。"
item4: "新しいフォーマットを作成するには、[*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) メソッドを使用します。"
item5: 出力を絞り込みます。
---