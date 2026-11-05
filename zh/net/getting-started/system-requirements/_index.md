---
translation: true
template: /templates/_template-net.md
title: 系统要求| Aspose.TeX for .NET 入门
linktitle: 系统要求
weight: 50
url: /net/system-requirements/
description: NuGet 包 Aspose.TeX 和 Aspose.TeX.Drawing 支持的操作系统、.NET 版本和开发环境。
lastmod: "2026-11-02"
---

{{<section overview>}}

Aspose.TeX for .NET 以两个 API 相同的 NuGet 包提供。由于它们使用不同的图形后端，系统要求也有所不同。

| | `Aspose.TeX` | `Aspose.TeX.Drawing` |
|---|---|---|
| 图形后端 | `System.Drawing.Common` (GDI+) | Aspose.Drawing，内置于包中 |
| 操作系统 | Windows | Windows、Linux、macOS |
| 包的目标框架 | .NET Framework 4.0、.NET Standard 2.0、.NET 6.0、.NET 7.0 | .NET Standard 2.0、.NET 7.0 |

## 支持的操作系统

### Aspose.TeX

* Microsoft Windows 桌面版和服务器版 (x64、x86)
* Microsoft Azure（基于 Windows 的服务）

从 .NET 6 开始，Microsoft 仅在 Windows 上支持该包所依赖的 `System.Drawing.Common`。

### Aspose.TeX.Drawing

* Microsoft Windows 桌面版和服务器版 (x64、x86)
* Linux (x64、Arm64)，包括 Docker 容器
* macOS

不需要 `libgdiplus` 或 `fontconfig` 等本机库，也不需要安装字体。在 Linux 上，XPS 和 SVG 输出需要 ICU，而某些容器映像不包含 ICU。请参阅 [Linux、macOS 和 Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/)。

## 支持的 .NET 版本

### Aspose.TeX

* .NET Framework 4.0 或更高版本
* .NET 6 或更高版本
* .NET Standard 2.0 的任何其他实现，例如 .NET Core 2.0 或更高版本

### Aspose.TeX.Drawing

* .NET 7 或更高版本，包括 .NET 8、.NET 9 和 .NET 10
* .NET Framework 4.7.2 或更高版本（通过 .NET Standard 2.0）
* .NET Standard 2.0 的任何其他实现，例如 .NET Core 2.0 或更高版本

## 开发环境

Aspose.TeX for .NET 可以在任何面向 .NET 平台的开发环境中使用，例如 Microsoft Visual Studio、Visual Studio Code 或 JetBrains Rider，也可以与 .NET CLI 一起使用。
