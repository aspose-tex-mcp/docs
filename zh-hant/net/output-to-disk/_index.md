---
translation: true
template: /_templates/_output-to-disk-net.md
title: 將 TeX 輸出寫入磁盤 | .NET API 解決方案
url: /net/output-to-disk/
description: ".NET API 解決方案與 TeX 一起工作。通過示例了解如何使用幾行 C# 代碼為 TeX 文件創建自定義輸出。"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: 將 TeX 輸出寫入磁盤
h2: "通過 C# .NET 將 TeX 文件轉換的結果保存為磁盤"
---

{{<section overview>}}
---
p1: "TeX 被稱為排版語言，這意味著您無需格式化文檔中的文本，而是輸入純文本和命令。從文檔的文章 [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) 中得知，TeX 作業在明確指定的 TeX 文件上運行。在那裡，您還可以找到有關 TeX 交互模式和與 TeX 輸入和輸出相關的原語的信息。"
p2: "TeX 的主要用途是幫助創建數學或技術文本寫作。但是，當文件已經創建並且您不希望對其進行任何進一步的操作時，您可能希望將其轉換為不同的、更流行的格式。"
p3: "在此頁面上，您將找到一個代碼示例，解釋使用文件系統目錄進行輸入和輸出、輸出到 XPS 設備、覆蓋作業名稱、將終端輸出寫入磁盤。簡而言之，它是一種將輸出寫入磁盤的轉換。要運行這樣的操作，我們需要："
p4: "Aspose.TeX for .NET API 是一個功能豐富、功能強大且易於使用的 C# 平台文檔操作和轉換 API。"
p5: "打開 NuGet 包管理器，搜索 Aspose.TeX 並安裝。您也可以從包管理器控制台使用以下命令。"
---

{{<section feature1>}}
---
title: "將終端輸出寫入磁盤 C# 的步驟："
h3: "用於轉換 TeX 並將輸出寫入磁盤的 C# 代碼"
item1: "使用 [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) 的 [*TeXOptions*](https://) 方法在 ObjectTeX 引擎擴展上創建轉換選項參考.aspose.com/tex/net/aspose.tex/texoptions/) 類。"
item2: "如果您不希望將 TeXJob 構造函數的第一個參數作為作業名稱，請指定作業名稱。"
item3: "為輸入指定文件系統工作目錄。為此使用 [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) 類。"
item4: "借助 [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) 類的實體為輸出指定文件系統工作目錄。"
item5: "指定必須將終端輸出寫入輸出工作目錄中的文件。"
item6: "運行作業 [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) 方法 [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)。"
---