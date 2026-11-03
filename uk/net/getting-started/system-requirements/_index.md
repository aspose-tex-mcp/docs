---
translation: true
template: /templates/_template-net.md
title: Системні вимоги | Aspose.TeX .NET
linktitle: Системні вимоги
weight: 50
url: /net/system-requirements/
description: Підтримувані операційні системи, версії .NET і середовища розробки для пакетів NuGet Aspose.TeX і Aspose.TeX.Drawing.
lastmod: "2026-11-02"
---

{{<section overview>}}

Aspose.TeX для .NET випускається у вигляді двох пакетів NuGet з однаковим API. Системні вимоги до них відрізняються, оскільки вони використовують різні графічні підсистеми.

| | `Aspose.TeX` | `Aspose.TeX.Drawing` |
|---|---|---|
| Графічна підсистема | `System.Drawing.Common` (GDI+) | Aspose.Drawing, вбудована в пакет |
| Операційні системи | Windows | Windows, Linux, macOS |
| Цільові платформи пакета | .NET Framework 4.0, .NET Standard 2.0, .NET 6.0, .NET 7.0 | .NET Standard 2.0, .NET 7.0 |

## Підтримувані операційні системи

### Aspose.TeX

* Настільні та серверні випуски Microsoft Windows (x64, x86)
* Microsoft Azure (служби на основі Windows)

Починаючи з .NET 6, Microsoft підтримує `System.Drawing.Common`, від якої залежить цей пакет, лише у Windows.

### Aspose.TeX.Drawing

* Настільні та серверні випуски Microsoft Windows (x64, x86)
* Linux (x64, Arm64), зокрема Docker-контейнери
* macOS

Нативні бібліотеки, такі як `libgdiplus` або `fontconfig`, і встановлені шрифти не потрібні. У Linux для виведення в XPS і SVG потрібна ICU, якої немає в деяких образах контейнерів. Див. [Linux, macOS і Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/).

## Підтримувані версії .NET

### Aspose.TeX

* .NET Framework 4.0 або новіша версія
* .NET 6 або новіша версія
* Будь-яка інша реалізація .NET Standard 2.0, наприклад .NET Core 2.0 або новіша версія

### Aspose.TeX.Drawing

* .NET 7 або новіша версія, зокрема .NET 8, .NET 9 і .NET 10
* .NET Framework 4.7.2 або новіша версія (через .NET Standard 2.0)
* Будь-яка інша реалізація .NET Standard 2.0, наприклад .NET Core 2.0 або новіша версія

## Середовища розробки

Aspose.TeX для .NET можна використовувати в будь-якому середовищі розробки для платформи .NET, наприклад у Microsoft Visual Studio, Visual Studio Code або JetBrains Rider, а також із .NET CLI.
