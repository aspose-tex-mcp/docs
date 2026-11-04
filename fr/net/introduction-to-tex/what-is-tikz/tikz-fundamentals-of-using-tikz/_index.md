---
translation: true
template: /templates/_template-net.md
title: Principes fondamentaux de TikZ | Aspose.TeX .NET
linktitle: Principes fondamentaux de TikZ
weight: 19
url: /net/tikz-fundamentals-of-using-tikz/
keywords: Principes fondamentaux de TikZ, Principes fondamentaux de TikZ, Tutoriel TikZ
description: Explorez les principes fondamentaux et les commandes de base de TikZ pour créer des graphiques pour vos documents TeX et LaTeX.
lastmod: "2026-11-04"
---

{{<section overview>}}

Dans ce chapitre, nous explorons les principes et commandes fondamentaux de TikZ. Comprendre ces bases vous permettra de créer des graphiques clairs et expressifs pour vos documents.

## Système de coordonnées dans TikZ

Les graphiques TikZ sont créés à partir de coordonnées. Les coordonnées définissent des positions dans vos dessins et peuvent être spécifiées de différentes manières :

- **Coordonnées cartésiennes (x, y)** :

```tex
\documentclass{article}
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
    \draw (0,0) -- (2,2);
\end{tikzpicture}
\end{document}
```

- **Coordonnées polaires (angle : rayon)** :


```tex
    \draw (0,0) -- (45:2);
```

Les coordonnées peuvent être librement combinées dans un dessin pour obtenir le résultat graphique souhaité.

*Une brève remarque sur les décalages relatifs :

- (0,0) -- ++(1,1) se déplace vers (0,0), trace un segment jusqu’à (1,1) et définit le nouveau point courant à (1,1).
- (0,0) -- +(1,1) trace un segment jusqu’à (1,1) par rapport à (0,0), mais laisse le point courant inchangé, en (0,0).*

## Dessin de formes simples

TikZ permet de créer facilement des formes géométriques simples :

- **Lignes et polylignes** :

```tex
    \draw (0,0) -- (1,1) -- (2,0);
```

- **Rectangles**:

```tex
    \draw (0,0) rectangle (2,1);
```

- **Cercles et ellipses** :

```tex
   \draw (1,1) circle (0.5);
    \draw (3,1) ellipse (1 and 0.5);
```

## Couleurs et motifs de remplissage

Les couleurs et les motifs de remplissage améliorent considérablement la clarté visuelle. Vous pouvez spécifier les couleurs directement ou utiliser des noms prédéfinis :

```tex
   \draw[red, thick] (0,0) rectangle (1,1);
   \draw[fill=blue!20] (2,0) circle (0.5);
```

La syntaxe « blue!20 » désigne une couleur bleue d'intensité 20 %.

## Styles et épaisseurs de ligne

TikZ vous permet de modifier les styles et l'épaisseur des lignes pour améliorer la présentation graphique :

- **Épaisseur de ligne** :

```tex
   \draw[ultra thick] (0,0) -- (1,1);
   \draw[thin] (1,0) -- (2,1);
```

- **Lignes pointillées et en pointillés** :

```tex
   \draw[dashed] (0,0) -- (2,2);
   \draw[dotted] (2,0) -- (4,2);
```

## Nœuds et étiquettes

Les nœuds vous permettent d'ajouter facilement des annotations textuelles :

```tex
   \draw (0,0) -- (1,1) 
```

Vous pouvez positionner précisément les étiquettes par rapport à vos éléments graphiques, améliorant ainsi leur lisibilité.

## Tracés et courbes

Les tracés TikZ peuvent être des lignes droites ou des courbes. Les courbes sont créées à l'aide d'une syntaxe simple :

```tex
   \draw (0,0) .. controls (1,2) and (3,-1) .. (4,1);
```

Les points de contrôle façonnent la courbure de manière intuitive.

## Regroupement d'éléments

Le regroupement d'éléments graphiques simplifie les transformations (comme la mise à l'échelle et la rotation) :

```tex
\begin{scope}[rotate=45, scale=1.5]
  \draw (0,0) rectangle (1,1);
  \draw (1,1) circle (0.5);
\end{scope}
```

Les éléments de la « portée » pivotent et se redimensionnent ensemble, préservant ainsi l'alignement.

---

La maîtrise de ces concepts et commandes TikZ fondamentaux vous permettra de créer des graphiques sophistiqués pour vos documents.

## Exemple programmatique de traitement de dessins TikZ via Aspose.TeX

Vous trouverez ci-dessous une présentation détaillée ainsi qu'un exemple de code illustrant comment les développeurs peuvent compiler un document `.tex` contenant des dessins TikZ, directement en un fichier vectoriel (PDF) de haute fidélité, au sein d'une application .NET.

```csharp
using System;
using System.IO;
using Aspose.TeX;
using Aspose.TeX.IO;
using Aspose.TeX.Presentation.Pdf;

namespace AsposeTexTikzDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Définir les répertoires d'entrée et de sortie
            string dataDir = @"C:\DocumentSamples\TikzInput";
            string outputDir = @"C:\DocumentSamples\TikzOutput";

            // S'assurer que le répertoire de sortie existe
            Directory.CreateDirectory(outputDir);

            // Initialiser les options TeX pour une tâche standard de traitement de document LaTeX
            // TeXConfig.ObjectLaTeX configure le moteur avec les packages intégrés (dont tikz/pgf)
            TeXOptions options = TeXOptions.ConsoleAppOptions(TeXConfig.ObjectLaTeX);
            options.InputWorkingDirectory = new InputFileSystemDirectory(dataDir);
            options.OutputWorkingDirectory = new OutputFileSystemDirectory(outputDir);

            // Définir le nom de la tâche, utilisé pour les fichiers de sortie
            options.JobName = "tikz-fundamentals";

            // Configurer les options d'enregistrement pour un rendu direct au format PDF
            options.SaveOptions = new PdfSaveOptions();

            // Créer et exécuter le TeXJob avec le fichier source, le périphérique de sortie et les options
            Console.WriteLine("Starting TikZ compilation job...");

            TeXJobResult result = new TeXJob(
                Path.Combine(dataDir, "tikz-fundamentals.tex"),
                new PdfDevice(),
                options
            ).Run();

            if (result < TeXJobResult.ErrorMessageIssued)
                Console.WriteLine($"TikZ graphic successfully compiled to PDF at: {outputDir}");
            else
                Console.WriteLine($"Compilation failed with {result}. See the .log file in {outputDir}.");
        }
    }
}
```

**De plus, découvrez notre application web gratuite basée sur l'API Aspose.TeX pour .NET pour des conversions TeX rapides et faciles.**
