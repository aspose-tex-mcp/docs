---
translation: true
template: /templates/_template-net.md
title: .NET 用 Aspose.TeX コンバータ – FAQ
linktitle: よくある質問
type: docs
weight: 90
url: /net/conversion/faq/
description: Aspose.TeX for .NET による TeX ファイルと LaTeX ファイルの変換に関するよくある質問。サポートされている形式、変換コード、ストリームへの出力、画像オプション、パッケージ、評価モード、実行環境の要件について説明します。
keywords: Aspose.TeX, .NET, FAQ, LaTeX 変換, LaTeX から PDF, LaTeX から XPS, LaTeX から SVG, LaTeX から PNG, TeXJob, ライセンス, Linux
lastmod: "2026-11-02"
---

{{<section overview>}}

<br><br>

**Q: Aspose.TeX for .NET はどのような入力形式と出力形式をサポートしていますか?**

**A:** Aspose.TeX は TeX と LaTeX のドキュメントを組版します。メイン入力ファイルは、ファイル、ストリーム、またはターミナルから渡すことができます。メイン入力ファイルが読み込むファイルは、フォルダーまたは ZIP アーカイブから取得できます。単一の LaTeX 数式や LaTeX フラグメントは、専用の API でレンダリングできます。出力形式は PDF、XPS、SVG、PNG、JPEG、BMP、TIFF です。[サポートされているファイル形式](/tex/{{lang.url-fragment}}net/supported-file-formats/)を参照してください。
<br><br>

**Q: Aspose.TeX で LaTeX を Word (DOCX) や HTML に変換できますか?**

**A:** いいえ。Aspose.TeX が出力するのは PDF、XPS、SVG、ラスター画像だけです。別の形式が必要な場合は、その形式をサポートするライブラリで PDF 出力を変換してください。
<br><br>

**Q: C# で LaTeX ファイルを PDF に変換するにはどうすればよいですか?**

**A:** ObjectLaTeX 形式の `TeXOptions` を作成し、出力ディレクトリと `PdfSaveOptions` を設定して、`PdfDevice` を指定した `TeXJob` を実行します。

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPDF-Simplest.cs" >}}

結果は、ジョブ名で出力作業ディレクトリに書き込まれます。[LaTeX から PDF へ](/tex/{{lang.url-fragment}}net/latex-to-pdf/)を参照してください。
<br><br>

**Q: 出力形式はどのように選択しますか?**

**A:** `TeXOptions.SaveOptions` を設定し、対応するデバイスを `TeXJob` に渡します。

| 形式 | 保存オプション | デバイス |
|---|---|---|
| PDF | `PdfSaveOptions` | `PdfDevice` |
| XPS | `XpsSaveOptions` | `XpsDevice` |
| SVG | `SvgSaveOptions` | `SvgDevice` |
| PNG、JPEG、BMP、TIFF | `PngSaveOptions`、`JpegSaveOptions`、`BmpSaveOptions`、`TiffSaveOptions` | `ImageDevice` |

[LaTeX から XPS へ](/tex/{{lang.url-fragment}}net/latex-to-xps/)と[LaTeX から画像へ](/tex/{{lang.url-fragment}}net/latex-to-image/)を参照してください。
<br><br>

**Q: 結果をファイルではなくメモリ上で取得できますか?**

**A:** はい。`PdfDevice` と `XpsDevice` には、ドキュメントの書き込み先となる `Stream` を受け取るコンストラクターがあります。`ImageDevice` は、レンダリングしたページを `Result` プロパティにバイト配列の配列 (1 ページにつき 1 つ) として保持します。メイン入力をストリームから読み込むには、ストリームを `TeXJob` のコンストラクターに渡します。[LaTeX から PDF へ](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file)と[メイン TeX 入力ファイルを提供するその他の方法](/tex/{{lang.url-fragment}}net/other-ways-of-main-input/)を参照してください。
<br><br>

**Q: 画像の解像度と品質はどのように制御しますか?**

**A:** 画像の保存オプションの次のプロパティを使用します。

- `Resolution` — 画像の解像度 (DPI)。
- `SmoothingMode` と `InterpolationMode` — レンダリング品質。
- `TiffSaveOptions.Compression` と `TiffSaveOptions.Multipage` — TIFF の圧縮と、全ページを 1 つのファイルに保存するかどうか (マルチページ TIFF は `Aspose.TeX.Drawing` パッケージではまだサポートされていません)。

