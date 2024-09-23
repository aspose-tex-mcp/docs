---
translation: true
template: /templates/_template-net.md
title: TeX Command Line Converter | Aspose.TeX CLI Tools
linktitle: Aspose.TeX Convert
weight: 80
url: /net/cli-tools/tex-convert/
description: Powerful Command-Line Converter tool from Aspose.TeX to convert TeX/LaTeX documents easily and efficiently. Aspose CLI TeX converter.
keywords: tex to pdf cli converter, latex to pdf cli converter, cli tex converter
lastmod: "2024-09-20"
---

{{<section overview>}}

## Overview

The [Aspose.TeX Convert](https://www.nuget.org/packages/Aspose.TeX.Convert) tool is a powerful CLI application that facilitates the conversion of TeX and LaTeX documents into various formats. This tool lets developers and designers create documents that work seamlessly across different platforms and devices.

## Key Features

- **Supported Input Formats**: TeX, LaTeX.
- **Supported Output Formats**: PDF, XPS, PNG, JPEG, BMP, TIFF, SVG.
- **Flexible Usage**: Can be used both via simple command-line commands and programmatically in your C# code, compatible with .NET 6.0/7.0.

## Benefits

Using the Aspose.TeX Convert tool provides several advantages:

- **Efficiency**: Quickly convert TeX/LaTeX documents to multiple formats without the need for complex software.
- **Automation**: Integrate document conversion into your automated workflows and scripts.
- **Flexibility**: Handle various document formats to ensure compatibility with different systems and applications.

## Licensing

While the Aspose.TeX Convert application itself is free to use, converting documents requires a valid Aspose.TeX [license](/tex/{{lang.url-fragment}}net/licensing/). You can purchase a license or use Aspose.TeX in trial mode for evaluation purposes.

## How to install TeX Command-Line Converter?

The Aspose.TeX Convert tool can be installed either globally or locally, depending on your project's needs. It is recommended to use the local installation for project-specific use to avoid version conflicts.

### Global Installation

To install Aspose.TeX Convert globally on your machine, use the following command:


```bash
dotnet tool install --global Aspose.TeX.Convert
```

Specify the `--version` option if you need a specific version of the tool.

### Local Installation

For local installation within a specific project, first, navigate to your project's root directory. Then, execute the following commands:


1. Create a tool-manifest if not already present:

   ```bash
   dotnet new tool-manifest
   ```

2. Install Aspose.TeX Convert locally:

   ```bash
   dotnet tool install Aspose.TeX.Convert --local
   ```

Again, you can specify the `--version` option for a specific version.

### Updating the TeX CLI Converter

To update the Aspose.TeX Convert tool to the latest version, use the `dotnet tool update` command with either `--global` or `--local`, matching your installation type.

### Uninstalling the TeX CLI Converter

If you need to uninstall the tool, use the `dotnet tool uninstall` command with either `--global` or `--local`, depending on how the tool was installed.

## Usage

### Command Line

Convert your documents using command-line arguments. Here are the available parameters:


- `-i, --input [Required]`: Path to the input TeX or LaTeX document.
  - Example: `--input input.tex`
- `-o, --output [Required]`: Path for the converted document.
  - Example: `--output output.pdf`
- `-f, --format [Optional]`: Output document format.
  - Supported formats: PDF, XPS, PNG, JPEG, BMP, TIFF, SVG.
  - Example: `--format pdf`
- `-l, --license [Optional]`: Path to the Aspose.TeX .NET license file.
  - Example: `--license path_to_license.lic`
- `-v, --verbose [Optional]`: Enable verbose output.
  - Example: `--verbose`

Example command-line usage:


```bash
Aspose.TeX.Convert --input input.tex --output output.pdf --format pdf
```

### How to integrate CLI LaTeX Converter into C# Projects?

The Aspose.TeX Convert application can also be integrated directly into your .NET projects using the command line, enabling programmatic access to TeX conversion capabilities within your C# code.

**Adding the LaTeX Command Line Converter to Your Project:**

To add the Aspose.TeX Convert tool to your Visual Studio project, go to your project's root directory, and execute the following command:


```bash
dotnet Aspose.TeX.Convert add
```

This command adds the Aspose.TeX Convert functionality directly into your project, allowing you to use the library's methods and properties through your code. This is particularly useful for developers looking to implement customized TeX conversion processes directly within their applications.

### Use from Code

Here is an example of using the Aspose.TeX CLI tools programmatically in your C# code:


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

For more information and usage examples, please visit the [Aspose.TeX for .NET documentation](/tex/{{lang.url-fragment}}net/).
