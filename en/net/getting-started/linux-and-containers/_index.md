---
translation: true
template: /templates/_template-net.md
title: Linux, macOS and Docker | Aspose.TeX for .NET
linktitle: Linux, macOS and Docker
weight: 55
url: /net/linux-and-containers/
description: Run Aspose.TeX for .NET on Linux, macOS and in Docker containers with the Aspose.TeX.Drawing package. Package choice, migration from Aspose.TeX, Dockerfiles and known limitations.
keywords: aspose.tex linux, aspose.tex docker, aspose.tex macos, aspose.tex.drawing, latex to pdf linux .NET, latex to png docker .NET, System.Drawing.Common is not supported on this platform
lastmod: "2026-11-02"
---

{{<section overview>}}

## Choose the right package

Aspose.TeX for .NET is published as two NuGet packages with the same API and the same version number:

| Package | Graphics backend | Windows | Linux, macOS | Target frameworks |
|---|---|---|---|---|
| [`Aspose.TeX`](https://www.nuget.org/packages/Aspose.TeX) | `System.Drawing.Common` (GDI+) | Yes | No | .NET Framework 4.0, .NET Standard 2.0, .NET 6.0, .NET 7.0 |
| **[`Aspose.TeX.Drawing`](https://www.nuget.org/packages/Aspose.TeX.Drawing)** | Aspose.Drawing (managed, built into the package) | **Yes** | **Yes** | .NET Standard 2.0, .NET 7.0 |

Starting with .NET 6, Microsoft supports `System.Drawing.Common` only on Windows. If your application uses the `Aspose.TeX` package on Linux or macOS, it fails as soon as it renders anything:

```
System.PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.
```

Use `Aspose.TeX.Drawing` when your application runs on Linux, macOS, in Docker containers or in other non-Windows environments. The package works on Windows too, so you can use it everywhere if you build one application for several platforms.

`Aspose.TeX.Drawing` does not depend on `System.Drawing.Common` or `libgdiplus`. The Aspose.Drawing graphics backend is embedded in `Aspose.TeX.dll`, so the package delivers a single assembly to your application. The .NET 7.0 build is used by .NET 7, 8, 9, 10 and later; the .NET Standard 2.0 build is used by .NET Framework 4.7.2 and later.

## Install the package

Run one of the following commands in the folder of your project:

```bash
dotnet add package Aspose.TeX.Drawing
```

```powershell
Install-Package Aspose.TeX.Drawing
```

See [Installation](/tex/{{lang.url-fragment}}net/installation/) for other ways to reference the package.

{{% alert color="primary" %}}
Reference only one of the two packages. If a project references both `Aspose.TeX` and `Aspose.TeX.Drawing`, it builds without warnings, but only one `Aspose.TeX.dll` is copied to the output folder, and the application fails at run time, for example with `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.SizeF' from assembly 'Aspose.TeX'`. When you switch to `Aspose.TeX.Drawing`, remove the `Aspose.TeX` package first:

```bash
dotnet remove package Aspose.TeX
dotnet add package Aspose.TeX.Drawing
```
{{% /alert %}}

## Switch from Aspose.TeX to Aspose.TeX.Drawing

Namespaces, classes and members are the same in both packages, so most code needs no changes after you replace the package.

### Colors and sizes

Rendering options and results use colors and sizes, for example `MathRendererOptions.TextColor`, `FigureRendererOptions.BackgroundColor` and the return value of `MathRenderer.Render`. In `Aspose.TeX.Drawing`, these members have the types `Aspose.TeX.Drawing.Color` and `Aspose.TeX.Drawing.SizeF`. Both types convert implicitly to and from `System.Drawing.Color` and `System.Drawing.SizeF`. These are standard .NET types available on every platform without `System.Drawing.Common`, so code like the following compiles and runs with either package:

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

### Smoothing and interpolation modes

The only change concerns the `SmoothingMode` and `InterpolationMode` properties of image save options (`PngSaveOptions`, `JpegSaveOptions`, `BmpSaveOptions`, `TiffSaveOptions`). In the `Aspose.TeX` package, they use enumerations from the `System.Drawing.Drawing2D` namespace, which belongs to `System.Drawing.Common` (the compiler reports them as Windows-only with warning CA1416). In `Aspose.TeX.Drawing`, they use the `Aspose.TeX.Drawing.SmoothingMode` and `Aspose.TeX.Drawing.InterpolationMode` enumerations, which have the same members. Replace the `using` directive and keep the rest of the code.

With `Aspose.TeX`:

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

With `Aspose.TeX.Drawing`:

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

Import these two types with aliases, as shown above, rather than with `using Aspose.TeX.Drawing;`. The `Aspose.TeX.Drawing` namespace also contains `Color` and `SizeF`, so importing it together with `System.Drawing` causes the compiler error `CS0104: 'Color' is an ambiguous reference`.

### Types of the Aspose.TeX.Drawing namespace

The `Aspose.TeX.Drawing` namespace exists only in the `Aspose.TeX.Drawing` package:

| Type | Used by | Compatibility with System.Drawing |
|---|---|---|
| `Color` | `MathRendererOptions.TextColor`, `FigureRendererOptions.BackgroundColor` | Implicit conversion to and from `System.Drawing.Color` |
| `SizeF` | Return value of `MathRenderer.Render` and `FigureRenderer.Render`; `Size` of `MathRendererPluginResult` and `FigureRendererPluginResult` | Implicit conversion to and from `System.Drawing.SizeF` |
| `SmoothingMode` | `ImageSaveOptions.SmoothingMode` | Same members and values as `System.Drawing.Drawing2D.SmoothingMode` |
| `InterpolationMode` | `ImageSaveOptions.InterpolationMode` | Same members and values as `System.Drawing.Drawing2D.InterpolationMode` |

## Run in Docker

Aspose.TeX typesets documents with its own embedded TeX fonts, and `Aspose.TeX.Drawing` contains its graphics backend. Your container needs no `libgdiplus`, no `fontconfig` and no installed fonts. The only system component that matters is ICU, which XPS and SVG output require (see [Globalization invariant mode](#globalization-invariant-mode)).

The official .NET images based on Debian and Ubuntu work without additional setup:

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

Replace `MyApp.dll` with the name of your application. For ASP.NET Core applications, use `mcr.microsoft.com/dotnet/aspnet` instead of `mcr.microsoft.com/dotnet/runtime`; the same rules apply.

The following table lists what each kind of image needs:

| Base image | Additional setup |
|---|---|
| `runtime:8.0`, `aspnet:8.0` (Debian) | None |
| `runtime:8.0-noble`, `aspnet:8.0-noble` (Ubuntu) | None |
| `runtime:8.0-alpine`, `aspnet:8.0-alpine` | Install ICU and turn off invariant mode (see below) |
| `runtime:8.0-noble-chiseled`, `aspnet:8.0-noble-chiseled` | Use the `-noble-chiseled-extra` variant, which includes ICU |
| `runtime:8.0-noble-chiseled-extra`, `aspnet:8.0-noble-chiseled-extra` | None |

The same applies to the .NET 9 and .NET 10 images. Both `linux/amd64` and `linux/arm64` images are supported.

### Alpine

Alpine images run .NET in globalization invariant mode and do not contain ICU. Install the `icu-libs` package and turn off invariant mode:

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

### Chiseled (distroless) images

Chiseled images contain no shell and no package manager, so you cannot install ICU into them. Use the `-chiseled-extra` variant, which already includes ICU:

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

Chiseled images run the application as a non-root user. Write output files to a writable location, such as a mounted volume or `/tmp`, rather than to the application folder.

## Globalization invariant mode

XPS and SVG output requires ICU. If .NET runs in [globalization invariant mode](https://aka.ms/GlobalizationInvariantMode), conversion to XPS or SVG fails with an exception such as:

```
System.Globalization.CultureNotFoundException: Only the invariant culture is supported in globalization-invariant mode. See https://aka.ms/GlobalizationInvariantMode for more information. (Parameter 'name')
en-US is an invalid culture identifier.
```

Invariant mode is turned on by default in Alpine and chiseled images, and by the `<InvariantGlobalization>true</InvariantGlobalization>` project property. PDF, PNG, JPEG, BMP and TIFF output works in invariant mode. If you need XPS or SVG output, install ICU as shown in [Run in Docker](#run-in-docker) and do not turn on invariant mode in the project.

## Licensing

`Aspose.TeX.Drawing` uses the same license as `Aspose.TeX`, and you apply it the same way (see [Licensing](/tex/{{lang.url-fragment}}net/licensing/)). The license also covers the embedded Aspose.Drawing backend; you do not need a separate Aspose.Drawing license.

In evaluation mode, raster output (PNG, JPEG, BMP, TIFF) of `Aspose.TeX.Drawing` carries two watermarks: the Aspose.TeX evaluation watermark and an "Evaluation only Aspose.Drawing" watermark. Both disappear once you apply the Aspose.TeX license.

## Known limitations

`Aspose.TeX.Drawing` cannot save multipage TIFF files yet. If you set `TiffSaveOptions.Multipage` to `true`, the resulting TIFF file contains only the first page of the document, and no exception is thrown. To get all pages, set `Multipage` to `false` to obtain a separate TIFF image for each page, or convert the document to PDF or XPS.

## Troubleshooting

| Error | Cause | Solution |
|---|---|---|
| `PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.` | The application uses the `Aspose.TeX` package on Linux or macOS. | Use the `Aspose.TeX.Drawing` package. |
| `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.…' from assembly 'Aspose.TeX'` | The project references both `Aspose.TeX` and `Aspose.TeX.Drawing`. | Remove the `Aspose.TeX` package. |
| `CultureNotFoundException: … en-US is an invalid culture identifier.` when saving to XPS or SVG | .NET runs in globalization invariant mode. | Install ICU and turn off invariant mode, see [Globalization invariant mode](#globalization-invariant-mode). |
| `error CS0104: 'Color' is an ambiguous reference between 'System.Drawing.Color' and 'Aspose.TeX.Drawing.Color'` | The code imports both `System.Drawing` and `Aspose.TeX.Drawing`. | Import `Aspose.TeX.Drawing` types with aliases, see [Smoothing and interpolation modes](#smoothing-and-interpolation-modes). |
| A multipage TIFF file contains only one page. | Known limitation of `Aspose.TeX.Drawing`. | See [Known limitations](#known-limitations). |

## Checklist for Linux and container deployment

- [ ] Reference `Aspose.TeX.Drawing` instead of `Aspose.TeX`, and only one of the two packages.
- [ ] If your code imports both `System.Drawing` and `Aspose.TeX.Drawing`, import the `Aspose.TeX.Drawing` types with aliases.
- [ ] If you need XPS or SVG output, make sure ICU is available and invariant mode is off: install `icu-libs` on Alpine, use the `-chiseled-extra` variant of chiseled images, and do not set `InvariantGlobalization` in the project.
- [ ] Write output files to a writable location, especially in chiseled images, which run as a non-root user.
- [ ] Apply the license once at application startup, before the first conversion.
- [ ] If you need all pages in TIFF format, set `TiffSaveOptions.Multipage` to `false` or use PDF or XPS output.
