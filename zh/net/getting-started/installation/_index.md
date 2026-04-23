---
translation: true
template: /templates/_template-net.md
linktitle: 安装
title: 安装 | .NET的Aspose.TeX
weight: 60
url: /net/installation/
description: 通过单击“下载软件包”，可以在下载的ZIP软件包或从Nuget Gallery中找到.NET的Aspose.TeX API文档。
lastmod: "2026-04-22"
---

{{<section overview>}}

## 通过NuGet安装.net的aspose.tex

NuGet是一个免费的，开源开发人员的包装管理系统，用于.NET平台，目的是简化开发过程中将第三方库将其纳入.NET应用程序的过程。这是一个视觉工作室的扩展，它可以轻松添加，删除和更新使用.NET框架的Visual Studio项目中的库和工具。可以通过创建NuGet软件包并将其存储在NuGet存储库中，可以轻松地与其他开发人员共享库或工具。安装软件包时，NuGet将文件复制到解决方案中，并自动进行必要的更改，例如添加引用并更改您的app.config或web.config文件。如果您决定删除库，NuGet会删除文件并逆转对项目的任何更改，以免剩下混乱。

### 引用aspose.tex .net

利用这一出色的功能，我们将[Aspose.TeX for .NET]捆绑在一起(1)库中的NuGet软件包，然后将其上传到NuGet存储库中。使用此选项，您可以从不在系统上安装此组件的情况下使用aspose.tex。 NuGet在Visual Studio 2010和更高版本，Visual Web Developer 2010和Windows Phone Developer工具7.1中运行。在我们的测试中，我们使用Visual Studio 2015 Ultimate进行了测试。

开始：

1. 在Visual Studio中打开解决方案或项目。
2. 添加NuGet Package Manager作为视觉工作室扩展名：

    1. 选择“工具”菜单，然后选择“扩展管理器”。
    2. 选择“在线库”以获取在线可用软件包的完整列表。
    3. 选择“NuGet 包管理器”。
    4. 点击“下载”。
    5. 安装包管理器后，重新启动 Visual Studio 以使更改生效。

    安装 NuGet 包管理器后，您可以从“管理 NuGet 包”窗口，或使用专用于 Visual Studio 窗口的“包管理器控制台”中的 PowerShell 命令行命令来查找、安装、删除和更新软件包。选择“工具”后，然后选择“库包管理器”，即可找到这两个选项。

### 使用软件包管理器安装软件包

使用软件包管理器控制台引用组件：

1. 在Visual Studio中打开您的.NET应用程序。
2. 在**工具**菜单上，选择**库软件包管理器**，然后**软件包管理器控制台**。
3. 键入命令“Install-Package Aspose.TeX”以安装最新的完整版本，或键入命令“Install-Package Aspose.TeX -prerelease”，以安装包括热修复程序在内的最新版本。
4. 按**Enter**。

### 使用软件包管理器控制台更新软件包

如果您已经通过NuGet引用了组件，请按照以下步骤更新对最新版本的引用：

1. 在Visual Studio中打开您的.NET应用程序。
2. 从**工具**菜单中，选择**库软件包管理器**，然后是**软件包管理器**以打开软件包管理器控制台。
3. 键入命令“Update-Package Aspose.TeX”以引用最新的完整版本，或键入命令“Update-Package Aspose.TeX -prerelease”，以安装最新版本，包括热修复程序。
4. 按**Enter**。

### 使用包装管理器GUI安装软件包

请按照以下步骤使用软件包管理器GUI引用组件：

1. 在Visual Studio中打开您的.NET应用程序。
2. 从**工具**菜单中，从**解决方案**选择**库软件包管理器**和**管理NuGet软件包**选项。 

    您也可以从解决方案资源管理器中获取类似的选项：
    1. 右键单击​​项目名称。
    2. 选择“管理 NuGet 包”。

3. 从左菜单中选择**在线**。
4. 在搜索框中键入**Aspose.TeX**，以找到.net的aspose.tex。
5. 单击**安装/更新**在最新版本的Aspose.TeX for .NET旁边