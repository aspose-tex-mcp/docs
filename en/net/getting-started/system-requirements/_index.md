---
translation: true
template: /templates/_template-net.md
title: System Requirements | Aspose.TeX .NET
linktitle: System Requirements
weight: 50
url: /net/system-requirements/
description: Supported operating systems, .NET versions and development environments for the Aspose.TeX and Aspose.TeX.Drawing NuGet packages.
lastmod: "2026-11-02"
---

{{<section overview>}}

Aspose.TeX for .NET is available as two NuGet packages with the same API. Their system requirements differ because they use different graphics backends.

| | `Aspose.TeX` | `Aspose.TeX.Drawing` |
|---|---|---|
| Graphics backend | `System.Drawing.Common` (GDI+) | Aspose.Drawing, embedded in the package |
| Operating systems | Windows | Windows, Linux, macOS |
| Target frameworks of the package | .NET Framework 4.0, .NET Standard 2.0, .NET 6.0, .NET 7.0 | .NET Standard 2.0, .NET 7.0 |

## Supported Operating Systems

### Aspose.TeX

* Microsoft Windows desktop and server editions (x64, x86)
* Microsoft Azure (Windows-based services)

Starting with .NET 6, Microsoft supports `System.Drawing.Common`, which this package depends on, only on Windows.

### Aspose.TeX.Drawing

* Microsoft Windows desktop and server editions (x64, x86)
* Linux (x64, Arm64), including Docker containers
* macOS

No native libraries such as `libgdiplus` or `fontconfig`, and no installed fonts are required. On Linux, XPS and SVG output requires ICU, which some container images do not include. See [Linux, macOS and Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/).

## Supported .NET Versions

### Aspose.TeX

* .NET Framework 4.0 or later
* .NET 6 or later
* Any other implementation of .NET Standard 2.0, such as .NET Core 2.0 or later

### Aspose.TeX.Drawing

* .NET 7 or later, including .NET 8, .NET 9 and .NET 10
* .NET Framework 4.7.2 or later (through .NET Standard 2.0)
* Any other implementation of .NET Standard 2.0, such as .NET Core 2.0 or later

## Development Environments

You can use Aspose.TeX for .NET in any development environment that targets the .NET platform, such as Microsoft Visual Studio, Visual Studio Code or JetBrains Rider, and with the .NET CLI.
