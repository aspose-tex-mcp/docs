---
translation: true
template: /templates/_template-net.md
title: Systemanforderungen | Aspose.TeX .NET
linktitle: Systemanforderungen
weight: 50
url: /net/system-requirements/
description: Unterstützte Betriebssysteme, .NET-Versionen und Entwicklungsumgebungen für die NuGet-Pakete Aspose.TeX und Aspose.TeX.Drawing.
lastmod: "2026-11-02"
---

{{<section overview>}}

Aspose.TeX für .NET ist als zwei NuGet-Pakete mit derselben API verfügbar. Ihre Systemanforderungen unterscheiden sich, weil sie unterschiedliche Grafik-Backends verwenden.

| | `Aspose.TeX` | `Aspose.TeX.Drawing` |
|---|---|---|
| Grafik-Backend | `System.Drawing.Common` (GDI+) | Aspose.Drawing, im Paket enthalten |
| Betriebssysteme | Windows | Windows, Linux, macOS |
| Zielframeworks des Pakets | .NET Framework 4.0, .NET Standard 2.0, .NET 6.0, .NET 7.0 | .NET Standard 2.0, .NET 7.0 |

## Unterstützte Betriebssysteme

### Aspose.TeX

* Desktop- und Server-Editionen von Microsoft Windows (x64, x86)
* Microsoft Azure (Windows-basierte Dienste)

Ab .NET 6 unterstützt Microsoft `System.Drawing.Common`, von dem dieses Paket abhängt, nur unter Windows.

### Aspose.TeX.Drawing

* Desktop- und Server-Editionen von Microsoft Windows (x64, x86)
* Linux (x64, Arm64), einschließlich Docker-Containern
* macOS

Native Bibliotheken wie `libgdiplus` oder `fontconfig` und installierte Schriftarten sind nicht erforderlich. Unter Linux erfordert die Ausgabe in XPS und SVG ICU, das in manchen Container-Images fehlt. Siehe [Linux, macOS und Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/).

## Unterstützte .NET-Versionen

### Aspose.TeX

* .NET Framework 4.0 oder neuer
* .NET 6 oder neuer
* Jede andere Implementierung von .NET Standard 2.0, etwa .NET Core 2.0 oder neuer

### Aspose.TeX.Drawing

* .NET 7 oder neuer, einschließlich .NET 8, .NET 9 und .NET 10
* .NET Framework 4.7.2 oder neuer (über .NET Standard 2.0)
* Jede andere Implementierung von .NET Standard 2.0, etwa .NET Core 2.0 oder neuer

## Entwicklungsumgebungen

Sie können Aspose.TeX für .NET in jeder Entwicklungsumgebung verwenden, die auf die .NET-Plattform abzielt, etwa Microsoft Visual Studio, Visual Studio Code oder JetBrains Rider, sowie mit der .NET CLI.
