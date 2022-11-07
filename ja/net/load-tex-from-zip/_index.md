---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: TeX を ZIP から読み込む | .NET API ソリューション
url: /net/load-tex-from-zip/
description: "TeX で動作する .NET API ソリューション。この例で、数行の C# コードで ZIP から TeX ファイルをロードする方法を学びます。"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: TeX ソースファイルを ZIP から読み込む
h2: "ZIP アーカイブから TeX ファイルをロードする .NET API ソリューション"
---

{{<section overview>}}
---
p1: "TeX は組版言語として知られています。これは、ドキュメント内のテキストをフォーマットせずに、プレーン テキストをコマンドと共に入力することを意味します。出力として、必要な (指定された) 形式のフォーマット済みファイルが得られます。 TeX の入力と出力の理解を深めるには、ドキュメントの [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) を学習してください。"
p2: "知られているように、TeX の主な目的は、数学的または技術的なテキストの作成を支援することです。ただし、操作の前に、ファイルを最初にロードする必要があります。ここでは、入力と出力に ZIP ディレクトリを使用して ZIP から TeX ソース ファイルをロードする方法、PDF デバイスに出力する方法、端末出力をコンソールに書き込む方法を説明するコード スニペットがあります。"
p3: ".tex ファイルをロードするには、次のものが必要です。"
p4: "Aspose.TeX for .NET API は、C# プラットフォーム向けの機能豊富で強力で使いやすいドキュメント操作および変換 API です。"
p5: "NuGet パッケージ マネージャーを開き、Aspose.TeX を検索してインストールします。パッケージ マネージャー コンソールから次のコマンドを使用することもできます。"
---

{{<section feature1>}}
---
title: "ZIP アーカイブ C# から TeX をロードする手順:"
h3: "TeX をロードするための C# コード"
item1: "ZIP アーカイブのストリームを開き、入力作業ディレクトリとして使用します。"
item2: "ZIP アーカイブのストリームを開き、出力作業ディレクトリとして使用します。"
item3: "[*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) のメソッド [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) クラス。"
item4: "入力用に ZIP アーカイブの作業ディレクトリを指定するか、アーカイブ内のパスを指定します。これには [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) クラスのコンストラクターを使用します。"
item5: "出力用の ZIP アーカイブ作業ディレクトリを指定するか、アーカイブ内のパスを指定します。これには [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) クラスのコンストラクターを使用します。"
item6: "[*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) クラスを使用して、コンソールを出力ターミナルとして指定します。"
item7: "[*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/) クラスを使用して保存オプションを定義します。"
item8: "ジョブを実行 [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)。"
item9: 出力を絞り込みます。
---