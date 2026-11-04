---
translation: true
template: /templates/_template-net.md
title: Packages LaTeX externes | Aspose.TeX pour .NET
linktitle: Packages LaTeX externes
weight: 20
url: /net/external-latex-packages/
description: Aspose.TeX pour .NET permet l'utilisation de packages non inclus dans la bibliothèque elle-même, tels que les packages fancybox ou pgfplots.
keywords: packages Latex externes, Aspose Tex, .Net Tex, packages Latex, Fancybox, PGFplots, répertoire d'entrée requis, fichier ZIP d'entrée, répertoire d'entrée personnalisé, conversion Tex
lastmod: "2026-11-04"
---

{{<section overview>}}

## Packages LaTeX externes

La bibliothèque **Aspose.TeX** comprend un certain nombre de [packages LaTeX courants](/tex/{{lang.url-fragment}}net/embedded-packages/). Vous n'avez donc pas à vous soucier de la manière de fournir ces packages au moteur TeX de la bibliothèque. Mais parfois (ou assez souvent), votre fichier LaTeX peut nécessiter un package au-delà du « bundle » de packages pris en charge « nativement ». Si tel est le cas, vous pouvez essayer de fournir l'entrée requise, c'est-à-dire les fichiers sources du package requis, via l'option [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) de l'instance de classe [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/). Nous verrons comment cela fonctionne avec deux exemples.

### Entrée requise décompressée (package `fancybox`)

