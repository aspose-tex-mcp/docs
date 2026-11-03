---
translation: true
template: /templates/_template-net.md
title: Linux、macOS 和 Docker | .NET的Aspose.TeX
linktitle: Linux、macOS 和 Docker
weight: 55
url: /net/linux-and-containers/
description: 使用 Aspose.TeX.Drawing 包在 Linux、macOS 和 Docker 容器中运行 Aspose.TeX for .NET。包的选择、从 Aspose.TeX 迁移、Dockerfile 和已知限制。
keywords: aspose.tex linux, aspose.tex docker, aspose.tex macos, aspose.tex.drawing, latex 转 pdf linux .NET, latex 转 png docker .NET, System.Drawing.Common is not supported on this platform
lastmod: "2026-11-02"
---

{{<section overview>}}

## 选择合适的包 {#choose-the-right-package}

Aspose.TeX for .NET 以两个 NuGet 包的形式发布，二者的 API 和版本号相同：

| 包 | 图形后端 | Windows | Linux、macOS | 目标框架 |
|---|---|---|---|---|
| [`Aspose.TeX`](https://www.nuget.org/packages/Aspose.TeX) | `System.Drawing.Common` (GDI+) | 是 | 否 | .NET Framework 4.0、.NET Standard 2.0、.NET 6.0、.NET 7.0 |
| **[`Aspose.TeX.Drawing`](https://www.nuget.org/packages/Aspose.TeX.Drawing)** | Aspose.Drawing（托管，内置于包中） | **是** | **是** | .NET Standard 2.0、.NET 7.0 |

从 .NET 6 开始，Microsoft 仅在 Windows 上支持 `System.Drawing.Common`。如果应用程序在 Linux 或 macOS 上使用 `Aspose.TeX` 包，一旦进行渲染就会失败：

```
System.PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.
```

当应用程序在 Linux、macOS、Docker 容器或其他非 Windows 环境中运行时，请使用 `Aspose.TeX.Drawing`。该包同样可以在 Windows 上运行，因此如果为多个平台构建同一个应用程序，可以在所有平台上使用它。

`Aspose.TeX.Drawing` 不依赖 `System.Drawing.Common` 或 `libgdiplus`。图形后端 Aspose.Drawing 嵌入在 `Aspose.TeX.dll` 中，因此该包只向应用程序添加一个程序集。.NET 7.0 版本供 .NET 7、8、9、10 及更高版本使用；.NET Standard 2.0 版本供 .NET Framework 4.7.2 及更高版本使用。

## 安装包 {#install-the-package}

在项目文件夹中运行以下命令之一：

```bash
dotnet add package Aspose.TeX.Drawing
```

```powershell
Install-Package Aspose.TeX.Drawing
```

有关引用该包的其他方式，请参阅[安装](/tex/{{lang.url-fragment}}net/installation/)。

{{% alert color="primary" %}}
两个包中只能引用一个。如果项目同时引用 `Aspose.TeX` 和 `Aspose.TeX.Drawing`，构建时不会出现警告，但输出文件夹中只会复制一个 `Aspose.TeX.dll`，应用程序会在运行时失败，例如出现 `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.SizeF' from assembly 'Aspose.TeX'`。切换到 `Aspose.TeX.Drawing` 时，请先删除 `Aspose.TeX` 包：

```bash
dotnet remove package Aspose.TeX
dotnet add package Aspose.TeX.Drawing
```
{{% /alert %}}

## 从 Aspose.TeX 切换到 Aspose.TeX.Drawing {#switch-from-asposetex-to-asposetexdrawing}

两个包中的命名空间、类和成员相同，因此替换包之后，大部分代码无需修改。

### 颜色和尺寸 {#colors-and-sizes}

渲染选项和结果会用到颜色和尺寸，例如 `MathRendererOptions.TextColor`、`FigureRendererOptions.BackgroundColor` 以及 `MathRenderer.Render` 的返回值。在 `Aspose.TeX.Drawing` 中，这些成员的类型为 `Aspose.TeX.Drawing.Color` 和 `Aspose.TeX.Drawing.SizeF`。这两种类型都可以与 `System.Drawing.Color` 和 `System.Drawing.SizeF` 相互隐式转换。后者是无需 `System.Drawing.Common` 即可在所有平台上使用的标准 .NET 类型，因此下面这样的代码在两个包中都能编译和运行：

```csharp
using System.Drawing;
using System.IO;
using Aspose.TeX.Features;

PngMathRendererOptions options = new PngMathRendererOptions
{
    Resolution = 150,
    TextColor = Color.Black,
    BackgroundColor = Color.White
};

using (Stream stream = File.Create("formula.png"))
{
    SizeF size = new PngMathRenderer().Render(@"$$E = mc^2$$", stream, options);
}
```

### 平滑模式和插值模式 {#smoothing-and-interpolation-modes}

唯一的变化涉及图像保存选项（`PngSaveOptions`、`JpegSaveOptions`、`BmpSaveOptions`、`TiffSaveOptions`）的 `SmoothingMode` 和 `InterpolationMode` 属性。在 `Aspose.TeX` 包中，它们使用 `System.Drawing.Drawing2D` 命名空间中的枚举，该命名空间属于 `System.Drawing.Common`（编译器会通过警告 CA1416 将它们报告为仅限 Windows）。在 `Aspose.TeX.Drawing` 中，它们使用成员相同的 `Aspose.TeX.Drawing.SmoothingMode` 和 `Aspose.TeX.Drawing.InterpolationMode` 枚举。替换 `using` 指令，其余代码保持不变。

使用 `Aspose.TeX` 时：

```csharp
using System.Drawing.Drawing2D;
using Aspose.TeX.Presentation.Image;

PngSaveOptions saveOptions = new PngSaveOptions
{
    Resolution = 300,
    SmoothingMode = SmoothingMode.AntiAlias,
    InterpolationMode = InterpolationMode.HighQualityBicubic
};
```

使用 `Aspose.TeX.Drawing` 时：

```csharp
using Aspose.TeX.Presentation.Image;
using SmoothingMode = Aspose.TeX.Drawing.SmoothingMode;
using InterpolationMode = Aspose.TeX.Drawing.InterpolationMode;

PngSaveOptions saveOptions = new PngSaveOptions
{
    Resolution = 300,
    SmoothingMode = SmoothingMode.AntiAlias,
    InterpolationMode = InterpolationMode.HighQualityBicubic
};
```

请像上面那样使用别名导入这两个类型，而不要使用 `using Aspose.TeX.Drawing;`。`Aspose.TeX.Drawing` 命名空间还包含 `Color` 和 `SizeF`，因此将它与 `System.Drawing` 一起导入会导致编译错误 `CS0104: 'Color' is an ambiguous reference`。

### Aspose.TeX.Drawing 命名空间中的类型 {#types-of-the-asposetexdrawing-namespace}

`Aspose.TeX.Drawing` 命名空间仅存在于 `Aspose.TeX.Drawing` 包中：

| 类型 | 使用位置 | 与 System.Drawing 的兼容性 |
|---|---|---|
| `Color` | `MathRendererOptions.TextColor`、`FigureRendererOptions.BackgroundColor` | 与 `System.Drawing.Color` 相互隐式转换 |
| `SizeF` | `MathRenderer.Render` 和 `FigureRenderer.Render` 的返回值；`MathRendererPluginResult` 和 `FigureRendererPluginResult` 的 `Size` | 与 `System.Drawing.SizeF` 相互隐式转换 |
| `SmoothingMode` | `ImageSaveOptions.SmoothingMode` | 成员和值与 `System.Drawing.Drawing2D.SmoothingMode` 相同 |
| `InterpolationMode` | `ImageSaveOptions.InterpolationMode` | 成员和值与 `System.Drawing.Drawing2D.InterpolationMode` 相同 |

## 在 Docker 中运行 {#run-in-docker}

Aspose.TeX 使用自身内置的 TeX 字体排版文档，`Aspose.TeX.Drawing` 则包含自己的图形后端。容器中不需要 `libgdiplus`、`fontconfig`，也不需要安装字体。唯一相关的系统组件是 ICU，XPS 和 SVG 输出需要它（请参阅[全球化固定模式](#globalization-invariant-mode)）。

基于 Debian 和 Ubuntu 的官方 .NET 映像无需额外设置即可使用：

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /src
COPY . .
RUN dotnet publish -c Release -o /app

FROM mcr.microsoft.com/dotnet/runtime:8.0
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "MyApp.dll"]
```

请将 `MyApp.dll` 替换为应用程序的名称。对于 ASP.NET Core 应用程序，请使用 `mcr.microsoft.com/dotnet/aspnet` 代替 `mcr.microsoft.com/dotnet/runtime`；规则相同。

下表列出了每种映像需要的设置：

| 基础映像 | 额外设置 |
|---|---|
| `runtime:8.0`、`aspnet:8.0` (Debian) | 无 |
| `runtime:8.0-noble`、`aspnet:8.0-noble` (Ubuntu) | 无 |
| `runtime:8.0-alpine`、`aspnet:8.0-alpine` | 安装 ICU 并关闭固定模式（见下文） |
| `runtime:8.0-noble-chiseled`、`aspnet:8.0-noble-chiseled` | 使用包含 ICU 的 `-noble-chiseled-extra` 变体 |
| `runtime:8.0-noble-chiseled-extra`、`aspnet:8.0-noble-chiseled-extra` | 无 |

.NET 9 和 .NET 10 的映像同样适用。支持 `linux/amd64` 和 `linux/arm64` 映像。

### Alpine {#alpine}

Alpine 映像以全球化固定模式运行 .NET，并且不包含 ICU。请安装 `icu-libs` 包并关闭固定模式：

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /src
COPY . .
RUN dotnet publish -c Release -o /app

FROM mcr.microsoft.com/dotnet/runtime:8.0-alpine
RUN apk add --no-cache icu-libs
ENV DOTNET_SYSTEM_GLOBALIZATION_INVARIANT=false
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "MyApp.dll"]
```

### Chiseled (distroless) 映像 {#chiseled-distroless-images}

Chiseled 映像不包含 shell 和包管理器，因此无法在其中安装 ICU。请使用已包含 ICU 的 `-chiseled-extra` 变体：

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /src
COPY . .
RUN dotnet publish -c Release -o /app

FROM mcr.microsoft.com/dotnet/runtime:8.0-noble-chiseled-extra
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "MyApp.dll"]
```

Chiseled 映像以非 root 用户身份运行应用程序。请将输出文件写入可写位置，例如已挂载的卷或 `/tmp`，而不是应用程序文件夹。

## 全球化固定模式 {#globalization-invariant-mode}

XPS 和 SVG 输出需要 ICU。如果 .NET 在[全球化固定模式](https://aka.ms/GlobalizationInvariantMode)下运行，转换为 XPS 或 SVG 时会因如下异常而失败：

```
System.Globalization.CultureNotFoundException: Only the invariant culture is supported in globalization-invariant mode. See https://aka.ms/GlobalizationInvariantMode for more information. (Parameter 'name')
en-US is an invalid culture identifier.
```

固定模式在 Alpine 和 chiseled 映像中默认开启，项目属性 `<InvariantGlobalization>true</InvariantGlobalization>` 也会将其开启。PDF、PNG、JPEG、BMP 和 TIFF 输出在固定模式下可以正常工作。如果需要 XPS 或 SVG 输出，请按照[在 Docker 中运行](#run-in-docker)中的说明安装 ICU，并且不要在项目中开启固定模式。

## 许可 {#licensing}

`Aspose.TeX.Drawing` 使用与 `Aspose.TeX` 相同的许可证，应用方式也相同（请参阅[许可](/tex/{{lang.url-fragment}}net/licensing/)）。该许可证同样涵盖内置的图形后端 Aspose.Drawing；不需要单独的 Aspose.Drawing 许可证。

在评估模式下，`Aspose.TeX.Drawing` 的光栅输出（PNG、JPEG、BMP、TIFF）带有两个水印：Aspose.TeX 评估水印和“Evaluation only Aspose.Drawing”水印。应用 Aspose.TeX 许可证后，两者都会消失。

## 已知限制 {#known-limitations}

`Aspose.TeX.Drawing` 目前还无法保存多页 TIFF 文件。如果将 `TiffSaveOptions.Multipage` 设置为 `true`，生成的 TIFF 文件只包含文档的第一页，并且不会引发异常。要获取所有页面，请将 `Multipage` 设置为 `false`，为每一页获取单独的 TIFF 图像，或将文档转换为 PDF 或 XPS。

## 故障排除 {#troubleshooting}

| 错误 | 原因 | 解决方法 |
|---|---|---|
| `PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.` | 应用程序在 Linux 或 macOS 上使用 `Aspose.TeX` 包。 | 使用 `Aspose.TeX.Drawing` 包。 |
| `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.…' from assembly 'Aspose.TeX'` | 项目同时引用了 `Aspose.TeX` 和 `Aspose.TeX.Drawing`。 | 删除 `Aspose.TeX` 包。 |
| 保存为 XPS 或 SVG 时出现 `CultureNotFoundException: … en-US is an invalid culture identifier.` | .NET 在全球化固定模式下运行。 | 安装 ICU 并关闭固定模式，请参阅[全球化固定模式](#globalization-invariant-mode)。 |
| `error CS0104: 'Color' is an ambiguous reference between 'System.Drawing.Color' and 'Aspose.TeX.Drawing.Color'` | 代码同时导入了 `System.Drawing` 和 `Aspose.TeX.Drawing`。 | 使用别名导入 `Aspose.TeX.Drawing` 的类型，请参阅[平滑模式和插值模式](#smoothing-and-interpolation-modes)。 |
| 多页 TIFF 文件只包含一页。 | `Aspose.TeX.Drawing` 的已知限制。 | 请参阅[已知限制](#known-limitations)。 |

## 在 Linux 和容器中部署的检查清单 {#checklist-for-linux-and-container-deployment}

- [ ] 引用 `Aspose.TeX.Drawing` 而不是 `Aspose.TeX`，并且两个包中只引用一个。
- [ ] 如果代码同时导入 `System.Drawing` 和 `Aspose.TeX.Drawing`，请使用别名导入 `Aspose.TeX.Drawing` 的类型。
- [ ] 如果需要 XPS 或 SVG 输出，请确保 ICU 可用且固定模式已关闭：在 Alpine 中安装 `icu-libs`，对 chiseled 映像使用 `-chiseled-extra` 变体，并且不要在项目中设置 `InvariantGlobalization`。
- [ ] 将输出文件写入可写位置，尤其是在以非 root 用户运行应用程序的 chiseled 映像中。
- [ ] 在应用程序启动时、首次转换之前应用一次许可证。
- [ ] 如果需要 TIFF 格式的所有页面，请将 `TiffSaveOptions.Multipage` 设置为 `false`，或使用 PDF 或 XPS 输出。