たとえば、`new PngSaveOptions { Resolution = 300 }` は 300 DPI の PNG 画像を生成します。[LaTeX から画像へ](/tex/{{lang.url-fragment}}net/latex-to-image/)を参照してください。
<br><br>

**Q: 変換が成功したかどうかはどのように確認しますか?**

**A:** `TeXJob.Run()` は `TeXJobResult` 値 (`Spotless`、`WarningIssued`、`ErrorMessageIssued`、`FatalErrorStop` のいずれか) を返します。詳細は、出力ディレクトリのトランスクリプト (`.log`) ファイルと出力ターミナルに書き込まれます。[Aspose.TeXの出力インターフェイス](/tex/{{lang.url-fragment}}net/aspose-tex-output/)を参照してください。
<br><br>

**Q: サーバーに LaTeX (MiKTeX など) をインストールする必要がありますか?**

**A:** いいえ。Aspose.TeX は、独自の TeX エンジン、LaTeX フォーマット、フォントを備えたスタンドアロンの .NET ライブラリです。外部の TeX ディストリビューションは必要ありません。
<br><br>

**Q: どの LaTeX パッケージを使用できますか?**

**A:** Aspose.TeX には組み込みの LaTeX パッケージ一式が含まれています。[埋め込まれたLaTeXパッケージ](/tex/{{lang.url-fragment}}net/embedded-packages/)を参照してください。その他のパッケージを使用するには、そのファイルをフォルダーまたは ZIP アーカイブに置き、`TeXOptions.RequiredInputDirectory` に指定します。[外部 LaTeX パッケージ](/tex/{{lang.url-fragment}}net/external-latex-packages/)を参照してください。
<br><br>

**Q: ドキュメント全体ではなく、単一の数式や LaTeX フラグメントをレンダリングできますか?**

**A:** はい。数式には `PngMathRenderer` または `SvgMathRenderer` を、任意の LaTeX フラグメントには `PngFigureRenderer` または `SvgFigureRenderer` を使用します。これらはレンダリングした画像のサイズを返します。[LaTeX 数式のレンダリング](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/)と[LaTeX 図のレンダリング](/tex/{{lang.url-fragment}}net/latex-figure-rendering/)を参照してください。
<br><br>

**Q: 実行環境の要件は何ですか?**

**A:**

- `Aspose.TeX` パッケージ: Windows (x64/x86)、.NET Framework 4.0 以降、.NET Standard 2.0、.NET 6 以降。
- `Aspose.TeX.Drawing` パッケージ: Windows、Linux、macOS (x64/Arm64)、.NET Framework 4.7.2 以降、.NET 7 以降。
- 追加のネイティブ ライブラリは必要ありません。Linux では、XPS と SVG の出力に ICU が必要です。[システム要件](/tex/{{lang.url-fragment}}net/system-requirements/)と[Linux、macOS、Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/)を参照してください。
<br><br>

**Q: 評価版にはどのような制限がありますか?**

**A:** ライセンスがない場合、Aspose.TeX は評価モードで動作します。出力されるのはドキュメントの最大 4 ページで、各ページに評価版の透かしが入ります。評価版は同じパッケージです。制限なしで評価するには、[30 日間の一時ライセンス](https://purchase.aspose.com/temporary-license/)をリクエストしてください。[ライセンス](/tex/{{lang.url-fragment}}net/licensing/)を参照してください。
<br><br>

**Q: コードでライセンスを適用するにはどうすればよいですか?**

**A:** 最初の変換の前に、ライセンスを 1 回だけ適用します。

```csharp
Aspose.TeX.License license = new Aspose.TeX.License();
license.SetLicense(@"C:\License\Aspose.TeX.lic");
```

ライセンスはストリームから読み込むこともでき、従量制 (metered) ライセンスを使用することもできます。[ライセンス](/tex/{{lang.url-fragment}}net/licensing/)を参照してください。価格については、[Aspose.TeX の価格ページ](https://purchase.aspose.com/pricing/tex/)を参照してください。
<br><br>

**Q: API ドキュメント、サンプル、サポートはどこで入手できますか?**

**A:**

- [開発者ガイド](https://docs.aspose.com/tex/net/)
- [API リファレンス](https://reference.aspose.com/tex/net/)
- [コミュニティ フォーラム](https://forum.aspose.com/c/tex/)
<br><br>
