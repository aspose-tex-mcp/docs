---
translation: true
template: /_templates/_output-to-zip-net.md
title: TeX から ZIP | .NET API ソリューション
url: /net/output-to-zip/
description: "TeX で動作する .NET API ソリューション。 TeX から ZIP への変換機能により、TeX ファイルを最も一般的なアーカイブとして保存できます。この機能の C# の例。"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: 出力を ZIP に書き込む
h2: "TeX ファイル変換の結果を C# .NET 経由で ZIP として保存します。"
---

{{<section overview>}}
---
p1: "TeX は、データ マークアップ言語の 1 つとして知られています。これは、出版物セット システム (コンピュータ組版) の主要なコアです。 [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) はプログラミング言語であるため、ファイル形式として考えるのは疑問です。一方、この言語を理解するのは通訳エンジンです。とにかく、要するに、その主な目的は、数学的または技術的なテキストの作成を支援することです。しかし、ファイルが既に作成されていて、それ以上操作したくない場合は、別のより一般的な形式に変換することをお勧めします。"
p2: "Aspose.TeX API ソリューションを使用すると、TeX ファイルを変換し、結果を ZIP アーカイブとして保存できます。ここでは、TeX を PDF に変換し、結果の出力を zip に保存する方法に関するコード スニペットを見つけることができます。 API コンバーターは、C# でサポートされている任意の言語を使用して TeX を変換します。ここに表示されている API を使用して、独自のクロスプラットフォーム アプリケーションを作成したり、.NET プロジェクトに統合したりすることもできます。このような [*クロスプラットフォーム コンバーター*](https://products.aspose.app/tex/conversion/tex) は、Aspose エコシステムにも存在します。しかし、必要な例を実行するには:"
p3: "Aspose.TeX for .NET API は、C# プラットフォーム向けの機能豊富で強力で使いやすいドキュメント操作および変換 API です。"
p4: "NuGet パッケージ マネージャーを開き、Aspose.TeX を検索してインストールします。パッケージ マネージャー コンソールから次のコマンドを使用することもできます。"
---

{{<section feature1>}}
---
title: 出力 TeX ファイル C# に ZIP ディレクトリを使用する手順。
h3: "出力に ZIP ディレクトリを使用するための C# コード"
item1: "[*TeXOptions クラス*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) のインスタンスを作成します。"
item2: "[*OutputWorkingDirectory*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) プロパティを使用して、出力用の ZIP アーカイブ作業ディレクトリを指定します。"
item3: "[*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) クラスを使用して、コンソールを出力ターミナルとして指定します。"
item4: "[*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/) クラスを使用して、保存のオプションを定義します。"
item5: "[*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) を使用して変換を実行 [*PdfDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/)"
item6: 出力を絞り込みます。
item7: "出力 ZIP アーカイブを完成させるには、[*OutputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) クラスを使用します。"
---