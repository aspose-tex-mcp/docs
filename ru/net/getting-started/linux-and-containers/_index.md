---
translation: true
template: /templates/_template-net.md
title: Linux, macOS и Docker | Aspose.TeX для .NET
linktitle: Linux, macOS и Docker
weight: 55
url: /net/linux-and-containers/
description: Запуск Aspose.TeX для .NET в Linux, macOS и Docker-контейнерах с пакетом Aspose.TeX.Drawing. Выбор пакета, переход с Aspose.TeX, Dockerfile и известные ограничения.
keywords: aspose.tex linux, aspose.tex docker, aspose.tex macos, aspose.tex.drawing, latex в pdf linux .NET, latex в png docker .NET, System.Drawing.Common is not supported on this platform
lastmod: "2026-11-02"
---

{{<section overview>}}

## Выбор пакета {#choose-the-right-package}

Aspose.TeX для .NET публикуется в виде двух пакетов NuGet с одинаковым API и одинаковым номером версии:

| Пакет | Графическая подсистема | Windows | Linux, macOS | Целевые платформы |
|---|---|---|---|---|
| [`Aspose.TeX`](https://www.nuget.org/packages/Aspose.TeX) | `System.Drawing.Common` (GDI+) | Да | Нет | .NET Framework 4.0, .NET Standard 2.0, .NET 6.0, .NET 7.0 |
| **[`Aspose.TeX.Drawing`](https://www.nuget.org/packages/Aspose.TeX.Drawing)** | Aspose.Drawing (управляемая, встроена в пакет) | **Да** | **Да** | .NET Standard 2.0, .NET 7.0 |

Начиная с .NET 6, Microsoft поддерживает `System.Drawing.Common` только в Windows. Если приложение использует пакет `Aspose.TeX` в Linux или macOS, оно падает при первой же попытке что-либо отрисовать:

```
System.PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.
```

Используйте `Aspose.TeX.Drawing`, если приложение работает в Linux, macOS, Docker-контейнерах или в другой среде, отличной от Windows. Пакет работает и в Windows, поэтому, если вы собираете одно приложение для нескольких платформ, его можно использовать везде.

`Aspose.TeX.Drawing` не зависит от `System.Drawing.Common` и `libgdiplus`. Графическая подсистема Aspose.Drawing встроена в `Aspose.TeX.dll`, поэтому пакет добавляет в приложение одну сборку. Сборка для .NET 7.0 используется в .NET 7, 8, 9, 10 и более поздних версиях; сборка для .NET Standard 2.0 — в .NET Framework 4.7.2 и более поздних версиях.

## Установка пакета {#install-the-package}

Выполните одну из следующих команд в папке проекта:

```bash
dotnet add package Aspose.TeX.Drawing
```

```powershell
Install-Package Aspose.TeX.Drawing
```

Другие способы подключения пакета описаны на странице [Установка](/tex/{{lang.url-fragment}}net/installation/).

{{% alert color="primary" %}}
Подключайте только один из двух пакетов. Если проект ссылается и на `Aspose.TeX`, и на `Aspose.TeX.Drawing`, он собирается без предупреждений, но в выходную папку копируется только одна `Aspose.TeX.dll`, и приложение падает во время выполнения, например с ошибкой `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.SizeF' from assembly 'Aspose.TeX'`. При переходе на `Aspose.TeX.Drawing` сначала удалите пакет `Aspose.TeX`:

```bash
dotnet remove package Aspose.TeX
dotnet add package Aspose.TeX.Drawing
```
{{% /alert %}}

## Переход с Aspose.TeX на Aspose.TeX.Drawing {#switch-from-asposetex-to-asposetexdrawing}

Пространства имён, классы и члены в обоих пакетах одинаковы, поэтому после замены пакета большая часть кода не требует изменений.

### Цвета и размеры {#colors-and-sizes}

Параметры и результаты отрисовки используют цвета и размеры, например `MathRendererOptions.TextColor`, `FigureRendererOptions.BackgroundColor` и возвращаемое значение `MathRenderer.Render`. В `Aspose.TeX.Drawing` эти члены имеют типы `Aspose.TeX.Drawing.Color` и `Aspose.TeX.Drawing.SizeF`. Оба типа неявно преобразуются в `System.Drawing.Color` и `System.Drawing.SizeF` и обратно. Это стандартные типы .NET, доступные на любой платформе без `System.Drawing.Common`, поэтому такой код компилируется и работает с любым из пакетов:

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

### Режимы сглаживания и интерполяции {#smoothing-and-interpolation-modes}

Единственное изменение касается свойств `SmoothingMode` и `InterpolationMode` параметров сохранения изображений (`PngSaveOptions`, `JpegSaveOptions`, `BmpSaveOptions`, `TiffSaveOptions`). В пакете `Aspose.TeX` они используют перечисления из пространства имён `System.Drawing.Drawing2D`, которое относится к `System.Drawing.Common` (компилятор помечает их как доступные только в Windows предупреждением CA1416). В `Aspose.TeX.Drawing` они используют перечисления `Aspose.TeX.Drawing.SmoothingMode` и `Aspose.TeX.Drawing.InterpolationMode` с теми же членами. Замените директиву `using`, остальной код оставьте без изменений.

С `Aspose.TeX`:

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

С `Aspose.TeX.Drawing`:

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

Импортируйте эти два типа с псевдонимами, как показано выше, а не директивой `using Aspose.TeX.Drawing;`. Пространство имён `Aspose.TeX.Drawing` содержит также `Color` и `SizeF`, поэтому его импорт вместе с `System.Drawing` приводит к ошибке компиляции `CS0104: 'Color' is an ambiguous reference`.

### Типы пространства имён Aspose.TeX.Drawing {#types-of-the-asposetexdrawing-namespace}

Пространство имён `Aspose.TeX.Drawing` есть только в пакете `Aspose.TeX.Drawing`:

| Тип | Где используется | Совместимость с System.Drawing |
|---|---|---|
| `Color` | `MathRendererOptions.TextColor`, `FigureRendererOptions.BackgroundColor` | Неявное преобразование в `System.Drawing.Color` и обратно |
| `SizeF` | Возвращаемое значение `MathRenderer.Render` и `FigureRenderer.Render`; `Size` в `MathRendererPluginResult` и `FigureRendererPluginResult` | Неявное преобразование в `System.Drawing.SizeF` и обратно |
| `SmoothingMode` | `ImageSaveOptions.SmoothingMode` | Те же члены и значения, что у `System.Drawing.Drawing2D.SmoothingMode` |
| `InterpolationMode` | `ImageSaveOptions.InterpolationMode` | Те же члены и значения, что у `System.Drawing.Drawing2D.InterpolationMode` |

## Запуск в Docker {#run-in-docker}

Aspose.TeX набирает документы собственными встроенными шрифтами TeX, а `Aspose.TeX.Drawing` содержит свою графическую подсистему. Контейнеру не нужны `libgdiplus`, `fontconfig` и установленные шрифты. Значение имеет только ICU — эта библиотека нужна для вывода в XPS и SVG (см. [Инвариантный режим глобализации](#globalization-invariant-mode)).

Официальные образы .NET на основе Debian и Ubuntu работают без дополнительной настройки:

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

Замените `MyApp.dll` именем своего приложения. Для приложений ASP.NET Core используйте `mcr.microsoft.com/dotnet/aspnet` вместо `mcr.microsoft.com/dotnet/runtime`; правила те же.

В таблице указано, что нужно для каждого вида образа:

| Базовый образ | Дополнительная настройка |
|---|---|
| `runtime:8.0`, `aspnet:8.0` (Debian) | Не нужна |
| `runtime:8.0-noble`, `aspnet:8.0-noble` (Ubuntu) | Не нужна |
| `runtime:8.0-alpine`, `aspnet:8.0-alpine` | Установить ICU и отключить инвариантный режим (см. ниже) |
| `runtime:8.0-noble-chiseled`, `aspnet:8.0-noble-chiseled` | Использовать вариант `-noble-chiseled-extra`, в котором есть ICU |
| `runtime:8.0-noble-chiseled-extra`, `aspnet:8.0-noble-chiseled-extra` | Не нужна |

То же относится к образам .NET 9 и .NET 10. Поддерживаются образы `linux/amd64` и `linux/arm64`.

### Alpine {#alpine}

Образы Alpine запускают .NET в инвариантном режиме глобализации и не содержат ICU. Установите пакет `icu-libs` и отключите инвариантный режим:

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

### Chiseled-образы (distroless) {#chiseled-distroless-images}

В chiseled-образах нет оболочки и менеджера пакетов, поэтому установить в них ICU нельзя. Используйте вариант `-chiseled-extra`, в котором ICU уже есть:

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

Chiseled-образы запускают приложение от имени пользователя без прав root. Записывайте выходные файлы в доступное для записи место, например в подключённый том или `/tmp`, а не в папку приложения.

## Инвариантный режим глобализации {#globalization-invariant-mode}

Для вывода в XPS и SVG нужна ICU. Если .NET работает в [инвариантном режиме глобализации](https://aka.ms/GlobalizationInvariantMode), преобразование в XPS или SVG завершается исключением, например:

```
System.Globalization.CultureNotFoundException: Only the invariant culture is supported in globalization-invariant mode. See https://aka.ms/GlobalizationInvariantMode for more information. (Parameter 'name')
en-US is an invalid culture identifier.
```

Инвариантный режим включён по умолчанию в образах Alpine и chiseled, а также включается свойством проекта `<InvariantGlobalization>true</InvariantGlobalization>`. Вывод в PDF, PNG, JPEG, BMP и TIFF в инвариантном режиме работает. Если нужен вывод в XPS или SVG, установите ICU, как показано в разделе [Запуск в Docker](#run-in-docker), и не включайте инвариантный режим в проекте.

## Лицензирование {#licensing}

`Aspose.TeX.Drawing` использует ту же лицензию, что и `Aspose.TeX`, и применяется она так же (см. [Лицензирование](/tex/{{lang.url-fragment}}net/licensing/)). Лицензия распространяется и на встроенную графическую подсистему Aspose.Drawing; отдельная лицензия Aspose.Drawing не нужна.

В ознакомительном режиме растровый вывод (PNG, JPEG, BMP, TIFF) пакета `Aspose.TeX.Drawing` содержит два водяных знака: водяной знак ознакомительной версии Aspose.TeX и водяной знак «Evaluation only Aspose.Drawing». Оба исчезают после применения лицензии Aspose.TeX.

## Известные ограничения {#known-limitations}

`Aspose.TeX.Drawing` пока не умеет сохранять многостраничные файлы TIFF. Если установить `TiffSaveOptions.Multipage` в `true`, итоговый файл TIFF будет содержать только первую страницу документа, а исключение не возникнет. Чтобы получить все страницы, установите `Multipage` в `false` — тогда каждая страница сохранится в отдельное изображение TIFF — или преобразуйте документ в PDF или XPS.

## Устранение неполадок {#troubleshooting}

| Ошибка | Причина | Решение |
|---|---|---|
| `PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.` | Приложение использует пакет `Aspose.TeX` в Linux или macOS. | Используйте пакет `Aspose.TeX.Drawing`. |
| `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.…' from assembly 'Aspose.TeX'` | Проект ссылается и на `Aspose.TeX`, и на `Aspose.TeX.Drawing`. | Удалите пакет `Aspose.TeX`. |
| `CultureNotFoundException: … en-US is an invalid culture identifier.` при сохранении в XPS или SVG | .NET работает в инвариантном режиме глобализации. | Установите ICU и отключите инвариантный режим, см. [Инвариантный режим глобализации](#globalization-invariant-mode). |
| `error CS0104: 'Color' is an ambiguous reference between 'System.Drawing.Color' and 'Aspose.TeX.Drawing.Color'` | Код импортирует и `System.Drawing`, и `Aspose.TeX.Drawing`. | Импортируйте типы `Aspose.TeX.Drawing` с псевдонимами, см. [Режимы сглаживания и интерполяции](#smoothing-and-interpolation-modes). |
| Многостраничный файл TIFF содержит только одну страницу. | Известное ограничение `Aspose.TeX.Drawing`. | См. [Известные ограничения](#known-limitations). |

## Контрольный список для развёртывания в Linux и контейнерах {#checklist-for-linux-and-container-deployment}

- [ ] Подключите `Aspose.TeX.Drawing` вместо `Aspose.TeX`, и только один из двух пакетов.
- [ ] Если код импортирует и `System.Drawing`, и `Aspose.TeX.Drawing`, импортируйте типы `Aspose.TeX.Drawing` с псевдонимами.
- [ ] Если нужен вывод в XPS или SVG, убедитесь, что ICU доступна, а инвариантный режим отключён: установите `icu-libs` в Alpine, используйте вариант `-chiseled-extra` chiseled-образов и не задавайте `InvariantGlobalization` в проекте.
- [ ] Записывайте выходные файлы в доступное для записи место, особенно в chiseled-образах, которые запускают приложение без прав root.
- [ ] Применяйте лицензию один раз при запуске приложения, до первого преобразования.
- [ ] Если нужны все страницы в формате TIFF, установите `TiffSaveOptions.Multipage` в `false` или используйте вывод в PDF или XPS.
