---
translation: true
template: /templates/_template-net.md
title: Системные требования | Aspose.TeX .NET
linktitle: Системные требования
weight: 50
url: /net/system-requirements/
description: Поддерживаемые операционные системы, версии .NET и среды разработки для пакетов NuGet Aspose.TeX и Aspose.TeX.Drawing.
lastmod: "2026-11-02"
---

{{<section overview>}}

Aspose.TeX для .NET выпускается в виде двух пакетов NuGet с одинаковым API. Системные требования у них различаются, поскольку они используют разные графические подсистемы.

| | `Aspose.TeX` | `Aspose.TeX.Drawing` |
|---|---|---|
| Графическая подсистема | `System.Drawing.Common` (GDI+) | Aspose.Drawing, встроена в пакет |
| Операционные системы | Windows | Windows, Linux, macOS |
| Целевые платформы пакета | .NET Framework 4.0, .NET Standard 2.0, .NET 6.0, .NET 7.0 | .NET Standard 2.0, .NET 7.0 |

## Поддерживаемые операционные системы

### Aspose.TeX

* Настольные и серверные выпуски Microsoft Windows (x64, x86)
* Microsoft Azure (службы на основе Windows)

Начиная с .NET 6, Microsoft поддерживает `System.Drawing.Common`, от которой зависит этот пакет, только в Windows.

### Aspose.TeX.Drawing

* Настольные и серверные выпуски Microsoft Windows (x64, x86)
* Linux (x64, Arm64), включая Docker-контейнеры
* macOS

Нативные библиотеки, такие как `libgdiplus` или `fontconfig`, и установленные шрифты не нужны. В Linux для вывода в XPS и SVG требуется ICU, которой нет в некоторых образах контейнеров. См. [Linux, macOS и Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/).

## Поддерживаемые версии .NET

### Aspose.TeX

* .NET Framework 4.0 или более поздняя версия
* .NET 6 или более поздняя версия
* Любая другая реализация .NET Standard 2.0, например .NET Core 2.0 или более поздняя версия

### Aspose.TeX.Drawing

* .NET 7 или более поздняя версия, включая .NET 8, .NET 9 и .NET 10
* .NET Framework 4.7.2 или более поздняя версия (через .NET Standard 2.0)
* Любая другая реализация .NET Standard 2.0, например .NET Core 2.0 или более поздняя версия

## Среды разработки

Aspose.TeX для .NET можно использовать в любой среде разработки для платформы .NET, например в Microsoft Visual Studio, Visual Studio Code или JetBrains Rider, а также с .NET CLI.
