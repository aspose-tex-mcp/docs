---
translation: true
template: /templates/_template-net.md
title: Linux, macOS und Docker | Aspose.TeX für .NET
linktitle: Linux, macOS und Docker
weight: 55
url: /net/linux-and-containers/
description: Aspose.TeX für .NET mit dem Paket Aspose.TeX.Drawing unter Linux, macOS und in Docker-Containern ausführen. Paketauswahl, Umstieg von Aspose.TeX, Dockerfiles und bekannte Einschränkungen.
keywords: aspose.tex linux, aspose.tex docker, aspose.tex macos, aspose.tex.drawing, latex in pdf linux .NET, latex in png docker .NET, System.Drawing.Common is not supported on this platform
lastmod: "2026-11-02"
---

{{<section overview>}}

## Das richtige Paket wählen {#choose-the-right-package}

Aspose.TeX für .NET wird als zwei NuGet-Pakete mit derselben API und derselben Versionsnummer veröffentlicht:

| Paket | Grafik-Backend | Windows | Linux, macOS | Zielframeworks |
|---|---|---|---|---|
| [`Aspose.TeX`](https://www.nuget.org/packages/Aspose.TeX) | `System.Drawing.Common` (GDI+) | Ja | Nein | .NET Framework 4.0, .NET Standard 2.0, .NET 6.0, .NET 7.0 |
| **[`Aspose.TeX.Drawing`](https://www.nuget.org/packages/Aspose.TeX.Drawing)** | Aspose.Drawing (verwaltet, im Paket enthalten) | **Ja** | **Ja** | .NET Standard 2.0, .NET 7.0 |

Ab .NET 6 unterstützt Microsoft `System.Drawing.Common` nur unter Windows. Verwendet Ihre Anwendung das Paket `Aspose.TeX` unter Linux oder macOS, schlägt sie fehl, sobald sie etwas rendert:

```
System.PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.
```

Verwenden Sie `Aspose.TeX.Drawing`, wenn Ihre Anwendung unter Linux, macOS, in Docker-Containern oder in anderen Umgebungen außer Windows läuft. Das Paket funktioniert auch unter Windows. Wenn Sie eine Anwendung für mehrere Plattformen erstellen, können Sie es also überall verwenden.

`Aspose.TeX.Drawing` hängt weder von `System.Drawing.Common` noch von `libgdiplus` ab. Das Grafik-Backend Aspose.Drawing ist in `Aspose.TeX.dll` eingebettet, sodass das Paket Ihrer Anwendung eine einzige Assembly hinzufügt. Der Build für .NET 7.0 wird von .NET 7, 8, 9, 10 und neuer verwendet; der Build für .NET Standard 2.0 von .NET Framework 4.7.2 und neuer.

## Das Paket installieren {#install-the-package}

Führen Sie einen der folgenden Befehle im Ordner Ihres Projekts aus:

```bash
dotnet add package Aspose.TeX.Drawing
```

```powershell
Install-Package Aspose.TeX.Drawing
```

Weitere Möglichkeiten, das Paket einzubinden, finden Sie unter [Installation](/tex/{{lang.url-fragment}}net/installation/).

{{% alert color="primary" %}}
Binden Sie nur eines der beiden Pakete ein. Verweist ein Projekt sowohl auf `Aspose.TeX` als auch auf `Aspose.TeX.Drawing`, wird es ohne Warnungen erstellt, aber nur eine `Aspose.TeX.dll` wird in den Ausgabeordner kopiert, und die Anwendung schlägt zur Laufzeit fehl, zum Beispiel mit `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.SizeF' from assembly 'Aspose.TeX'`. Entfernen Sie beim Umstieg auf `Aspose.TeX.Drawing` zuerst das Paket `Aspose.TeX`:

```bash
dotnet remove package Aspose.TeX
dotnet add package Aspose.TeX.Drawing
```
{{% /alert %}}

## Von Aspose.TeX zu Aspose.TeX.Drawing wechseln {#switch-from-asposetex-to-asposetexdrawing}

Namespaces, Klassen und Member sind in beiden Paketen gleich, daher muss der meiste Code nach dem Austausch des Pakets nicht geändert werden.

### Farben und Größen {#colors-and-sizes}

Render-Optionen und -Ergebnisse verwenden Farben und Größen, zum Beispiel `MathRendererOptions.TextColor`, `FigureRendererOptions.BackgroundColor` und den Rückgabewert von `MathRenderer.Render`. In `Aspose.TeX.Drawing` haben diese Member die Typen `Aspose.TeX.Drawing.Color` und `Aspose.TeX.Drawing.SizeF`. Beide Typen werden implizit in `System.Drawing.Color` und `System.Drawing.SizeF` und zurück konvertiert. Das sind Standardtypen von .NET, die auf jeder Plattform ohne `System.Drawing.Common` verfügbar sind. Code wie der folgende wird daher mit beiden Paketen kompiliert und ausgeführt:

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

### Glättungs- und Interpolationsmodi {#smoothing-and-interpolation-modes}

Die einzige Änderung betrifft die Eigenschaften `SmoothingMode` und `InterpolationMode` der Bildspeicheroptionen (`PngSaveOptions`, `JpegSaveOptions`, `BmpSaveOptions`, `TiffSaveOptions`). Im Paket `Aspose.TeX` verwenden sie Enumerationen aus dem Namespace `System.Drawing.Drawing2D`, der zu `System.Drawing.Common` gehört (der Compiler meldet sie mit der Warnung CA1416 als nur unter Windows verfügbar). In `Aspose.TeX.Drawing` verwenden sie die Enumerationen `Aspose.TeX.Drawing.SmoothingMode` und `Aspose.TeX.Drawing.InterpolationMode`, die dieselben Member haben. Ersetzen Sie die `using`-Direktive und lassen Sie den übrigen Code unverändert.

Mit `Aspose.TeX`:

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

Mit `Aspose.TeX.Drawing`:

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

Importieren Sie diese beiden Typen wie oben gezeigt mit Aliasen und nicht mit `using Aspose.TeX.Drawing;`. Der Namespace `Aspose.TeX.Drawing` enthält auch `Color` und `SizeF`. Wird er zusammen mit `System.Drawing` importiert, meldet der Compiler den Fehler `CS0104: 'Color' is an ambiguous reference`.

### Typen des Namespace Aspose.TeX.Drawing {#types-of-the-asposetexdrawing-namespace}

Den Namespace `Aspose.TeX.Drawing` gibt es nur im Paket `Aspose.TeX.Drawing`:

| Typ | Verwendet von | Kompatibilität mit System.Drawing |
|---|---|---|
| `Color` | `MathRendererOptions.TextColor`, `FigureRendererOptions.BackgroundColor` | Implizite Konvertierung in `System.Drawing.Color` und zurück |
| `SizeF` | Rückgabewert von `MathRenderer.Render` und `FigureRenderer.Render`; `Size` von `MathRendererPluginResult` und `FigureRendererPluginResult` | Implizite Konvertierung in `System.Drawing.SizeF` und zurück |
| `SmoothingMode` | `ImageSaveOptions.SmoothingMode` | Dieselben Member und Werte wie `System.Drawing.Drawing2D.SmoothingMode` |
| `InterpolationMode` | `ImageSaveOptions.InterpolationMode` | Dieselben Member und Werte wie `System.Drawing.Drawing2D.InterpolationMode` |

## In Docker ausführen {#run-in-docker}

Aspose.TeX setzt Dokumente mit seinen eigenen eingebetteten TeX-Schriftarten, und `Aspose.TeX.Drawing` enthält sein Grafik-Backend. Ihr Container benötigt weder `libgdiplus` noch `fontconfig` noch installierte Schriftarten. Die einzige relevante Systemkomponente ist ICU, die für die Ausgabe in XPS und SVG erforderlich ist (siehe [Invarianter Globalisierungsmodus](#globalization-invariant-mode)).

Die offiziellen .NET-Images auf Basis von Debian und Ubuntu funktionieren ohne zusätzliche Einrichtung:

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

Ersetzen Sie `MyApp.dll` durch den Namen Ihrer Anwendung. Verwenden Sie für ASP.NET Core-Anwendungen `mcr.microsoft.com/dotnet/aspnet` statt `mcr.microsoft.com/dotnet/runtime`; es gelten dieselben Regeln.

Die folgende Tabelle zeigt, was jede Art von Image benötigt:

| Basis-Image | Zusätzliche Einrichtung |
|---|---|
| `runtime:8.0`, `aspnet:8.0` (Debian) | Keine |
| `runtime:8.0-noble`, `aspnet:8.0-noble` (Ubuntu) | Keine |
| `runtime:8.0-alpine`, `aspnet:8.0-alpine` | ICU installieren und den invarianten Modus ausschalten (siehe unten) |
| `runtime:8.0-noble-chiseled`, `aspnet:8.0-noble-chiseled` | Die Variante `-noble-chiseled-extra` verwenden, die ICU enthält |
| `runtime:8.0-noble-chiseled-extra`, `aspnet:8.0-noble-chiseled-extra` | Keine |

Dasselbe gilt für die Images von .NET 9 und .NET 10. Images für `linux/amd64` und `linux/arm64` werden unterstützt.

### Alpine {#alpine}

Alpine-Images führen .NET im invarianten Globalisierungsmodus aus und enthalten kein ICU. Installieren Sie das Paket `icu-libs` und schalten Sie den invarianten Modus aus:

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

### Chiseled-Images (distroless) {#chiseled-distroless-images}

Chiseled-Images enthalten weder eine Shell noch einen Paketmanager, daher können Sie ICU darin nicht installieren. Verwenden Sie die Variante `-chiseled-extra`, die ICU bereits enthält:

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

Chiseled-Images führen die Anwendung als Benutzer ohne Root-Rechte aus. Schreiben Sie Ausgabedateien an einen beschreibbaren Ort, etwa in ein eingebundenes Volume oder nach `/tmp`, und nicht in den Anwendungsordner.

## Invarianter Globalisierungsmodus {#globalization-invariant-mode}

Die Ausgabe in XPS und SVG erfordert ICU. Läuft .NET im [invarianten Globalisierungsmodus](https://aka.ms/GlobalizationInvariantMode), schlägt die Konvertierung in XPS oder SVG mit einer Ausnahme wie dieser fehl:

```
System.Globalization.CultureNotFoundException: Only the invariant culture is supported in globalization-invariant mode. See https://aka.ms/GlobalizationInvariantMode for more information. (Parameter 'name')
en-US is an invalid culture identifier.
```

Der invariante Modus ist in Alpine- und Chiseled-Images standardmäßig eingeschaltet und wird außerdem durch die Projekteigenschaft `<InvariantGlobalization>true</InvariantGlobalization>` aktiviert. Die Ausgabe in PDF, PNG, JPEG, BMP und TIFF funktioniert im invarianten Modus. Wenn Sie XPS- oder SVG-Ausgabe benötigen, installieren Sie ICU wie unter [In Docker ausführen](#run-in-docker) gezeigt und schalten Sie den invarianten Modus im Projekt nicht ein.

## Lizenzierung {#licensing}

`Aspose.TeX.Drawing` verwendet dieselbe Lizenz wie `Aspose.TeX`, und Sie wenden sie auf dieselbe Weise an (siehe [Lizenzierung](/tex/{{lang.url-fragment}}net/licensing/)). Die Lizenz deckt auch das eingebettete Grafik-Backend Aspose.Drawing ab; eine separate Aspose.Drawing-Lizenz ist nicht erforderlich.

Im Evaluierungsmodus trägt die Rasterausgabe (PNG, JPEG, BMP, TIFF) von `Aspose.TeX.Drawing` zwei Wasserzeichen: das Evaluierungswasserzeichen von Aspose.TeX und das Wasserzeichen „Evaluation only Aspose.Drawing“. Beide verschwinden, sobald Sie die Aspose.TeX-Lizenz anwenden.

## Bekannte Einschränkungen {#known-limitations}

`Aspose.TeX.Drawing` kann noch keine mehrseitigen TIFF-Dateien speichern. Wenn Sie `TiffSaveOptions.Multipage` auf `true` setzen, enthält die resultierende TIFF-Datei nur die erste Seite des Dokuments, und es wird keine Ausnahme ausgelöst. Um alle Seiten zu erhalten, setzen Sie `Multipage` auf `false` – dann wird für jede Seite ein eigenes TIFF-Bild erzeugt – oder konvertieren Sie das Dokument in PDF oder XPS.

## Fehlerbehebung {#troubleshooting}

| Fehler | Ursache | Lösung |
|---|---|---|
| `PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.` | Die Anwendung verwendet das Paket `Aspose.TeX` unter Linux oder macOS. | Verwenden Sie das Paket `Aspose.TeX.Drawing`. |
| `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.…' from assembly 'Aspose.TeX'` | Das Projekt verweist sowohl auf `Aspose.TeX` als auch auf `Aspose.TeX.Drawing`. | Entfernen Sie das Paket `Aspose.TeX`. |
| `CultureNotFoundException: … en-US is an invalid culture identifier.` beim Speichern in XPS oder SVG | .NET läuft im invarianten Globalisierungsmodus. | Installieren Sie ICU und schalten Sie den invarianten Modus aus, siehe [Invarianter Globalisierungsmodus](#globalization-invariant-mode). |
| `error CS0104: 'Color' is an ambiguous reference between 'System.Drawing.Color' and 'Aspose.TeX.Drawing.Color'` | Der Code importiert sowohl `System.Drawing` als auch `Aspose.TeX.Drawing`. | Importieren Sie die Typen von `Aspose.TeX.Drawing` mit Aliasen, siehe [Glättungs- und Interpolationsmodi](#smoothing-and-interpolation-modes). |
| Eine mehrseitige TIFF-Datei enthält nur eine Seite. | Bekannte Einschränkung von `Aspose.TeX.Drawing`. | Siehe [Bekannte Einschränkungen](#known-limitations). |

## Checkliste für die Bereitstellung unter Linux und in Containern {#checklist-for-linux-and-container-deployment}

- [ ] Binden Sie `Aspose.TeX.Drawing` statt `Aspose.TeX` ein, und nur eines der beiden Pakete.
- [ ] Wenn Ihr Code sowohl `System.Drawing` als auch `Aspose.TeX.Drawing` importiert, importieren Sie die Typen von `Aspose.TeX.Drawing` mit Aliasen.
- [ ] Wenn Sie XPS- oder SVG-Ausgabe benötigen, stellen Sie sicher, dass ICU verfügbar und der invariante Modus ausgeschaltet ist: Installieren Sie `icu-libs` unter Alpine, verwenden Sie die Variante `-chiseled-extra` der Chiseled-Images und setzen Sie `InvariantGlobalization` im Projekt nicht.
- [ ] Schreiben Sie Ausgabedateien an einen beschreibbaren Ort, besonders in Chiseled-Images, die die Anwendung ohne Root-Rechte ausführen.
- [ ] Wenden Sie die Lizenz einmal beim Start der Anwendung an, vor der ersten Konvertierung.
- [ ] Wenn Sie alle Seiten im TIFF-Format benötigen, setzen Sie `TiffSaveOptions.Multipage` auf `false` oder verwenden Sie die Ausgabe in PDF oder XPS.
