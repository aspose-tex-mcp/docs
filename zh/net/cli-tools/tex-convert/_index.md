---
translation: true
template: /templates/_template-net.md
title: TeX 命令行转换器 | Aspose.TeX CLI 工具
linktitle: Aspose.TeX 转换
weight: 80
url: /net/cli-tools/tex-convert/
description: 强大的 Aspose.TeX 命令行转换工具，可轻松高效地将 TeX/LaTeX 文档转换为多种格式。Aspose CLI TeX 转换器。
keywords: tex to pdf cli converter, latex to pdf cli converter, cli tex converter
lastmod: "2026-02-27"
---

{{<section overview>}}

## Overview

[Aspose.TeX Convert](https://www.nuget.org/packages/Aspose.TeX.Convert) 工具是一款功能强大的 CLI 应用程序，可帮助将 TeX 和 LaTeX 文档转换为多种格式。该工具让开发者和设计师能够创建在不同平台和设备上无缝工作的文档。

## Key Features

- **Supported Input Formats**: TeX, LaTeX.
- **Supported Output Formats**: PDF, XPS, PNG, JPEG, BMP, TIFF, SVG.
- **Flexible Usage**: 可通过简单的命令行指令使用，也可在 C# 代码中以编程方式调用，兼容 .NET 6.0/7.0。

## Benefits

使用 Aspose.TeX Convert 工具可获得以下优势：

- **Efficiency**: 快速将 TeX/LaTeX 文档转换为多种格式，无需复杂的软件。
- **Automation**: 将文档转换集成到自动化工作流和脚本中。
- **Flexibility**: 处理各种文档格式，确保与不同系统和应用程序的兼容性。

## Licensing

虽然 Aspose.TeX Convert 应用本身免费使用，但转换文档需要有效的 Aspose.TeX [许可证](/tex/{{lang.url-fragment}}net/licensing/)。您可以购买许可证或在试用模式下评估 Aspose.TeX。

## How to install TeX Command-Line Converter?

Aspose.TeX Convert 工具可以全局或本地安装，取决于您的项目需求。建议使用本地安装以避免版本冲突，适用于项目特定使用。

### Global Installation

在机器上全局安装 Aspose.TeX Convert，请使用以下命令：

```bash
dotnet tool install --global Aspose.TeX.Convert
```

如果需要特定版本，可添加 `--version` 参数。

### Local Installation

在特定项目内部进行本地安装，首先导航到项目根目录，然后执行以下命令：

1. 若尚未存在 tool‑manifest，创建它：

   ```bash
   dotnet new tool-manifest
   ```

2. 本地安装 Aspose.TeX Convert：

   ```bash
   dotnet tool install Aspose.TeX.Convert --local
   ```

同样，您可以使用 `--version` 参数指定特定版本。

### Updating the TeX CLI Converter

要将 Aspose.TeX Convert 工具更新到最新版本，请使用 `dotnet tool update` 命令，并根据您的安装类型添加 `--global` 或 `--local`。

### Uninstalling the TeX CLI Converter

如果需要卸载该工具，请使用 `dotnet tool uninstall` 命令，同样根据安装方式添加 `--global` 或 `--local`。

## Usage

### Command Line

通过命令行参数转换文档。以下是可用参数：

- `-i, --input [Required]`: 输入 TeX 或 LaTeX 文档的路径。  
  示例：`--input input.tex`
- `-o, --output [Required]`: 转换后文档的保存路径。  
  示例：`--output output.pdf`
- `-f, --format [Optional]`: 输出文档格式。  
  支持的格式：PDF, XPS, PNG, JPEG, BMP, TIFF, SVG。  
  示例：`--format pdf`
- `-l, --license [Optional]`: Aspose.TeX .NET 许可证文件的路径。  
  示例：`--license path_to_license.lic`
- `-v, --verbose [Optional]`: 启用详细输出。  
  示例：`--verbose`

示例命令行用法：

```bash
Aspose.TeX.Convert --input input.tex --output output.pdf --format pdf
```

### How to integrate CLI LaTeX Converter into C# Projects?

Aspose.TeX Convert 应用还可以直接集成到 .NET 项目中，通过命令行实现对 TeX 转换功能的编程访问。

**Adding the LaTeX Command Line Converter to Your Project:**

将 Aspose.TeX Convert 工具添加到 Visual Studio 项目中，进入项目根目录并执行以下命令：

```bash
dotnet Aspose.TeX.Convert add
```

此命令将在项目中直接加入 Aspose.TeX Convert 功能，使您能够在代码中使用库的方法和属性，这对需要在应用程序内部实现自定义 TeX 转换流程的开发者特别有用。

### Use from Code

下面示例展示了如何在 C# 代码中以编程方式使用 Aspose.TeX CLI 工具：

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

有关详细信息和使用示例，请访问 [Aspose.TeX for .NET 文档](/tex/{{lang.url-fragment}}net/).
