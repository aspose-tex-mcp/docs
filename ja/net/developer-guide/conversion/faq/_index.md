---
translation: true
template: /templates/_template-net.md
title: .NET 用 Aspose.TeX コンバータ – FAQ
linktitle: よくある質問
type: docs
weight: 90
url: /net/conversion/faq/
description: Aspose.TeX for .NET に関するよくある質問には、サポートされている形式、変換例、ライセンス、バッチ処理、画像オプションなどが含まれています。
keywords: Aspose.TeX、.NET、FAQ、LaTeX 変換、PDF、Word、HTML、画像エクスポート、ライセンス、バッチ変換、API、ドキュメント
lastmod: "2025-12-04"
---

{{<section overview>}}

<br><br>

**Q: Aspose.TeX for .NET はどのようなソース形式と出力形式をサポートしていますか?**  

**A:** Aspose.TeX は、LaTeX ソース ファイル (`*.tex`)、プレーンテキストの LaTeX スニペット、およびインライン数学 (`$$…$$`、`\(...\)`、`\[…\]`) を読み取ることができます。 PDF、XPS、SVG、PNG、JPEG、BMP、TIFF、DOCX、ODT、HTML‑5 (CSS 付き)、および EPUB (PDF→EPUB 経由) に出力できます。  
<br><br>

**Q: C# で `.tex` ファイルを PDF に変換するにはどうすればよいですか?**  

**A:** 
```csharp
using Aspose.TeX;

// Load LaTeX source
var tex = new TexDocument(@"C:\Input\sample.tex");

// Convert to PDF
using (var pdf = tex.ToPdf())
{
    pdf.Save(@"C:\Output\sample.pdf");
}
```  
<br><br>

**Q: LaTeX を Word (DOC/DOCX) または HTML に直接変換できますか?**  

**A:** はい。 DOC/DOCX には `TexDocument.ToWord()` を使用し、クリーンな HTML‑5 出力には `TexDocument.ToHtml()` を使用します (スタイルはデフォルトでインライン展開されます)。  
<br><br>

**Q: 数式は正確に表示されますか?**  

**A:** 組み込みの LaTeX 数学パーサーは、方程式を PDF/SVG の高品質ベクトル グラフィックスとして、または PNG/JPEG のアンチエイリアス ビットマップとしてレンダリングします。 「align」、「eqnarray」、「amsmath」、「tikz」などの複雑な環境に対して完全なサポートが提供されます。  
<br><br>

**Q: サーバー上に LaTeX インストール (MiKTeX など) が必要ですか?**  

**A:** いいえ。Aspose.TeX は完全にスタンドアロンの .NET ライブラリであり、外部の TeX ディストリビューションを必要としません。  
<br><br>

**Q: 実行時の要件は何ですか?**  

**A:** 

• .NET Framework4.6 以降 **または** .NETCore2.1+/.NET5+。  
• Windowsx64/x86、Linux (glibc2.12+)、macOS (Catalyst)。  
• 追加のネイティブ バイナリは必要ありません。  
<br><br>

**Q: 画像出力の解像度と品質を制御するにはどうすればよいですか?**  

**A:** 
```ccsharp
var opts = new ImageSaveOptions
{
    Resolution = 300,   // DPI
    Quality = 95        // JPEG quality (0‑100)
};
var img = tex.ToPng(opts);
img.Save(@"C:\Output\sample.png");
```  
<br><br>

**Q: 無料の試用版または評価版はありますか?**  

**A:** 30 日間の評価 DLL は、Aspose Web サイトから入手できます。これには完全な機能セットが含まれていますが、各変換は入力の 500 KB に制限されます。試用版ビルドにはライセンス キーは必要ありません。  
<br><br>

**Q: ライセンスはコード内でどのように処理されますか?**  

**A:** 
```csharp
Aspose.TeX.License license = new Aspose.TeX.License();
license.SetLicense(@"C:\License\Aspose.TeX.lic");
```  
<br><br>

**Q: バッチ変換 (複数の `.tex` ファイル) を効率的に実行できますか?** 

**A:** はい。ファイルごとに `TexDocument` を作成するか、複数のフラグメントに対して単一のインスタンスを再利用します。このライブラリは読み取り専用操作に対してスレッドセーフであるため、`Parallel.ForEach` を使用して作業を並列化できます。  
<br><br>

**Q: カスタム パッケージまたはユーザー定義マクロのサポートは受けられますか?**  

**A:** コア サポートには、`amsmath`、`amssymb`、`graphicx`、`hyperref`、`tikz` などの一般的なパッケージが含まれています。サポートされていないパッケージについては、LaTeX を自分で前処理するか、`ExternalPackageResolver` API を使用して実行時にカスタム `.sty` ファイルをロードすることができます。  
<br><br>

**Q: 生成された PDF に透かしやページ番号を追加するにはどうすればよいですか?**  

**A:** 変換後、結果を `Aspose.Pdf.PdfDocument` として扱うことができます。例:  
```csharp
var pdf = tex.ToPdf();
pdf.AddWatermarkText("Confidential");
pdf.AddPageNumbers();
pdf.Save(@"C:\Output\sample.pdf");
```  
2 つの Aspose ライブラリは同じ名前空間階層を共有するため、相互運用性がシームレスになります。  
<br><br>

**Q: 料金モデルは何ですか?**  

**A:** 

• 小規模ビジネス開発者: 年間 999 ドル (最大 5 人の開発者)。  
• 開発者 OEM: 年間 3499 ドルからの永久ライセンス (ソース コードを含む)。

ご要望に応じて、ボリューム ディスカウントとサイト ライセンスをご利用いただけます。  
<br><br>

**Q: 詳細な API ドキュメントとサンプルはどこで入手できますか?**  
<br>
**A:** 

• [公式ドキュメント](https://docs.aspose.com/tex/net/)
• [GitHub サンプル](https://github.com/aspose-tex/Aspose.TeX-net) 
• [コミュニティフォーラム](https://forum.aspose.com/c/tex/31)  
<br><br>