Disons que nous avons le fichier LaTeX simple suivant, qui est `required-input-fs.tex` de notre [exemple de solution](https://GitHub.com/aspose-tex/Aspose.TeX-for-.NET) :


```tex
\documentclass{article}
\usepackage[a6paper,landscape]{geometry}
\usepackage{fancybox}
\begin{document}
Test: \fbox{
  \begin{Bitemize}[b]
  \item First item
  \item A second one\\ on two lines
  \item(2pt) A third with extra space
  \end{Bitemize}
}
\par\bigskip
Test: \fbox{
  \begin{Beqnarray}[t]
  y & = & x^2 \\
  a^2 + 2ab + b^2 & = & (a + b)^2 \\
  \int_0^\infty e^{-ax} dx & = & \frac{1}{a}
  \end{Beqnarray}
}
\end{document}
```

Sur la 3ème ligne, nous pouvons voir que le fichier nécessite le package `fancybox`, qui n'est pas supporté "nativement". Supposons également que nous ayons le fichier source du package `fancybox`. Il s’agit d’un package simple, il se compose donc en réalité d’un seul fichier. Nous pouvons placer ce fichier n'importe où dans notre système de fichiers et spécifier le chemin du répertoire aussi simplement que indiqué ci-dessous :


```C#
options.RequiredInputDirectory = new InputFileSystemDirectory("path-to-directory-where-fancybox.sty-located");
```

Après avoir exécuté un travail TeX avec cette option (n'oubliez pas d'ajuster les autres options si nécessaire), nous obtenons le document de sortie (c'est-à-dire une image PNG).

![Document de sortie](/tex/images/net/Conversion-RequiredInputFs.png)

Voici le code source complet de l'exemple :

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInput-FileSystem.cs" >}}

### Entrée requise archivée (package `pgfplots`)

Disons maintenant que nous avons le fichier LaTeX suivant, également assez simple, qui est `required-input-zip.tex` de notre exemple de solution :


```tex
\documentclass{article}
\usepackage[margin=0.25in]{geometry}
\usepackage{pgfplots}
\pgfplotsset{width=10cm,compat=1.18}
\begin{document}

First example is 2D and 3D math expressions plotted side-by-side.

%Here begins the 2D plot
\begin{tikzpicture}
\begin{axis}
\addplot[color=red]{exp(x)};
\end{axis}
\end{tikzpicture}
%Here ends the 2D plot
\hskip 5pt
%Here begins the 3D plot
\begin{tikzpicture}
\begin{axis}
\addplot3[
    surf,
]
{exp(-x^2-y^2)*x};
\end{axis}
\end{tikzpicture}
%Here ends the 3D plot

\end{document}
```

Sur la 3ème ligne, nous pouvons voir que le fichier nécessite le package `pgfplots`, qui n'est pas non plus supporté "nativement". Encore une fois, nous supposons que nous avons les fichiers sources du paquet `pgfplots`. Il s'agit d'un nombre assez important de fichiers répartis entre deux emplacements si vous les trouvez dans le répertoire d'installation de n'importe quelle application de composition LaTeX. Vous pouvez trouver le dossier `pgfplots` dans les dossiers `\tex\generic` et `\tex\latex`. Et le contenu de ces deux dossiers doit être fourni comme entrée requise dans la bibliothèque Aspose.TeX. Nous souhaitons que ces fichiers sources soient regroupés dans une archive ZIP, voici donc la présentation de l'archive :

![Mise en page de l'archive](/tex/images/net/pgfplots-zip-layout.png)

Et voici comment nous spécifions l'accès à ces fichiers sources :


```C#
using (Stream zipStream = File.Open("path-to-zip-with-pgfplots-sources"), FileMode.Open))
{
    ...
    options.RequiredInputDirectory = new InputZipDirectory(zipStream);
    ...
}
```

Après avoir exécuté un travail TeX avec cette option, nous obtenons le document de sortie :

![Document de sortie](/tex/images/net/Conversion-RequiredInputZip.png)

Voici le code source complet de l'exemple :

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInput-Zip.cs" >}}

> **_REMARQUE :_** Le résultat a été vérifié à l'aide du package `pgfplots` version 1.18.1. La version du package `pfg` inclus dans la bibliothèque **Aspose.TeX** est la 3.1.9a.

### Utilisation de packages de polices externes

En règle générale, les distributions LaTeX fournissent un ensemble de polices par défaut disponibles pour la composition. À l'exception de ces polices, **Aspose.TeX** inclut un certain nombre de packages de polices non standard. Par exemple, « amsfonts », « eurosym » et « wasysym ». Comme nous l'avons vu ci-dessus, Aspose.TeX permet également d'employer des packages externes. Mais nous parlions surtout de packages qui ne contiennent pas de polices.
L'extension du moteur *Object TeX* de **Aspose.TeX** a besoin de cartes de polices (qui sont des fichiers texte dans un certain format avec l'extension `.map` par convention) pour déterminer quelles polices physiques correspondent au nom de police interne de chaque TeX. . Ces cartes de polices doivent être chargées dans la mémoire de TeX lors de la phase d'initialisation. Et, bien sûr, elles doivent être présentes parmi les fichiers du package que vous branchez. Comme le moteur ne connaît pas les noms de toutes les cartes de polices, il recherche tous les fichiers avec l'extension `.map`. Par conséquent, une implémentation de l'interface [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/) utilisée comme valeur de l'option [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) doit fournir un moyen d'accéder aux collections de noms de fichiers par extension. Plus précisément, cette implémentation doit également implémenter l'interface [IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/). Les implémentations standard - [InputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) et [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) - le font déjà.

Ci-dessous, nous fournissons un exemple illustratif d'un répertoire d'entrée requis personnalisé qui implémente également l'interface [IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/). Tout en nous concentrant sur la collecte des noms de fichiers par extension, nous omettons intentionnellement les détails du stockage et de la récupération des fichiers.

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-RequiredInputDirectory.cs" >}}

### Restrictions

Il peut arriver qu'un package requis par votre fichier LaTeX soit développé sous le noyau *LaTeX3e*. Un tel package ne fonctionnera probablement pas avec la bibliothèque **Aspose.TeX** puisque cette dernière est basée sur le noyau *LaTeX2e*.

Il peut également arriver qu'un package requis par votre fichier LaTeX appelle directement des commandes primitives dépendantes du périphérique qui ne sont pas prises en charge par le moteur *Object TeX* de la bibliothèque **Aspose.TeX**. Malheureusement, un tel package ne fonctionnera pas à coup sûr.

## Création d'un agent d'IA pour l'optimisation des packages LaTeX intégrés

Si vous devez créer un agent d'IA qui optimise le contenu pour l'inventaire de packages intégré sans effectuer de longues requêtes réseau dynamiques ni de recherches dans le système de fichiers lors de la génération, vous pouvez utiliser le flux de travail décrit ci-dessous.

Au lieu de forcer un LLM à deviner quels packages sont sûrs ou rapides à utiliser, l'agent cible cet inventaire précis de packages précompilés afin d'éviter les erreurs dues à des packages manquants.

![Architecture d'assemblage de documents pour agent d'IA intégré](/tex/images/net/tutorial/blockscheme-for-ai-latex-package-optimization.png)

1. Extraction des intentions de mise en page (couche d'analyse LLM)

L'utilisateur fournit des données non structurées de formats multiples ou des directives conversationnelles. Le LLM associe directement les demandes à la liste des packages intégrés d'Aspose (`colortbl` pour l'ombrage des lignes, `geometry` pour les marges et `multirow` pour les cellules s'étendant sur plusieurs lignes).

2. Isolation de l'AST et injection du préambule

Au lieu d'écrire des importations de packages volumineuses, l'agent vérifie les exigences du code par rapport à la liste des packages intégrés.

Il n'écrit dans le préambule que les commandes `\usepackage` nécessaires.

3. Mise en sandbox et exécution du flux (Nœud moteur Aspose.TeX)

Le code source LaTeX est transmis à un `TeXJob` sous forme de flux, avec `TeXOptions` créé pour `TeXConfig.ObjectLaTeX`. `TeXJob.Run()` est synchrone : l'agent l'exécute donc dans un worker en arrière-plan.

```tex
\usepackage[a4paper,margin=0.5in]{geometry}
\usepackage{amsmath,multirow,colortbl}
```

4. Sérialisation des ressources (Couche de rendu de sortie)

La tâche écrit le résultat avec un périphérique de sortie, tel que `PdfDevice` ou `SvgDevice`, et l'agent le renvoie au client.