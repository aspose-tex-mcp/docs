---
translation: true
template: /templates/_template-net.md
title: Linux, macOS et Docker | Aspose.TeX pour .NET
linktitle: Linux, macOS et Docker
weight: 55
url: /net/linux-and-containers/
description: Exécuter Aspose.TeX pour .NET sous Linux, macOS et dans des conteneurs Docker avec le package Aspose.TeX.Drawing. Choix du package, migration depuis Aspose.TeX, Dockerfiles et limitations connues.
keywords: aspose.tex linux, aspose.tex docker, aspose.tex macos, aspose.tex.drawing, latex en pdf linux .NET, latex en png docker .NET, System.Drawing.Common is not supported on this platform
lastmod: "2026-11-02"
---

{{<section overview>}}

## Choisir le bon package {#choose-the-right-package}

Aspose.TeX pour .NET est publié sous forme de deux packages NuGet ayant la même API et le même numéro de version :

| Package | Moteur graphique | Windows | Linux, macOS | Frameworks cibles |
|---|---|---|---|---|
| [`Aspose.TeX`](https://www.nuget.org/packages/Aspose.TeX) | `System.Drawing.Common` (GDI+) | Oui | Non | .NET Framework 4.0, .NET Standard 2.0, .NET 6.0, .NET 7.0 |
| **[`Aspose.TeX.Drawing`](https://www.nuget.org/packages/Aspose.TeX.Drawing)** | Aspose.Drawing (managé, intégré au package) | **Oui** | **Oui** | .NET Standard 2.0, .NET 7.0 |

À partir de .NET 6, Microsoft ne prend en charge `System.Drawing.Common` que sous Windows. Si votre application utilise le package `Aspose.TeX` sous Linux ou macOS, elle échoue dès qu'elle effectue un rendu :

```
System.PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.
```

Utilisez `Aspose.TeX.Drawing` lorsque votre application s'exécute sous Linux, macOS, dans des conteneurs Docker ou dans d'autres environnements que Windows. Le package fonctionne aussi sous Windows ; vous pouvez donc l'utiliser partout si vous générez une même application pour plusieurs plateformes.

`Aspose.TeX.Drawing` ne dépend ni de `System.Drawing.Common` ni de `libgdiplus`. Le moteur graphique Aspose.Drawing est intégré à `Aspose.TeX.dll` : le package n'ajoute donc qu'un seul assembly à votre application. La version pour .NET 7.0 est utilisée par .NET 7, 8, 9, 10 et versions ultérieures ; la version pour .NET Standard 2.0 par .NET Framework 4.7.2 et versions ultérieures.

## Installer le package {#install-the-package}

Exécutez l'une des commandes suivantes dans le dossier de votre projet :

```bash
dotnet add package Aspose.TeX.Drawing
```

```powershell
Install-Package Aspose.TeX.Drawing
```

Consultez [Installation](/tex/{{lang.url-fragment}}net/installation/) pour d'autres façons de référencer le package.

{{% alert color="primary" %}}
Ne référencez qu'un seul des deux packages. Si un projet référence à la fois `Aspose.TeX` et `Aspose.TeX.Drawing`, il se compile sans avertissement, mais un seul `Aspose.TeX.dll` est copié dans le dossier de sortie, et l'application échoue à l'exécution, par exemple avec `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.SizeF' from assembly 'Aspose.TeX'`. Lorsque vous passez à `Aspose.TeX.Drawing`, supprimez d'abord le package `Aspose.TeX` :

```bash
dotnet remove package Aspose.TeX
dotnet add package Aspose.TeX.Drawing
```
{{% /alert %}}

## Passer d'Aspose.TeX à Aspose.TeX.Drawing {#switch-from-asposetex-to-asposetexdrawing}

Les espaces de noms, les classes et les membres sont identiques dans les deux packages ; la plupart du code ne nécessite donc aucune modification après le remplacement du package.

### Couleurs et tailles {#colors-and-sizes}

Les options et les résultats de rendu utilisent des couleurs et des tailles, par exemple `MathRendererOptions.TextColor`, `FigureRendererOptions.BackgroundColor` et la valeur renvoyée par `MathRenderer.Render`. Dans `Aspose.TeX.Drawing`, ces membres ont les types `Aspose.TeX.Drawing.Color` et `Aspose.TeX.Drawing.SizeF`. Les deux types se convertissent implicitement vers et depuis `System.Drawing.Color` et `System.Drawing.SizeF`. Ce sont des types .NET standard, disponibles sur toutes les plateformes sans `System.Drawing.Common` ; un code comme le suivant se compile et s'exécute donc avec l'un ou l'autre package :

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

### Modes de lissage et d'interpolation {#smoothing-and-interpolation-modes}

La seule différence concerne les propriétés `SmoothingMode` et `InterpolationMode` des options d'enregistrement d'images (`PngSaveOptions`, `JpegSaveOptions`, `BmpSaveOptions`, `TiffSaveOptions`). Dans le package `Aspose.TeX`, elles utilisent des énumérations de l'espace de noms `System.Drawing.Drawing2D`, qui appartient à `System.Drawing.Common` (le compilateur les signale comme réservées à Windows avec l'avertissement CA1416). Dans `Aspose.TeX.Drawing`, elles utilisent les énumérations `Aspose.TeX.Drawing.SmoothingMode` et `Aspose.TeX.Drawing.InterpolationMode`, qui ont les mêmes membres. Remplacez la directive `using` et conservez le reste du code.

Avec `Aspose.TeX` :

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

Avec `Aspose.TeX.Drawing` :

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

Importez ces deux types avec des alias, comme ci-dessus, plutôt qu'avec `using Aspose.TeX.Drawing;`. L'espace de noms `Aspose.TeX.Drawing` contient aussi `Color` et `SizeF` ; l'importer en même temps que `System.Drawing` provoque l'erreur de compilation `CS0104: 'Color' is an ambiguous reference`.

### Types de l'espace de noms Aspose.TeX.Drawing {#types-of-the-asposetexdrawing-namespace}

L'espace de noms `Aspose.TeX.Drawing` n'existe que dans le package `Aspose.TeX.Drawing` :

| Type | Utilisé par | Compatibilité avec System.Drawing |
|---|---|---|
| `Color` | `MathRendererOptions.TextColor`, `FigureRendererOptions.BackgroundColor` | Conversion implicite vers et depuis `System.Drawing.Color` |
| `SizeF` | Valeur renvoyée par `MathRenderer.Render` et `FigureRenderer.Render` ; `Size` de `MathRendererPluginResult` et `FigureRendererPluginResult` | Conversion implicite vers et depuis `System.Drawing.SizeF` |
| `SmoothingMode` | `ImageSaveOptions.SmoothingMode` | Mêmes membres et valeurs que `System.Drawing.Drawing2D.SmoothingMode` |
| `InterpolationMode` | `ImageSaveOptions.InterpolationMode` | Mêmes membres et valeurs que `System.Drawing.Drawing2D.InterpolationMode` |

## Exécuter dans Docker {#run-in-docker}

Aspose.TeX compose les documents avec ses propres polices TeX intégrées, et `Aspose.TeX.Drawing` contient son moteur graphique. Votre conteneur n'a besoin ni de `libgdiplus`, ni de `fontconfig`, ni de polices installées. Le seul composant système qui compte est ICU, nécessaire pour la sortie XPS et SVG (voir [Mode invariant de globalisation](#globalization-invariant-mode)).

Les images .NET officielles basées sur Debian et Ubuntu fonctionnent sans configuration supplémentaire :

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

Remplacez `MyApp.dll` par le nom de votre application. Pour les applications ASP.NET Core, utilisez `mcr.microsoft.com/dotnet/aspnet` au lieu de `mcr.microsoft.com/dotnet/runtime` ; les mêmes règles s'appliquent.

Le tableau suivant indique ce dont chaque type d'image a besoin :

| Image de base | Configuration supplémentaire |
|---|---|
| `runtime:8.0`, `aspnet:8.0` (Debian) | Aucune |
| `runtime:8.0-noble`, `aspnet:8.0-noble` (Ubuntu) | Aucune |
| `runtime:8.0-alpine`, `aspnet:8.0-alpine` | Installer ICU et désactiver le mode invariant (voir ci-dessous) |
| `runtime:8.0-noble-chiseled`, `aspnet:8.0-noble-chiseled` | Utiliser la variante `-noble-chiseled-extra`, qui inclut ICU |
| `runtime:8.0-noble-chiseled-extra`, `aspnet:8.0-noble-chiseled-extra` | Aucune |

Il en va de même pour les images .NET 9 et .NET 10. Les images `linux/amd64` et `linux/arm64` sont prises en charge.

### Alpine {#alpine}

Les images Alpine exécutent .NET en mode invariant de globalisation et ne contiennent pas ICU. Installez le package `icu-libs` et désactivez le mode invariant :

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

### Images chiseled (distroless) {#chiseled-distroless-images}

Les images chiseled ne contiennent ni shell ni gestionnaire de packages ; vous ne pouvez donc pas y installer ICU. Utilisez la variante `-chiseled-extra`, qui inclut déjà ICU :

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

Les images chiseled exécutent l'application sous un utilisateur sans privilèges root. Écrivez les fichiers de sortie dans un emplacement accessible en écriture, comme un volume monté ou `/tmp`, plutôt que dans le dossier de l'application.

## Mode invariant de globalisation {#globalization-invariant-mode}

La sortie XPS et SVG nécessite ICU. Si .NET s'exécute en [mode invariant de globalisation](https://aka.ms/GlobalizationInvariantMode), la conversion en XPS ou en SVG échoue avec une exception comme celle-ci :

```
System.Globalization.CultureNotFoundException: Only the invariant culture is supported in globalization-invariant mode. See https://aka.ms/GlobalizationInvariantMode for more information. (Parameter 'name')
en-US is an invalid culture identifier.
```

Le mode invariant est activé par défaut dans les images Alpine et chiseled, ainsi que par la propriété de projet `<InvariantGlobalization>true</InvariantGlobalization>`. La sortie PDF, PNG, JPEG, BMP et TIFF fonctionne en mode invariant. Si vous avez besoin d'une sortie XPS ou SVG, installez ICU comme indiqué dans [Exécuter dans Docker](#run-in-docker) et n'activez pas le mode invariant dans le projet.

## Licence {#licensing}

`Aspose.TeX.Drawing` utilise la même licence qu'`Aspose.TeX`, et vous l'appliquez de la même manière (voir [Licence](/tex/{{lang.url-fragment}}net/licensing/)). La licence couvre aussi le moteur graphique Aspose.Drawing intégré ; aucune licence Aspose.Drawing distincte n'est nécessaire.

En mode d'évaluation, la sortie raster (PNG, JPEG, BMP, TIFF) d'`Aspose.TeX.Drawing` porte deux filigranes : le filigrane d'évaluation d'Aspose.TeX et un filigrane « Evaluation only Aspose.Drawing ». Les deux disparaissent dès que vous appliquez la licence Aspose.TeX.

## Limitations connues {#known-limitations}

`Aspose.TeX.Drawing` ne peut pas encore enregistrer de fichiers TIFF multipages. Si vous définissez `TiffSaveOptions.Multipage` sur `true`, le fichier TIFF obtenu ne contient que la première page du document, et aucune exception n'est levée. Pour obtenir toutes les pages, définissez `Multipage` sur `false` afin d'obtenir une image TIFF distincte par page, ou convertissez le document en PDF ou en XPS.

## Dépannage {#troubleshooting}

| Erreur | Cause | Solution |
|---|---|---|
| `PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.` | L'application utilise le package `Aspose.TeX` sous Linux ou macOS. | Utilisez le package `Aspose.TeX.Drawing`. |
| `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.…' from assembly 'Aspose.TeX'` | Le projet référence à la fois `Aspose.TeX` et `Aspose.TeX.Drawing`. | Supprimez le package `Aspose.TeX`. |
| `CultureNotFoundException: … en-US is an invalid culture identifier.` lors de l'enregistrement en XPS ou en SVG | .NET s'exécute en mode invariant de globalisation. | Installez ICU et désactivez le mode invariant, voir [Mode invariant de globalisation](#globalization-invariant-mode). |
| `error CS0104: 'Color' is an ambiguous reference between 'System.Drawing.Color' and 'Aspose.TeX.Drawing.Color'` | Le code importe à la fois `System.Drawing` et `Aspose.TeX.Drawing`. | Importez les types d'`Aspose.TeX.Drawing` avec des alias, voir [Modes de lissage et d'interpolation](#smoothing-and-interpolation-modes). |
| Un fichier TIFF multipage ne contient qu'une seule page. | Limitation connue d'`Aspose.TeX.Drawing`. | Voir [Limitations connues](#known-limitations). |

## Liste de contrôle pour le déploiement sous Linux et dans des conteneurs {#checklist-for-linux-and-container-deployment}

- [ ] Référencez `Aspose.TeX.Drawing` au lieu d'`Aspose.TeX`, et un seul des deux packages.
- [ ] Si votre code importe à la fois `System.Drawing` et `Aspose.TeX.Drawing`, importez les types d'`Aspose.TeX.Drawing` avec des alias.
- [ ] Si vous avez besoin d'une sortie XPS ou SVG, assurez-vous qu'ICU est disponible et que le mode invariant est désactivé : installez `icu-libs` sous Alpine, utilisez la variante `-chiseled-extra` des images chiseled et ne définissez pas `InvariantGlobalization` dans le projet.
- [ ] Écrivez les fichiers de sortie dans un emplacement accessible en écriture, en particulier dans les images chiseled, qui exécutent l'application sans privilèges root.
- [ ] Appliquez la licence une seule fois au démarrage de l'application, avant la première conversion.
- [ ] Si vous avez besoin de toutes les pages au format TIFF, définissez `TiffSaveOptions.Multipage` sur `false` ou utilisez la sortie PDF ou XPS.
