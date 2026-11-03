---
translation: true
template: /templates/_template-net.md
title: Linux, macOS y Docker | Aspose.TeX para .NET
linktitle: Linux, macOS y Docker
weight: 55
url: /net/linux-and-containers/
description: Ejecute Aspose.TeX para .NET en Linux, macOS y contenedores Docker con el paquete Aspose.TeX.Drawing. Elección del paquete, migración desde Aspose.TeX, Dockerfiles y limitaciones conocidas.
keywords: aspose.tex linux, aspose.tex docker, aspose.tex macos, aspose.tex.drawing, latex a pdf linux .NET, latex a png docker .NET, System.Drawing.Common is not supported on this platform
lastmod: "2026-11-02"
---

{{<section overview>}}

## Elegir el paquete adecuado {#choose-the-right-package}

Aspose.TeX para .NET se publica como dos paquetes NuGet con la misma API y el mismo número de versión:

| Paquete | Backend gráfico | Windows | Linux, macOS | Marcos de destino |
|---|---|---|---|---|
| [`Aspose.TeX`](https://www.nuget.org/packages/Aspose.TeX) | `System.Drawing.Common` (GDI+) | Sí | No | .NET Framework 4.0, .NET Standard 2.0, .NET 6.0, .NET 7.0 |
| **[`Aspose.TeX.Drawing`](https://www.nuget.org/packages/Aspose.TeX.Drawing)** | Aspose.Drawing (administrado, integrado en el paquete) | **Sí** | **Sí** | .NET Standard 2.0, .NET 7.0 |

A partir de .NET 6, Microsoft admite `System.Drawing.Common` solo en Windows. Si su aplicación usa el paquete `Aspose.TeX` en Linux o macOS, falla en cuanto renderiza algo:

```
System.PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.
```

Use `Aspose.TeX.Drawing` cuando su aplicación se ejecute en Linux, macOS, contenedores Docker u otros entornos distintos de Windows. El paquete también funciona en Windows, así que puede usarlo en todas partes si compila una aplicación para varias plataformas.

`Aspose.TeX.Drawing` no depende de `System.Drawing.Common` ni de `libgdiplus`. El backend gráfico Aspose.Drawing está integrado en `Aspose.TeX.dll`, por lo que el paquete aporta un único ensamblado a su aplicación. La compilación para .NET 7.0 la usan .NET 7, 8, 9, 10 y versiones posteriores; la compilación para .NET Standard 2.0, .NET Framework 4.7.2 y versiones posteriores.

## Instalar el paquete {#install-the-package}

Ejecute uno de los siguientes comandos en la carpeta de su proyecto:

```bash
dotnet add package Aspose.TeX.Drawing
```

```powershell
Install-Package Aspose.TeX.Drawing
```

Consulte [Instalación](/tex/{{lang.url-fragment}}net/installation/) para conocer otras formas de referenciar el paquete.

{{% alert color="primary" %}}
Referencie solo uno de los dos paquetes. Si un proyecto referencia tanto `Aspose.TeX` como `Aspose.TeX.Drawing`, se compila sin advertencias, pero solo se copia un `Aspose.TeX.dll` a la carpeta de salida y la aplicación falla en tiempo de ejecución, por ejemplo con `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.SizeF' from assembly 'Aspose.TeX'`. Al cambiar a `Aspose.TeX.Drawing`, quite primero el paquete `Aspose.TeX`:

```bash
dotnet remove package Aspose.TeX
dotnet add package Aspose.TeX.Drawing
```
{{% /alert %}}

## Cambiar de Aspose.TeX a Aspose.TeX.Drawing {#switch-from-asposetex-to-asposetexdrawing}

Los espacios de nombres, las clases y los miembros son los mismos en ambos paquetes, por lo que la mayor parte del código no necesita cambios tras sustituir el paquete.

### Colores y tamaños {#colors-and-sizes}

Las opciones y los resultados de renderizado usan colores y tamaños, por ejemplo `MathRendererOptions.TextColor`, `FigureRendererOptions.BackgroundColor` y el valor devuelto por `MathRenderer.Render`. En `Aspose.TeX.Drawing`, estos miembros tienen los tipos `Aspose.TeX.Drawing.Color` y `Aspose.TeX.Drawing.SizeF`. Ambos tipos se convierten implícitamente a `System.Drawing.Color` y `System.Drawing.SizeF` y viceversa. Son tipos estándar de .NET disponibles en todas las plataformas sin `System.Drawing.Common`, así que un código como el siguiente se compila y se ejecuta con cualquiera de los dos paquetes:

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

### Modos de suavizado e interpolación {#smoothing-and-interpolation-modes}

El único cambio afecta a las propiedades `SmoothingMode` e `InterpolationMode` de las opciones de guardado de imágenes (`PngSaveOptions`, `JpegSaveOptions`, `BmpSaveOptions`, `TiffSaveOptions`). En el paquete `Aspose.TeX`, usan enumeraciones del espacio de nombres `System.Drawing.Drawing2D`, que pertenece a `System.Drawing.Common` (el compilador las marca como exclusivas de Windows con la advertencia CA1416). En `Aspose.TeX.Drawing`, usan las enumeraciones `Aspose.TeX.Drawing.SmoothingMode` y `Aspose.TeX.Drawing.InterpolationMode`, que tienen los mismos miembros. Sustituya la directiva `using` y mantenga el resto del código.

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

Importe estos dos tipos con alias, como se muestra arriba, y no con `using Aspose.TeX.Drawing;`. El espacio de nombres `Aspose.TeX.Drawing` también contiene `Color` y `SizeF`, por lo que importarlo junto con `System.Drawing` provoca el error de compilación `CS0104: 'Color' is an ambiguous reference`.

### Tipos del espacio de nombres Aspose.TeX.Drawing {#types-of-the-asposetexdrawing-namespace}

El espacio de nombres `Aspose.TeX.Drawing` solo existe en el paquete `Aspose.TeX.Drawing`:

| Tipo | Usado por | Compatibilidad con System.Drawing |
|---|---|---|
| `Color` | `MathRendererOptions.TextColor`, `FigureRendererOptions.BackgroundColor` | Conversión implícita a `System.Drawing.Color` y viceversa |
| `SizeF` | Valor devuelto por `MathRenderer.Render` y `FigureRenderer.Render`; `Size` de `MathRendererPluginResult` y `FigureRendererPluginResult` | Conversión implícita a `System.Drawing.SizeF` y viceversa |
| `SmoothingMode` | `ImageSaveOptions.SmoothingMode` | Mismos miembros y valores que `System.Drawing.Drawing2D.SmoothingMode` |
| `InterpolationMode` | `ImageSaveOptions.InterpolationMode` | Mismos miembros y valores que `System.Drawing.Drawing2D.InterpolationMode` |

## Ejecutar en Docker {#run-in-docker}

Aspose.TeX compone los documentos con sus propias fuentes TeX integradas, y `Aspose.TeX.Drawing` contiene su backend gráfico. Su contenedor no necesita `libgdiplus`, ni `fontconfig`, ni fuentes instaladas. El único componente del sistema que importa es ICU, necesario para la salida en XPS y SVG (consulte [Modo invariable de globalización](#globalization-invariant-mode)).

Las imágenes oficiales de .NET basadas en Debian y Ubuntu funcionan sin configuración adicional:

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

Sustituya `MyApp.dll` por el nombre de su aplicación. Para aplicaciones ASP.NET Core, use `mcr.microsoft.com/dotnet/aspnet` en lugar de `mcr.microsoft.com/dotnet/runtime`; se aplican las mismas reglas.

La siguiente tabla indica qué necesita cada tipo de imagen:

| Imagen base | Configuración adicional |
|---|---|
| `runtime:8.0`, `aspnet:8.0` (Debian) | Ninguna |
| `runtime:8.0-noble`, `aspnet:8.0-noble` (Ubuntu) | Ninguna |
| `runtime:8.0-alpine`, `aspnet:8.0-alpine` | Instalar ICU y desactivar el modo invariable (ver más abajo) |
| `runtime:8.0-noble-chiseled`, `aspnet:8.0-noble-chiseled` | Usar la variante `-noble-chiseled-extra`, que incluye ICU |
| `runtime:8.0-noble-chiseled-extra`, `aspnet:8.0-noble-chiseled-extra` | Ninguna |

Lo mismo se aplica a las imágenes de .NET 9 y .NET 10. Se admiten imágenes `linux/amd64` y `linux/arm64`.

### Alpine {#alpine}

Las imágenes Alpine ejecutan .NET en modo invariable de globalización y no contienen ICU. Instale el paquete `icu-libs` y desactive el modo invariable:

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

### Imágenes chiseled (distroless) {#chiseled-distroless-images}

Las imágenes chiseled no contienen shell ni gestor de paquetes, por lo que no es posible instalar ICU en ellas. Use la variante `-chiseled-extra`, que ya incluye ICU:

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

Las imágenes chiseled ejecutan la aplicación como un usuario sin privilegios de root. Escriba los archivos de salida en una ubicación con permisos de escritura, como un volumen montado o `/tmp`, y no en la carpeta de la aplicación.

## Modo invariable de globalización {#globalization-invariant-mode}

La salida en XPS y SVG requiere ICU. Si .NET se ejecuta en [modo invariable de globalización](https://aka.ms/GlobalizationInvariantMode), la conversión a XPS o SVG falla con una excepción como esta:

```
System.Globalization.CultureNotFoundException: Only the invariant culture is supported in globalization-invariant mode. See https://aka.ms/GlobalizationInvariantMode for more information. (Parameter 'name')
en-US is an invalid culture identifier.
```

El modo invariable está activado de forma predeterminada en las imágenes Alpine y chiseled, y también lo activa la propiedad de proyecto `<InvariantGlobalization>true</InvariantGlobalization>`. La salida en PDF, PNG, JPEG, BMP y TIFF funciona en modo invariable. Si necesita salida en XPS o SVG, instale ICU como se muestra en [Ejecutar en Docker](#run-in-docker) y no active el modo invariable en el proyecto.

## Licencias {#licensing}

`Aspose.TeX.Drawing` usa la misma licencia que `Aspose.TeX`, y se aplica de la misma manera (consulte [Licencias](/tex/{{lang.url-fragment}}net/licensing/)). La licencia también cubre el backend gráfico Aspose.Drawing integrado; no necesita una licencia de Aspose.Drawing aparte.

En modo de evaluación, la salida rasterizada (PNG, JPEG, BMP, TIFF) de `Aspose.TeX.Drawing` lleva dos marcas de agua: la marca de agua de evaluación de Aspose.TeX y una marca de agua «Evaluation only Aspose.Drawing». Ambas desaparecen al aplicar la licencia de Aspose.TeX.

## Limitaciones conocidas {#known-limitations}

`Aspose.TeX.Drawing` todavía no puede guardar archivos TIFF de varias páginas. Si establece `TiffSaveOptions.Multipage` en `true`, el archivo TIFF resultante contiene solo la primera página del documento y no se produce ninguna excepción. Para obtener todas las páginas, establezca `Multipage` en `false` para obtener una imagen TIFF independiente por página, o convierta el documento a PDF o XPS.

## Solución de problemas {#troubleshooting}

| Error | Causa | Solución |
|---|---|---|
| `PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.` | La aplicación usa el paquete `Aspose.TeX` en Linux o macOS. | Use el paquete `Aspose.TeX.Drawing`. |
| `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.…' from assembly 'Aspose.TeX'` | El proyecto referencia tanto `Aspose.TeX` como `Aspose.TeX.Drawing`. | Quite el paquete `Aspose.TeX`. |
| `CultureNotFoundException: … en-US is an invalid culture identifier.` al guardar en XPS o SVG | .NET se ejecuta en modo invariable de globalización. | Instale ICU y desactive el modo invariable; consulte [Modo invariable de globalización](#globalization-invariant-mode). |
| `error CS0104: 'Color' is an ambiguous reference between 'System.Drawing.Color' and 'Aspose.TeX.Drawing.Color'` | El código importa tanto `System.Drawing` como `Aspose.TeX.Drawing`. | Importe los tipos de `Aspose.TeX.Drawing` con alias; consulte [Modos de suavizado e interpolación](#smoothing-and-interpolation-modes). |
| Un archivo TIFF de varias páginas contiene solo una página. | Limitación conocida de `Aspose.TeX.Drawing`. | Consulte [Limitaciones conocidas](#known-limitations). |

## Lista de comprobación para la implementación en Linux y contenedores {#checklist-for-linux-and-container-deployment}

- [ ] Referencie `Aspose.TeX.Drawing` en lugar de `Aspose.TeX`, y solo uno de los dos paquetes.
- [ ] Si su código importa tanto `System.Drawing` como `Aspose.TeX.Drawing`, importe los tipos de `Aspose.TeX.Drawing` con alias.
- [ ] Si necesita salida en XPS o SVG, asegúrese de que ICU esté disponible y el modo invariable desactivado: instale `icu-libs` en Alpine, use la variante `-chiseled-extra` de las imágenes chiseled y no establezca `InvariantGlobalization` en el proyecto.
- [ ] Escriba los archivos de salida en una ubicación con permisos de escritura, especialmente en las imágenes chiseled, que ejecutan la aplicación sin privilegios de root.
- [ ] Aplique la licencia una sola vez al iniciar la aplicación, antes de la primera conversión.
- [ ] Si necesita todas las páginas en formato TIFF, establezca `TiffSaveOptions.Multipage` en `false` o use la salida en PDF o XPS.
