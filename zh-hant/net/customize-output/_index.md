---
translation: true
template: /_templates/_customize-output-net.md
title: 創建自定義輸出 TeX | .NET API 解決方案
url: /net/customize-output/
description: ".NET API 解決方案與 TeX 一起工作。閱讀示例如何使用幾行 C# 代碼為 TeX 文件創建自定義輸出。"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: 自定義輸出
h2: ".NET API 解決方案來自定義 TeX 文件的輸出"
---

{{<section overview>}}
---
p1: "TeX 被稱為排版語言。這意味著您不對文檔中的文本進行格式化，而是將純文本與命令一起輸入。"
p2: "文檔的文章 [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) 告訴我們，TeX 文件可能不包含任何要排版的數據，而只包含控制序列.然而它通常包含這樣的數據，並且目標格式的文件具有排版文本。該文件還將與指定為輸入的文件具有相同的名稱，並且是主輸出文件。對於原始的 TeX，這是一個 DVI 格式的文件。我們將調用輸入和輸出文件的名稱，而不擴展作業名稱。"
p3: "在此頁面上，您將找到一個解釋創建自定義 TeX 格式文件的代碼示例，您可以在其中看到如何自定義 TeX 文件的輸出。要自定義 .tex 文件輸出，我們需要："
p4: "Aspose.TeX for .NET API 是一個功能豐富、功能強大且易於使用的 C# 平台文檔操作和轉換 API。"
p5: "打開 NuGet 包管理器，搜索 Aspose.TeX 並安裝。您也可以從包管理器控制台使用以下命令。"
---

{{<section feature1>}}
---
title: "自定義 TeX 輸出 C# 的步驟："
h3: "用於 TeX 輸出自定義的 C# 代碼"
item1: "借助 [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) 方法的 [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) 類，在 ObjectTeX 引擎擴展上創建無格式的 TeX 引擎選項。"
item2: "使用 [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) 類為輸入指定文件系統工作目錄。"
item3: "使用 [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) 類為輸出指定文件系統工作目錄。"
item4: "要創建新格式，請使用 [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/) 方法。"
item5: 細化輸出。
---