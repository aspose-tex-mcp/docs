---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: 從 ZIP 加載 TeX | .NET API 解決方案
url: /net/load-tex-from-zip/
description: ".NET API 解決方案與 TeX 一起工作。通過示例了解如何使用幾行 C# 代碼從 ZIP 加載 TeX 文件。"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: 從 ZIP 加載 TeX 源文件
h2: ".NET API 解決方案從 ZIP 存檔加載 TeX 文件"
---

{{<section overview>}}
---
p1: "TeX 被稱為排版語言。這意味著您不對文檔中的文本進行格式化，而是將純文本與命令一起輸入。作為輸出，您將獲得所需(指定)格式的格式化文件。要進一步了解 TeX 輸入和輸出，請學習文檔的 [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/)。"
p2: "眾所周知，TeX 的主要目的是幫助創建數學或技術文本寫作。但在進行任何操作之前，應首先加載文件。在這裡，您將找到代碼片段，解釋如何使用 ZIP 目錄從 ZIP 加載 TeX 源文件進行輸入和輸出、輸出到 PDF 設備、將終端輸出寫入控制台。"
p3: "要加載 .tex 文件，我們需要："
p4: "Aspose.TeX for .NET API 是一個功能豐富、功能強大且易於使用的 C# 平台文檔操作和轉換 API。"
p5: "打開 NuGet 包管理器，搜索 Aspose.TeX 並安裝。您也可以從包管理器控制台使用以下命令。"
---

{{<section feature1>}}
---
title: "從 ZIP 存檔 C# 加載 TeX 的步驟："
h3: "用於加載 TeX 的 C# 代碼"
item1: "打開 ZIP 存檔上的流以將其用作輸入工作目錄。"
item2: "打開 ZIP 存檔上的流以將其用作輸出工作目錄。"
item3: "使用 [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) 的 [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) 類。"
item4: "為輸入指定 ZIP 存檔工作目錄或/並指定存檔內的路徑。為此，請使用 [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) 類的構造函數。"
item5: "為輸出指定 ZIP 存檔工作目錄或/並指定存檔內的路徑。為此，請使用 [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) 類的構造函數。"
item6: "使用 [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/) 類將控制台指定為輸出終端。"
item7: "使用 [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/) 類定義保存選項。"
item8: "運行作業 [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) 方法 [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)。"
item9: 細化輸出。
---