---
translation: true
template: /templates/_template-net.md
title: Convertisseurs Aspose.TeX pour .NET – FAQ
linktitle: FAQ
type: docs
weight: 90
url: /net/conversion/faq/
description: Questions fréquentes sur la conversion de fichiers TeX et LaTeX avec Aspose.TeX pour .NET, notamment les formats pris en charge, le code de conversion, la sortie vers des flux, les options d'image, les packages, le mode d'évaluation et la configuration requise.
keywords: Aspose.TeX, .NET, FAQ, conversion LaTeX, LaTeX en PDF, LaTeX en XPS, LaTeX en SVG, LaTeX en PNG, TeXJob, licence, Linux
lastmod: "2026-11-02"
---

{{<section overview>}}

<br><br>

**Q : Quels formats d'entrée et de sortie Aspose.TeX pour .NET prend-il en charge ?**

**R :** Aspose.TeX compose des documents TeX et LaTeX. Le fichier d'entrée principal peut provenir d'un fichier, d'un flux ou d'un terminal ; les fichiers qu'il inclut peuvent provenir d'un dossier ou d'une archive ZIP. Des API distinctes effectuent le rendu d'une seule formule mathématique LaTeX ou d'un fragment LaTeX. Les formats de sortie sont PDF, XPS, SVG, PNG, JPEG, BMP et TIFF. Voir [Formats de fichiers pris en charge](/tex/{{lang.url-fragment}}net/supported-file-formats/).
<br><br>

**Q : Aspose.TeX peut-il convertir du LaTeX en Word (DOCX) ou en HTML ?**

**R :** Non. Aspose.TeX produit uniquement du PDF, du XPS, du SVG et des images raster. Si vous avez besoin d'un autre format, convertissez la sortie PDF avec une bibliothèque qui le prend en charge.
<br><br>

**Q : Comment convertir un fichier LaTeX en PDF en C# ?**

**R :** Créez `TeXOptions` pour le format ObjectLaTeX, définissez le répertoire de sortie et `PdfSaveOptions`, puis exécutez un `TeXJob` avec un `PdfDevice` :

{{< gist "aspose-com-gists" "507170b996a1d0c39bb4374e888b3205" "Example-ConvertLaTeXToPDF-Simplest.cs" >}}

Le résultat est écrit dans le répertoire de travail de sortie sous le nom de la tâche. Voir [LaTeX en PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/).
<br><br>

**Q : Comment choisir le format de sortie ?**

**R :** Définissez `TeXOptions.SaveOptions` et transmettez le périphérique correspondant à `TeXJob` :

| Format | Options d'enregistrement | Périphérique |
|---|---|---|
| PDF | `PdfSaveOptions` | `PdfDevice` |
| XPS | `XpsSaveOptions` | `XpsDevice` |
| SVG | `SvgSaveOptions` | `SvgDevice` |
| PNG, JPEG, BMP, TIFF | `PngSaveOptions`, `JpegSaveOptions`, `BmpSaveOptions`, `TiffSaveOptions` | `ImageDevice` |

Voir [LaTeX vers XPS](/tex/{{lang.url-fragment}}net/latex-to-xps/) et [LaTeX en image](/tex/{{lang.url-fragment}}net/latex-to-image/).
<br><br>

**Q : Puis-je obtenir le résultat en mémoire plutôt que dans un fichier ?**

