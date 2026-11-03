---
translation: true
template: /templates/_template-net.md
title: Requisitos del sistema | Aspose.TeX .NET
linktitle: Requisitos del sistema
weight: 50
url: /net/system-requirements/
description: Sistemas operativos, versiones de .NET y entornos de desarrollo compatibles con los paquetes NuGet Aspose.TeX y Aspose.TeX.Drawing.
lastmod: "2026-11-02"
---

{{<section overview>}}

Aspose.TeX para .NET está disponible como dos paquetes NuGet con la misma API. Sus requisitos del sistema difieren porque usan backends gráficos diferentes.

| | `Aspose.TeX` | `Aspose.TeX.Drawing` |
|---|---|---|
| Backend gráfico | `System.Drawing.Common` (GDI+) | Aspose.Drawing, integrado en el paquete |
| Sistemas operativos | Windows | Windows, Linux, macOS |
| Marcos de destino del paquete | .NET Framework 4.0, .NET Standard 2.0, .NET 6.0, .NET 7.0 | .NET Standard 2.0, .NET 7.0 |

## Sistemas operativos compatibles

### Aspose.TeX

* Ediciones de escritorio y servidor de Microsoft Windows (x64, x86)
* Microsoft Azure (servicios basados en Windows)

A partir de .NET 6, Microsoft admite `System.Drawing.Common`, del que depende este paquete, solo en Windows.

### Aspose.TeX.Drawing

* Ediciones de escritorio y servidor de Microsoft Windows (x64, x86)
* Linux (x64, Arm64), incluidos los contenedores Docker
* macOS

No se necesitan bibliotecas nativas como `libgdiplus` o `fontconfig`, ni fuentes instaladas. En Linux, la salida en XPS y SVG requiere ICU, que algunas imágenes de contenedor no incluyen. Consulte [Linux, macOS y Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/).

## Versiones de .NET compatibles

### Aspose.TeX

* .NET Framework 4.0 o posterior
* .NET 6 o posterior
* Cualquier otra implementación de .NET Standard 2.0, como .NET Core 2.0 o posterior

### Aspose.TeX.Drawing

* .NET 7 o posterior, incluidos .NET 8, .NET 9 y .NET 10
* .NET Framework 4.7.2 o posterior (a través de .NET Standard 2.0)
* Cualquier otra implementación de .NET Standard 2.0, como .NET Core 2.0 o posterior

## Entornos de desarrollo

Puede usar Aspose.TeX para .NET en cualquier entorno de desarrollo orientado a la plataforma .NET, como Microsoft Visual Studio, Visual Studio Code o JetBrains Rider, y con la CLI de .NET.
