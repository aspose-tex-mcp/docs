---
translation: true
template: /templates/_template-net.md
title: Configuration système requise | Aspose.TeX pour .NET
linktitle: Configuration système requise
weight: 50
url: /net/system-requirements/
description: Systèmes d'exploitation, versions de .NET et environnements de développement pris en charge par les packages NuGet Aspose.TeX et Aspose.TeX.Drawing.
lastmod: "2026-11-02"
---

{{<section overview>}}

Aspose.TeX pour .NET est disponible sous forme de deux packages NuGet ayant la même API. Leur configuration requise diffère, car ils utilisent des moteurs graphiques différents.

| | `Aspose.TeX` | `Aspose.TeX.Drawing` |
|---|---|---|
| Moteur graphique | `System.Drawing.Common` (GDI+) | Aspose.Drawing, intégré au package |
| Systèmes d'exploitation | Windows | Windows, Linux, macOS |
| Frameworks cibles du package | .NET Framework 4.0, .NET Standard 2.0, .NET 6.0, .NET 7.0 | .NET Standard 2.0, .NET 7.0 |

## Systèmes d'exploitation pris en charge

### Aspose.TeX

* Éditions bureau et serveur de Microsoft Windows (x64, x86)
* Microsoft Azure (services basés sur Windows)

À partir de .NET 6, Microsoft ne prend en charge `System.Drawing.Common`, dont dépend ce package, que sous Windows.

### Aspose.TeX.Drawing

* Éditions bureau et serveur de Microsoft Windows (x64, x86)
* Linux (x64, Arm64), y compris les conteneurs Docker
* macOS

Aucune bibliothèque native telle que `libgdiplus` ou `fontconfig` ni aucune police installée n'est nécessaire. Sous Linux, la sortie XPS et SVG nécessite ICU, absente de certaines images de conteneur. Voir [Linux, macOS et Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/).

## Versions de .NET prises en charge

### Aspose.TeX

* .NET Framework 4.0 ou version ultérieure
* .NET 6 ou version ultérieure
* Toute autre implémentation de .NET Standard 2.0, comme .NET Core 2.0 ou version ultérieure

### Aspose.TeX.Drawing

* .NET 7 ou version ultérieure, y compris .NET 8, .NET 9 et .NET 10
* .NET Framework 4.7.2 ou version ultérieure (via .NET Standard 2.0)
* Toute autre implémentation de .NET Standard 2.0, comme .NET Core 2.0 ou version ultérieure

## Environnements de développement

Vous pouvez utiliser Aspose.TeX pour .NET dans tout environnement de développement ciblant la plateforme .NET, comme Microsoft Visual Studio, Visual Studio Code ou JetBrains Rider, ainsi qu'avec la CLI .NET.