**R :** Oui. `PdfDevice` et `XpsDevice` ont des constructeurs qui acceptent un `Stream` dans lequel le document est écrit. `ImageDevice` conserve les pages rendues dans sa propriété `Result` sous forme de tableau de tableaux d'octets, un par page. Pour lire l'entrée principale depuis un flux, transmettez le flux au constructeur de `TeXJob`. Voir [LaTeX en PDF](/tex/{{lang.url-fragment}}net/latex-to-pdf/#an-alternative-way-to-write-the-main-output-pdf-file) et [Autres façons de fournir le fichier d'entrée TeX principal](/tex/{{lang.url-fragment}}net/other-ways-of-main-input/).
<br><br>

**Q : Comment contrôler la résolution et la qualité des images ?**

**R :** Utilisez les propriétés des options d'enregistrement d'images :

- `Resolution` — résolution de l'image en DPI.
- `SmoothingMode` et `InterpolationMode` — qualité du rendu.
- `TiffSaveOptions.Compression` et `TiffSaveOptions.Multipage` — compression TIFF et enregistrement de toutes les pages dans un seul fichier (le TIFF multipage n'est pas encore pris en charge par le package `Aspose.TeX.Drawing`).

Par exemple, `new PngSaveOptions { Resolution = 300 }` produit des images PNG à 300 DPI. Voir [LaTeX en image](/tex/{{lang.url-fragment}}net/latex-to-image/).
<br><br>

**Q : Comment savoir si la conversion a réussi ?**

**R :** `TeXJob.Run()` renvoie une valeur `TeXJobResult` : `Spotless`, `WarningIssued`, `ErrorMessageIssued` ou `FatalErrorStop`. Les détails sont écrits dans le fichier de transcription (`.log`) du répertoire de sortie et dans le terminal de sortie. Voir [Interface de sortie d'Aspose.TeX](/tex/{{lang.url-fragment}}net/aspose-tex-output/).
<br><br>

**Q : Ai-je besoin d'une installation LaTeX (par exemple MiKTeX) sur le serveur ?**

**R :** Non. Aspose.TeX est une bibliothèque .NET autonome dotée de son propre moteur TeX, de son format LaTeX et de ses polices. Elle ne nécessite aucune distribution TeX externe.
<br><br>

**Q : Quels packages LaTeX puis-je utiliser ?**

**R :** Aspose.TeX inclut un ensemble de packages LaTeX intégrés ; voir [Packages LaTeX intégrés](/tex/{{lang.url-fragment}}net/embedded-packages/). Pour utiliser d'autres packages, placez leurs fichiers dans un dossier ou une archive ZIP et indiquez-le dans `TeXOptions.RequiredInputDirectory` ; voir [Packages LaTeX externes](/tex/{{lang.url-fragment}}net/external-latex-packages/).
<br><br>

**Q : Puis-je effectuer le rendu d'une seule formule ou d'un fragment LaTeX au lieu d'un document entier ?**

**R :** Oui. Utilisez `PngMathRenderer` ou `SvgMathRenderer` pour les formules mathématiques et `PngFigureRenderer` ou `SvgFigureRenderer` pour les fragments LaTeX arbitraires. Ils renvoient la taille de l'image rendue. Voir [Rendu des formules mathématiques LaTeX](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) et [Rendu des figures LaTeX](/tex/{{lang.url-fragment}}net/latex-figure-rendering/).
<br><br>

**Q : Quelle est la configuration requise pour l'exécution ?**

**R :**

- Package `Aspose.TeX` : Windows (x64/x86) ; .NET Framework 4.0 ou ultérieur, .NET Standard 2.0, .NET 6 ou ultérieur.
- Package `Aspose.TeX.Drawing` : Windows, Linux et macOS (x64/Arm64) ; .NET Framework 4.7.2 ou ultérieur, .NET 7 ou ultérieur.
- Aucune bibliothèque native supplémentaire n'est nécessaire. Sous Linux, la sortie XPS et SVG nécessite ICU. Voir [Configuration système requise](/tex/{{lang.url-fragment}}net/system-requirements/) et [Linux, macOS et Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/).
<br><br>

**Q : Quelles sont les limitations de la version d'évaluation ?**

**R :** Sans licence, Aspose.TeX fonctionne en mode d'évaluation : il produit au maximum quatre pages d'un document, et ces pages portent un filigrane d'évaluation. La version d'évaluation est le même package ; pour l'évaluer sans limitations, demandez une [licence temporaire de 30 jours](https://purchase.aspose.com/temporary-license/). Voir [Licence](/tex/{{lang.url-fragment}}net/licensing/).
<br><br>

**Q : Comment appliquer une licence dans le code ?**

**R :** Appliquez la licence une seule fois, avant la première conversion :

```csharp
Aspose.TeX.License license = new Aspose.TeX.License();
license.SetLicense(@"C:\License\Aspose.TeX.lic");
```

Vous pouvez aussi charger la licence depuis un flux ou utiliser une licence au compteur (metered). Voir [Licence](/tex/{{lang.url-fragment}}net/licensing/). Pour les tarifs, consultez la [page des tarifs d'Aspose.TeX](https://purchase.aspose.com/pricing/tex/).
<br><br>

**Q : Où trouver la documentation de l'API, des exemples et de l'assistance ?**

**R :**

- [Guide du développeur](https://docs.aspose.com/tex/net/)
- [Référence de l'API](https://reference.aspose.com/tex/net/)
- [Forum de la communauté](https://forum.aspose.com/c/tex/)
<br><br>
