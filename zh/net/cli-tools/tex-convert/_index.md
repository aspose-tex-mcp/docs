---
translation: true
template: /templates/_template-net.md
title: Tex命令线转换器| Aspose.TeX CLI工具
linktitle: Aspose.TeX转换
weight: 80
url: /net/cli-tools/tex-convert/
description: 功能强大的命令行转换器工具从Aspose.TeX来轻松有效地转换Tex/latex文档。 Aspose CLI TEX转换器。
keywords: TEX到PDF CLI转换器，乳胶到PDF CLI转换器，CLI Tex Converter
lastmod: "2025-06-10"
---

{{<section overview>}}

## 概述

[Aspose.TeX转换](https://www.nuget.org/packages/Aspose.TeX.Convert)工具是一个强大的CLI应用程序，可促进Tex和乳胶文档转换为各种格式。该工具使开发人员和设计人员可以创建文档，这些文档可以在不同的平台和设备上无缝运行。

## 关键功能

- **支持的输入格式**：Tex，乳胶。
- **支持的输出格式**：PDF，XPS，PNG，JPEG，BMP，TIFF，SVG。
- **灵活的用法**：可以通过简单的命令行命令和C＃代码中的编程方式使用，与.NET 6.0/7.0兼容。

## 好处

使用aspose.tex转换工具提供了几个优点：

- **效率**：快速将TEX/乳胶文档转换为多种格式，而无需复杂的软件。
- **自动化**：将文档转换集成到您的自动化工作流和脚本中。
- **灵活性**：处理各种文档格式，以确保与不同的系统和应用程序的兼容性。

## 许可

虽然aspose.tex转换应用程序本身可以免费使用，但转换文档需要有效的aspose.tex [许可](/tex/{{lang.url-fragment}}net/licensing/)。您可以在试用模式下购买许可证或使用aspose.tex进行评估。

## 如何安装TEX命令行转换器？

aspose.tex转换工具可以在全球或本地安装，具体取决于您的项目需求。建议使用本地安装进行特定于项目的使用，以避免版本冲突。

### 全局安装

要安装Aspose.TeX在计算机上全球转换，请使用以下命令：


```bash
dotnet tool install --global Aspose.TeX.Convert
```

如果您需要该工具的特定版本，则指定“  -  Vers”选项。

### 本地安装

对于特定项目中的本地安装，首先，导航到项目的根目录。然后，执行以下命令：


1. 如果尚未存在的话，请创建一个工具字符：

   ```bash
   dotnet new tool-manifest
   ```

2. 安装aspose.tex在本地转换：

   ```bash
   dotnet tool install Aspose.TeX.Convert --local
   ```

同样，您可以为特定版本指定`–version'选项。

### 更新Tex CLI转换器

要将Aspose.TeX转换工具更新为最新版本，请使用`dotnet tool Update`命令与``global`或````''''命令，与您的安装类型匹配。

### 卸载Tex CLI转换器

如果需要卸载该工具，请使用带有`--global`或`--local`的`dotnet tool uninstall`命令，具体取决于该工具的安装方式。

## 用法

### 命令行

使用命令行参数转换您的文档。这是可用参数：


- `-i， - 输入[必需]`：输入Tex或乳胶文档的路径。
  - Example: `--input input.tex`
- `-o， - 输出[必需]：转换后的文档的路径。
  - Example: `--output output.pdf`
- `-f， -  format [可选]`：输出文档格式。
  - Supported formats: PDF, XPS, PNG, JPEG, BMP, TIFF, SVG.
  - Example: `--format pdf`
- `-l， -  license [可选]`：aspose.tex .net许可证文件的路径。
  - Example: `--license path_to_license.lic`
- `-v， -  verbose [可选]`：启用详细输出。
  - Example: `--verbose`

示例命令行的用法：


```bash
Aspose.TeX.Convert --input input.tex --output output.pdf --format pdf
```

### 如何将CLI乳胶转换器集成到C＃项目中？

Aspose.TeX转换应用程序还可以使用命令行直接集成到您的.NET项目中，从而使C＃代码中的Tex转换功能可以进行程序化访问。

**将乳胶命令行转换器添加到您的项目：**

要将Aspose.TeX转换工具添加到您的Visual Studio项目中，请转到您项目的根目录，然后执行以下命令：

```bash
dotnet Aspose.TeX.Convert add
```

此命令将Aspose.TeX直接添加到项目中，使您可以通过代码使用库的方法和属性。这对于希望直接在其应用程序中实施自定义的TEX转换过程的开发人员特别有用。

### 使用代码

这是在C＃代码中以编程方式使用Aspose.TeX CLI工具的示例：


```csharp
using Aspose.TeX.MicroApps.Convert;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        // Initialize convert options
        var options = new ConvertOptions
        {
            // Required: Specify the input document path
            InputDocument = "input.tex",
            
            // Required: Specify the output document path
            OutputFilePath = "output.pdf",
            
            // Optional: Specify the output format
            ToFormat = "pdf"
        };

        // Conditional: Apply license if you have one
        if (isLicensed)
        {
            options.LicenseFile = "path_to_license.lic";
        }

        // Execute the conversion task
        await ConvertTasks.Create(options).Execute();
    }
}
```

有关更多信息和用法示例，请访问[Aspose.TeX for .NET文档](/tex/{{lang.url-fragment}}net/)。