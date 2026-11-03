---
translation: true
template: /templates/_template-net.md
title: Linux, macOS e Docker | Aspose.TeX per .NET
linktitle: Linux, macOS e Docker
weight: 55
url: /net/linux-and-containers/
description: Eseguire Aspose.TeX per .NET su Linux, macOS e nei container Docker con il pacchetto Aspose.TeX.Drawing. Scelta del pacchetto, migrazione da Aspose.TeX, Dockerfile e limitazioni note.
keywords: aspose.tex linux, aspose.tex docker, aspose.tex macos, aspose.tex.drawing, latex a pdf linux .NET, latex a png docker .NET, System.Drawing.Common is not supported on this platform
lastmod: "2026-11-02"
---

{{<section overview>}}

## Scegliere il pacchetto giusto {#choose-the-right-package}

Aspose.TeX per .NET è pubblicato come due pacchetti NuGet con la stessa API e lo stesso numero di versione:

| Pacchetto | Backend grafico | Windows | Linux, macOS | Framework di destinazione |
|---|---|---|---|---|
| [`Aspose.TeX`](https://www.nuget.org/packages/Aspose.TeX) | `System.Drawing.Common` (GDI+) | Sì | No | .NET Framework 4.0, .NET Standard 2.0, .NET 6.0, .NET 7.0 |
| **[`Aspose.TeX.Drawing`](https://www.nuget.org/packages/Aspose.TeX.Drawing)** | Aspose.Drawing (gestito, incluso nel pacchetto) | **Sì** | **Sì** | .NET Standard 2.0, .NET 7.0 |

A partire da .NET 6, Microsoft supporta `System.Drawing.Common` solo su Windows. Se l'applicazione usa il pacchetto `Aspose.TeX` su Linux o macOS, si interrompe non appena esegue un rendering:

```
System.PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.
```

Usare `Aspose.TeX.Drawing` quando l'applicazione viene eseguita su Linux, macOS, in container Docker o in altri ambienti diversi da Windows. Il pacchetto funziona anche su Windows, quindi è possibile usarlo ovunque se si compila un'unica applicazione per più piattaforme.

`Aspose.TeX.Drawing` non dipende da `System.Drawing.Common` né da `libgdiplus`. Il backend grafico Aspose.Drawing è incorporato in `Aspose.TeX.dll`, quindi il pacchetto aggiunge all'applicazione un solo assembly. La build per .NET 7.0 viene usata da .NET 7, 8, 9, 10 e versioni successive; la build per .NET Standard 2.0 da .NET Framework 4.7.2 e versioni successive.

## Installare il pacchetto {#install-the-package}

Eseguire uno dei seguenti comandi nella cartella del progetto:

```bash
dotnet add package Aspose.TeX.Drawing
```

```powershell
Install-Package Aspose.TeX.Drawing
```

Per altri modi di aggiungere il riferimento al pacchetto, vedere [Installazione](/tex/{{lang.url-fragment}}net/installation/).

{{% alert color="primary" %}}
Fare riferimento a uno solo dei due pacchetti. Se un progetto fa riferimento sia ad `Aspose.TeX` sia ad `Aspose.TeX.Drawing`, viene compilato senza avvisi, ma nella cartella di output viene copiato un solo `Aspose.TeX.dll` e l'applicazione si interrompe in fase di esecuzione, ad esempio con `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.SizeF' from assembly 'Aspose.TeX'`. Quando si passa ad `Aspose.TeX.Drawing`, rimuovere prima il pacchetto `Aspose.TeX`:

```bash
dotnet remove package Aspose.TeX
dotnet add package Aspose.TeX.Drawing
```
{{% /alert %}}

## Passare da Aspose.TeX ad Aspose.TeX.Drawing {#switch-from-asposetex-to-asposetexdrawing}

Spazi dei nomi, classi e membri sono gli stessi in entrambi i pacchetti, quindi la maggior parte del codice non richiede modifiche dopo la sostituzione del pacchetto.

### Colori e dimensioni {#colors-and-sizes}

Le opzioni e i risultati del rendering usano colori e dimensioni, ad esempio `MathRendererOptions.TextColor`, `FigureRendererOptions.BackgroundColor` e il valore restituito da `MathRenderer.Render`. In `Aspose.TeX.Drawing` questi membri hanno i tipi `Aspose.TeX.Drawing.Color` e `Aspose.TeX.Drawing.SizeF`. Entrambi i tipi si convertono implicitamente da e verso `System.Drawing.Color` e `System.Drawing.SizeF`. Si tratta di tipi .NET standard, disponibili su ogni piattaforma senza `System.Drawing.Common`, quindi un codice come il seguente viene compilato ed eseguito con entrambi i pacchetti:

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

### Modalità di smussatura e interpolazione {#smoothing-and-interpolation-modes}

L'unica modifica riguarda le proprietà `SmoothingMode` e `InterpolationMode` delle opzioni di salvataggio delle immagini (`PngSaveOptions`, `JpegSaveOptions`, `BmpSaveOptions`, `TiffSaveOptions`). Nel pacchetto `Aspose.TeX` usano enumerazioni dello spazio dei nomi `System.Drawing.Drawing2D`, che appartiene a `System.Drawing.Common` (il compilatore le segnala come solo Windows con l'avviso CA1416). In `Aspose.TeX.Drawing` usano le enumerazioni `Aspose.TeX.Drawing.SmoothingMode` e `Aspose.TeX.Drawing.InterpolationMode`, che hanno gli stessi membri. Sostituire la direttiva `using` e lasciare invariato il resto del codice.

Con `Aspose.TeX`:

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

Con `Aspose.TeX.Drawing`:

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

Importare questi due tipi con alias, come mostrato sopra, e non con `using Aspose.TeX.Drawing;`. Lo spazio dei nomi `Aspose.TeX.Drawing` contiene anche `Color` e `SizeF`, quindi importarlo insieme a `System.Drawing` causa l'errore di compilazione `CS0104: 'Color' is an ambiguous reference`.

### Tipi dello spazio dei nomi Aspose.TeX.Drawing {#types-of-the-asposetexdrawing-namespace}

Lo spazio dei nomi `Aspose.TeX.Drawing` esiste solo nel pacchetto `Aspose.TeX.Drawing`:

| Tipo | Usato da | Compatibilità con System.Drawing |
|---|---|---|
| `Color` | `MathRendererOptions.TextColor`, `FigureRendererOptions.BackgroundColor` | Conversione implicita da e verso `System.Drawing.Color` |
| `SizeF` | Valore restituito da `MathRenderer.Render` e `FigureRenderer.Render`; `Size` di `MathRendererPluginResult` e `FigureRendererPluginResult` | Conversione implicita da e verso `System.Drawing.SizeF` |
| `SmoothingMode` | `ImageSaveOptions.SmoothingMode` | Stessi membri e valori di `System.Drawing.Drawing2D.SmoothingMode` |
| `InterpolationMode` | `ImageSaveOptions.InterpolationMode` | Stessi membri e valori di `System.Drawing.Drawing2D.InterpolationMode` |

## Eseguire in Docker {#run-in-docker}

Aspose.TeX compone i documenti con i propri font TeX incorporati, e `Aspose.TeX.Drawing` contiene il proprio backend grafico. Il container non richiede `libgdiplus`, `fontconfig` né font installati. L'unico componente di sistema rilevante è ICU, necessario per l'output in XPS e SVG (vedere [Modalità invariante di globalizzazione](#globalization-invariant-mode)).

Le immagini .NET ufficiali basate su Debian e Ubuntu funzionano senza configurazione aggiuntiva:

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

Sostituire `MyApp.dll` con il nome dell'applicazione. Per le applicazioni ASP.NET Core, usare `mcr.microsoft.com/dotnet/aspnet` invece di `mcr.microsoft.com/dotnet/runtime`; valgono le stesse regole.

La tabella seguente indica cosa serve per ciascun tipo di immagine:

| Immagine di base | Configurazione aggiuntiva |
|---|---|
| `runtime:8.0`, `aspnet:8.0` (Debian) | Nessuna |
| `runtime:8.0-noble`, `aspnet:8.0-noble` (Ubuntu) | Nessuna |
| `runtime:8.0-alpine`, `aspnet:8.0-alpine` | Installare ICU e disattivare la modalità invariante (vedere sotto) |
| `runtime:8.0-noble-chiseled`, `aspnet:8.0-noble-chiseled` | Usare la variante `-noble-chiseled-extra`, che include ICU |
| `runtime:8.0-noble-chiseled-extra`, `aspnet:8.0-noble-chiseled-extra` | Nessuna |

Lo stesso vale per le immagini di .NET 9 e .NET 10. Sono supportate le immagini `linux/amd64` e `linux/arm64`.

### Alpine {#alpine}

Le immagini Alpine eseguono .NET in modalità invariante di globalizzazione e non contengono ICU. Installare il pacchetto `icu-libs` e disattivare la modalità invariante:

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

### Immagini chiseled (distroless) {#chiseled-distroless-images}

Le immagini chiseled non contengono né una shell né un gestore di pacchetti, quindi non è possibile installarvi ICU. Usare la variante `-chiseled-extra`, che include già ICU:

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

Le immagini chiseled eseguono l'applicazione come utente senza privilegi di root. Scrivere i file di output in una posizione scrivibile, ad esempio un volume montato o `/tmp`, anziché nella cartella dell'applicazione.

## Modalità invariante di globalizzazione {#globalization-invariant-mode}

L'output in XPS e SVG richiede ICU. Se .NET viene eseguito in [modalità invariante di globalizzazione](https://aka.ms/GlobalizationInvariantMode), la conversione in XPS o SVG non riesce e genera un'eccezione come questa:

```
System.Globalization.CultureNotFoundException: Only the invariant culture is supported in globalization-invariant mode. See https://aka.ms/GlobalizationInvariantMode for more information. (Parameter 'name')
en-US is an invalid culture identifier.
```

La modalità invariante è attiva per impostazione predefinita nelle immagini Alpine e chiseled e viene attivata anche dalla proprietà di progetto `<InvariantGlobalization>true</InvariantGlobalization>`. L'output in PDF, PNG, JPEG, BMP e TIFF funziona in modalità invariante. Se serve l'output in XPS o SVG, installare ICU come mostrato in [Eseguire in Docker](#run-in-docker) e non attivare la modalità invariante nel progetto.

## Licenze {#licensing}

`Aspose.TeX.Drawing` usa la stessa licenza di `Aspose.TeX` e la si applica allo stesso modo (vedere [Licenze](/tex/{{lang.url-fragment}}net/licensing/)). La licenza copre anche il backend grafico Aspose.Drawing incorporato; non è necessaria una licenza Aspose.Drawing separata.

In modalità di valutazione, l'output raster (PNG, JPEG, BMP, TIFF) di `Aspose.TeX.Drawing` riporta due filigrane: la filigrana di valutazione di Aspose.TeX e una filigrana «Evaluation only Aspose.Drawing». Entrambe scompaiono quando si applica la licenza di Aspose.TeX.

## Limitazioni note {#known-limitations}

`Aspose.TeX.Drawing` non è ancora in grado di salvare file TIFF multipagina. Se si imposta `TiffSaveOptions.Multipage` su `true`, il file TIFF risultante contiene solo la prima pagina del documento e non viene generata alcuna eccezione. Per ottenere tutte le pagine, impostare `Multipage` su `false` per avere un'immagine TIFF separata per ogni pagina, oppure convertire il documento in PDF o XPS.

## Risoluzione dei problemi {#troubleshooting}

| Errore | Causa | Soluzione |
|---|---|---|
| `PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.` | L'applicazione usa il pacchetto `Aspose.TeX` su Linux o macOS. | Usare il pacchetto `Aspose.TeX.Drawing`. |
| `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.…' from assembly 'Aspose.TeX'` | Il progetto fa riferimento sia ad `Aspose.TeX` sia ad `Aspose.TeX.Drawing`. | Rimuovere il pacchetto `Aspose.TeX`. |
| `CultureNotFoundException: … en-US is an invalid culture identifier.` durante il salvataggio in XPS o SVG | .NET viene eseguito in modalità invariante di globalizzazione. | Installare ICU e disattivare la modalità invariante, vedere [Modalità invariante di globalizzazione](#globalization-invariant-mode). |
| `error CS0104: 'Color' is an ambiguous reference between 'System.Drawing.Color' and 'Aspose.TeX.Drawing.Color'` | Il codice importa sia `System.Drawing` sia `Aspose.TeX.Drawing`. | Importare i tipi di `Aspose.TeX.Drawing` con alias, vedere [Modalità di smussatura e interpolazione](#smoothing-and-interpolation-modes). |
| Un file TIFF multipagina contiene una sola pagina. | Limitazione nota di `Aspose.TeX.Drawing`. | Vedere [Limitazioni note](#known-limitations). |

## Elenco di controllo per la distribuzione su Linux e nei container {#checklist-for-linux-and-container-deployment}

- [ ] Fare riferimento ad `Aspose.TeX.Drawing` invece che ad `Aspose.TeX`, e a uno solo dei due pacchetti.
- [ ] Se il codice importa sia `System.Drawing` sia `Aspose.TeX.Drawing`, importare i tipi di `Aspose.TeX.Drawing` con alias.
- [ ] Se serve l'output in XPS o SVG, verificare che ICU sia disponibile e che la modalità invariante sia disattivata: installare `icu-libs` su Alpine, usare la variante `-chiseled-extra` delle immagini chiseled e non impostare `InvariantGlobalization` nel progetto.
- [ ] Scrivere i file di output in una posizione scrivibile, in particolare nelle immagini chiseled, che eseguono l'applicazione senza privilegi di root.
- [ ] Applicare la licenza una sola volta all'avvio dell'applicazione, prima della prima conversione.
- [ ] Se servono tutte le pagine in formato TIFF, impostare `TiffSaveOptions.Multipage` su `false` oppure usare l'output in PDF o XPS.
