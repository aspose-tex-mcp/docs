---
translation: true
template: /_templates/_customize-input-net.md
title: 創建自定義輸入 TeX | .NET API 解決方案 | Aspose
url: /net/customize-input/
description: ".NET API 解決方案與 TeX 一起工作。通過示例了解如何使用幾行 C# 代碼為 TeX 文件創建自定義輸入。"
keywords: 自定義輸入tex net api, C# api 自定義tex
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: 自定義輸入
h2: ".NET API 解決方案來自定義 TeX 文件的輸入"
---

{{<section overview>}}
---
p1: "TeX 被稱為排版語言。這意味著您不對文檔中的文本進行格式化，而是將純文本與命令一起輸入。正如文檔的文章 [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) 中所述，TeX 作業在明確指定的 TeX 文件上運行。因此，我們將這個文件包含在某個 TeX 作業的輸入中。"
p2: "在此頁面上，您將找到一個代碼示例，說明如何自定義 TeX 源文件的輸入，同時考慮到輸入應遵循 TeX 語法，並且理想情況下，僅包含引擎已知的命令。"
p3: "要自定義 .tex 文件輸入，我們需要："
p4: "Aspose.TeX for .NET API 是一個功能豐富、功能強大且易於使用的 C# 平台文檔操作和轉換 API。"
p5: "打開 NuGet 包管理器，搜索 Aspose.TeX 並安裝。您也可以從包管理器控制台使用以下命令。"
---

{{<section feature1>}}
---
title: "自定義 TeX 輸入 C# 的步驟："
h3: "用於 TeX 輸入自定義的 C# 代碼"
item1: "使用 [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) 的方法 [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) 類，在 ObjectTeX 引擎擴展上創建無格式的 TeX 引擎選項。"
item2: "使用 [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) 類，為輸入指定一個文件系統工作目錄。"
item3: "借助 [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) 方法，創建自定義格式。"
---