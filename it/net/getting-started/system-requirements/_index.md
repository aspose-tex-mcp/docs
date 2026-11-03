---
translation: true
template: /templates/_template-net.md
title: Requisiti di sistema | Aspose.TeX per .NET
linktitle: Requisiti di sistema
weight: 50
url: /net/system-requirements/
description: Sistemi operativi, versioni di .NET e ambienti di sviluppo supportati dai pacchetti NuGet Aspose.TeX e Aspose.TeX.Drawing.
lastmod: "2026-11-02"
---

{{<section overview>}}

Aspose.TeX per .NET è disponibile come due pacchetti NuGet con la stessa API. I loro requisiti di sistema sono diversi perché usano backend grafici diversi.

| | `Aspose.TeX` | `Aspose.TeX.Drawing` |
|---|---|---|
| Backend grafico | `System.Drawing.Common` (GDI+) | Aspose.Drawing, incluso nel pacchetto |
| Sistemi operativi | Windows | Windows, Linux, macOS |
| Framework di destinazione del pacchetto | .NET Framework 4.0, .NET Standard 2.0, .NET 6.0, .NET 7.0 | .NET Standard 2.0, .NET 7.0 |

## Sistemi operativi supportati

### Aspose.TeX

* Edizioni desktop e server di Microsoft Windows (x64, x86)
* Microsoft Azure (servizi basati su Windows)

A partire da .NET 6, Microsoft supporta `System.Drawing.Common`, da cui dipende questo pacchetto, solo su Windows.

### Aspose.TeX.Drawing

* Edizioni desktop e server di Microsoft Windows (x64, x86)
* Linux (x64, Arm64), inclusi i container Docker
* macOS

Non sono necessarie librerie native come `libgdiplus` o `fontconfig`, né font installati. Su Linux, l'output in XPS e SVG richiede ICU, che alcune immagini di container non includono. Vedere [Linux, macOS e Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/).

## Versioni di .NET supportate

### Aspose.TeX

* .NET Framework 4.0 o versioni successive
* .NET 6 o versioni successive
* Qualsiasi altra implementazione di .NET Standard 2.0, ad esempio .NET Core 2.0 o versioni successive

### Aspose.TeX.Drawing

* .NET 7 o versioni successive, inclusi .NET 8, .NET 9 e .NET 10
* .NET Framework 4.7.2 o versioni successive (tramite .NET Standard 2.0)
* Qualsiasi altra implementazione di .NET Standard 2.0, ad esempio .NET Core 2.0 o versioni successive

## Ambienti di sviluppo

È possibile usare Aspose.TeX per .NET in qualsiasi ambiente di sviluppo destinato alla piattaforma .NET, ad esempio Microsoft Visual Studio, Visual Studio Code o JetBrains Rider, e con la CLI di .NET.
