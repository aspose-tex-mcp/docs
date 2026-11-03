---
translation: true
template: /templates/_template-net.md
title: Linux, macOS і Docker | Aspose.TeX для .NET
linktitle: Linux, macOS і Docker
weight: 55
url: /net/linux-and-containers/
description: Запуск Aspose.TeX для .NET у Linux, macOS і Docker-контейнерах із пакетом Aspose.TeX.Drawing. Вибір пакета, перехід з Aspose.TeX, Dockerfile та відомі обмеження.
keywords: aspose.tex linux, aspose.tex docker, aspose.tex macos, aspose.tex.drawing, latex у pdf linux .NET, latex у png docker .NET, System.Drawing.Common is not supported on this platform
lastmod: "2026-11-02"
---

{{<section overview>}}

## Вибір пакета {#choose-the-right-package}

Aspose.TeX для .NET публікується у вигляді двох пакетів NuGet з однаковим API та однаковим номером версії:

| Пакет | Графічна підсистема | Windows | Linux, macOS | Цільові платформи |
|---|---|---|---|---|
| [`Aspose.TeX`](https://www.nuget.org/packages/Aspose.TeX) | `System.Drawing.Common` (GDI+) | Так | Ні | .NET Framework 4.0, .NET Standard 2.0, .NET 6.0, .NET 7.0 |
| **[`Aspose.TeX.Drawing`](https://www.nuget.org/packages/Aspose.TeX.Drawing)** | Aspose.Drawing (керована, вбудована в пакет) | **Так** | **Так** | .NET Standard 2.0, .NET 7.0 |

Починаючи з .NET 6, Microsoft підтримує `System.Drawing.Common` лише у Windows. Якщо застосунок використовує пакет `Aspose.TeX` у Linux або macOS, він завершується з помилкою під час першої ж спроби щось відмалювати:

```
System.PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.
```

Використовуйте `Aspose.TeX.Drawing`, якщо застосунок працює в Linux, macOS, Docker-контейнерах або в іншому середовищі, відмінному від Windows. Пакет працює і у Windows, тож якщо ви збираєте один застосунок для кількох платформ, його можна використовувати всюди.

`Aspose.TeX.Drawing` не залежить від `System.Drawing.Common` і `libgdiplus`. Графічну підсистему Aspose.Drawing вбудовано в `Aspose.TeX.dll`, тому пакет додає до застосунку одну збірку. Збірка для .NET 7.0 використовується в .NET 7, 8, 9, 10 і новіших версіях; збірка для .NET Standard 2.0 — у .NET Framework 4.7.2 і новіших версіях.

## Встановлення пакета {#install-the-package}

Виконайте одну з наведених команд у папці проєкту:

```bash
dotnet add package Aspose.TeX.Drawing
```

```powershell
Install-Package Aspose.TeX.Drawing
```

Інші способи підключення пакета описано на сторінці [Встановлення](/tex/{{lang.url-fragment}}net/installation/).

{{% alert color="primary" %}}
Підключайте лише один із двох пакетів. Якщо проєкт посилається і на `Aspose.TeX`, і на `Aspose.TeX.Drawing`, він збирається без попереджень, але до вихідної папки копіюється лише одна `Aspose.TeX.dll`, і застосунок завершується з помилкою під час виконання, наприклад `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.SizeF' from assembly 'Aspose.TeX'`. Під час переходу на `Aspose.TeX.Drawing` спочатку видаліть пакет `Aspose.TeX`:

```bash
dotnet remove package Aspose.TeX
dotnet add package Aspose.TeX.Drawing
```
{{% /alert %}}

## Перехід з Aspose.TeX на Aspose.TeX.Drawing {#switch-from-asposetex-to-asposetexdrawing}

Простори імен, класи та члени в обох пакетах однакові, тому після заміни пакета більша частина коду не потребує змін.

### Кольори та розміри {#colors-and-sizes}

Параметри та результати відмальовування використовують кольори й розміри, наприклад `MathRendererOptions.TextColor`, `FigureRendererOptions.BackgroundColor` і значення, що повертає `MathRenderer.Render`. В `Aspose.TeX.Drawing` ці члени мають типи `Aspose.TeX.Drawing.Color` і `Aspose.TeX.Drawing.SizeF`. Обидва типи неявно перетворюються на `System.Drawing.Color` і `System.Drawing.SizeF` і назад. Це стандартні типи .NET, доступні на будь-якій платформі без `System.Drawing.Common`, тому такий код компілюється й працює з будь-яким із пакетів:

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

### Режими згладжування та інтерполяції {#smoothing-and-interpolation-modes}

Єдина зміна стосується властивостей `SmoothingMode` та `InterpolationMode` параметрів збереження зображень (`PngSaveOptions`, `JpegSaveOptions`, `BmpSaveOptions`, `TiffSaveOptions`). У пакеті `Aspose.TeX` вони використовують переліки з простору імен `System.Drawing.Drawing2D`, який належить до `System.Drawing.Common` (компілятор позначає їх як доступні лише у Windows попередженням CA1416). В `Aspose.TeX.Drawing` вони використовують переліки `Aspose.TeX.Drawing.SmoothingMode` і `Aspose.TeX.Drawing.InterpolationMode` з тими самими членами. Замініть директиву `using`, решту коду залиште без змін.

З `Aspose.TeX`:

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

З `Aspose.TeX.Drawing`:

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

Імпортуйте ці два типи з псевдонімами, як показано вище, а не директивою `using Aspose.TeX.Drawing;`. Простір імен `Aspose.TeX.Drawing` містить також `Color` і `SizeF`, тому його імпорт разом із `System.Drawing` призводить до помилки компіляції `CS0104: 'Color' is an ambiguous reference`.

### Типи простору імен Aspose.TeX.Drawing {#types-of-the-asposetexdrawing-namespace}

Простір імен `Aspose.TeX.Drawing` є лише в пакеті `Aspose.TeX.Drawing`:

| Тип | Де використовується | Сумісність із System.Drawing |
|---|---|---|
| `Color` | `MathRendererOptions.TextColor`, `FigureRendererOptions.BackgroundColor` | Неявне перетворення на `System.Drawing.Color` і назад |
| `SizeF` | Значення, що повертають `MathRenderer.Render` і `FigureRenderer.Render`; `Size` у `MathRendererPluginResult` і `FigureRendererPluginResult` | Неявне перетворення на `System.Drawing.SizeF` і назад |
| `SmoothingMode` | `ImageSaveOptions.SmoothingMode` | Ті самі члени й значення, що в `System.Drawing.Drawing2D.SmoothingMode` |
| `InterpolationMode` | `ImageSaveOptions.InterpolationMode` | Ті самі члени й значення, що в `System.Drawing.Drawing2D.InterpolationMode` |

## Запуск у Docker {#run-in-docker}

Aspose.TeX верстає документи власними вбудованими шрифтами TeX, а `Aspose.TeX.Drawing` містить свою графічну підсистему. Контейнеру не потрібні `libgdiplus`, `fontconfig` і встановлені шрифти. Значення має лише ICU — ця бібліотека потрібна для виведення в XPS і SVG (див. [Інваріантний режим глобалізації](#globalization-invariant-mode)).

Офіційні образи .NET на основі Debian і Ubuntu працюють без додаткового налаштування:

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

Замініть `MyApp.dll` назвою свого застосунку. Для застосунків ASP.NET Core використовуйте `mcr.microsoft.com/dotnet/aspnet` замість `mcr.microsoft.com/dotnet/runtime`; правила ті самі.

У таблиці зазначено, що потрібно для кожного виду образу:

| Базовий образ | Додаткове налаштування |
|---|---|
| `runtime:8.0`, `aspnet:8.0` (Debian) | Не потрібне |
| `runtime:8.0-noble`, `aspnet:8.0-noble` (Ubuntu) | Не потрібне |
| `runtime:8.0-alpine`, `aspnet:8.0-alpine` | Встановити ICU та вимкнути інваріантний режим (див. нижче) |
| `runtime:8.0-noble-chiseled`, `aspnet:8.0-noble-chiseled` | Використовувати варіант `-noble-chiseled-extra`, у якому є ICU |
| `runtime:8.0-noble-chiseled-extra`, `aspnet:8.0-noble-chiseled-extra` | Не потрібне |

Те саме стосується образів .NET 9 і .NET 10. Підтримуються образи `linux/amd64` і `linux/arm64`.

### Alpine {#alpine}

Образи Alpine запускають .NET в інваріантному режимі глобалізації та не містять ICU. Встановіть пакет `icu-libs` і вимкніть інваріантний режим:

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

### Chiseled-образи (distroless) {#chiseled-distroless-images}

У chiseled-образах немає оболонки та менеджера пакетів, тому встановити в них ICU неможливо. Використовуйте варіант `-chiseled-extra`, у якому ICU вже є:

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

Chiseled-образи запускають застосунок від імені користувача без прав root. Записуйте вихідні файли в місце, доступне для запису, наприклад у підключений том або `/tmp`, а не в папку застосунку.

## Інваріантний режим глобалізації {#globalization-invariant-mode}

Для виведення в XPS і SVG потрібна ICU. Якщо .NET працює в [інваріантному режимі глобалізації](https://aka.ms/GlobalizationInvariantMode), перетворення в XPS або SVG завершується винятком, наприклад:

```
System.Globalization.CultureNotFoundException: Only the invariant culture is supported in globalization-invariant mode. See https://aka.ms/GlobalizationInvariantMode for more information. (Parameter 'name')
en-US is an invalid culture identifier.
```

Інваріантний режим увімкнено за замовчуванням в образах Alpine і chiseled, а також його вмикає властивість проєкту `<InvariantGlobalization>true</InvariantGlobalization>`. Виведення в PDF, PNG, JPEG, BMP і TIFF в інваріантному режимі працює. Якщо потрібне виведення в XPS або SVG, встановіть ICU, як показано в розділі [Запуск у Docker](#run-in-docker), і не вмикайте інваріантний режим у проєкті.

## Ліцензування {#licensing}

`Aspose.TeX.Drawing` використовує ту саму ліцензію, що й `Aspose.TeX`, і застосовується вона так само (див. [Ліцензування](/tex/{{lang.url-fragment}}net/licensing/)). Ліцензія поширюється й на вбудовану графічну підсистему Aspose.Drawing; окрема ліцензія Aspose.Drawing не потрібна.

В ознайомлювальному режимі растрове виведення (PNG, JPEG, BMP, TIFF) пакета `Aspose.TeX.Drawing` містить два водяні знаки: водяний знак ознайомлювальної версії Aspose.TeX і водяний знак «Evaluation only Aspose.Drawing». Обидва зникають після застосування ліцензії Aspose.TeX.

## Відомі обмеження {#known-limitations}

`Aspose.TeX.Drawing` поки що не вміє зберігати багатосторінкові файли TIFF. Якщо встановити `TiffSaveOptions.Multipage` у `true`, отриманий файл TIFF міститиме лише першу сторінку документа, а виняток не виникне. Щоб отримати всі сторінки, встановіть `Multipage` у `false` — тоді кожна сторінка збережеться в окреме зображення TIFF — або перетворіть документ у PDF чи XPS.

## Усунення несправностей {#troubleshooting}

| Помилка | Причина | Рішення |
|---|---|---|
| `PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.` | Застосунок використовує пакет `Aspose.TeX` у Linux або macOS. | Використовуйте пакет `Aspose.TeX.Drawing`. |
| `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.…' from assembly 'Aspose.TeX'` | Проєкт посилається і на `Aspose.TeX`, і на `Aspose.TeX.Drawing`. | Видаліть пакет `Aspose.TeX`. |
| `CultureNotFoundException: … en-US is an invalid culture identifier.` під час збереження в XPS або SVG | .NET працює в інваріантному режимі глобалізації. | Встановіть ICU та вимкніть інваріантний режим, див. [Інваріантний режим глобалізації](#globalization-invariant-mode). |
| `error CS0104: 'Color' is an ambiguous reference between 'System.Drawing.Color' and 'Aspose.TeX.Drawing.Color'` | Код імпортує і `System.Drawing`, і `Aspose.TeX.Drawing`. | Імпортуйте типи `Aspose.TeX.Drawing` з псевдонімами, див. [Режими згладжування та інтерполяції](#smoothing-and-interpolation-modes). |
| Багатосторінковий файл TIFF містить лише одну сторінку. | Відоме обмеження `Aspose.TeX.Drawing`. | Див. [Відомі обмеження](#known-limitations). |

## Контрольний список для розгортання в Linux і контейнерах {#checklist-for-linux-and-container-deployment}

- [ ] Підключіть `Aspose.TeX.Drawing` замість `Aspose.TeX`, і лише один із двох пакетів.
- [ ] Якщо код імпортує і `System.Drawing`, і `Aspose.TeX.Drawing`, імпортуйте типи `Aspose.TeX.Drawing` з псевдонімами.
- [ ] Якщо потрібне виведення в XPS або SVG, переконайтеся, що ICU доступна, а інваріантний режим вимкнено: встановіть `icu-libs` в Alpine, використовуйте варіант `-chiseled-extra` chiseled-образів і не задавайте `InvariantGlobalization` у проєкті.
- [ ] Записуйте вихідні файли в місце, доступне для запису, особливо в chiseled-образах, які запускають застосунок без прав root.
- [ ] Застосовуйте ліцензію один раз під час запуску застосунку, до першого перетворення.
- [ ] Якщо потрібні всі сторінки у форматі TIFF, встановіть `TiffSaveOptions.Multipage` у `false` або використовуйте виведення в PDF чи XPS.
