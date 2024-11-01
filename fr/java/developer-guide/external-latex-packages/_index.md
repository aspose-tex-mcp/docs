---
translation: true
template: /templates/_template-java.md
title: Packages LaTeX externes | Java
linktitle: Packages LaTeX externes
weight: 30
url: /java/external-latex-packages/
description: Aspose.TeX pour Java permet l'utilisation de packages non inclus dans la bibliothèque elle-même, tels que les packages fancybox ou pgfplots.
lastmod: "2024-09-27"
---

{{<section overview>}}

## Packages LaTeX externes

Il existe un certain nombre de [packages LaTeX courants](/tex/{{lang.url-fragment}}net/embedded-packages/) inclus dans la bibliothèque **Aspose.TeX** pour Java. Vous n'avez donc pas à vous soucier de la manière de fournir ces packages au moteur TeX de la bibliothèque. Mais parfois (peut-être souvent) votre fichier LaTeX peut nécessiter un package au-delà du « bundle » de packages pris en charge « nativement ». Dans ce cas, vous pouvez essayer de fournir l'entrée requise, c'est-à-dire les fichiers source du package requis, en utilisant la méthode [setRequiredInputDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-) de l'instance de classe [TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/). Nous verrons comment cela fonctionne avec deux exemples.

### Entrée requise décompressée (package `fancybox`)

Disons que nous avons le fichier LaTeX simple suivant, qui est `required-input-fs.tex` de notre [exemple de solution](https://GitHub.com/aspose-tex/Aspose.TeX-for-Java) :

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

Sur la 3ème ligne, nous voyons que le fichier nécessite le package `fancybox`, qui n'est pas supporté "nativement". Nous supposons également que nous disposons du fichier source du package `fancybox`. Il s’agit d’un package simple, il ne consiste donc en réalité que d’un seul fichier. Nous pouvons placer ce fichier n'importe où dans notre système de fichiers et spécifier le chemin du répertoire simplement comme suit :

```Java
options.setRequiredInputDirectory(new InputFileSystemDirectory("path-to-directory-where-fancybox.sty-located"));
```

Après avoir exécuté un travail TeX avec cette option (n'oubliez pas d'ajuster les autres options si nécessaire), nous obtenons le document de sortie (c'est-à-dire une image PNG).

![Document de sortie](/tex/images/java/Conversion-RequiredInputFs.png)

Voici le code source complet de l'exemple :

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.java" >}}

### Entrée requise archivée (package `pgfplots`)

Supposons maintenant que nous ayons le fichier LaTeX suivant, également assez simple, qui est « require-input-zip.tex » de notre exemple de solution :


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

Sur la 3ème ligne, nous voyons que le fichier nécessite le package `pgfplots`, qui n'est pas non plus supporté "nativement". Encore une fois, nous supposons que nous avons les fichiers sources du paquet `pgfplots`. Il s'agit d'un ensemble assez important de fichiers répartis entre deux emplacements si vous les trouvez dans le répertoire d'installation de n'importe quelle application de composition LaTeX. Vous pouvez trouver le dossier `pgfplots` dans les dossiers `\tex\generic` et `\tex\latex`. Et le contenu de ces deux dossiers doit être fourni comme entrée requise dans la bibliothèque Aspose.TeX. Nous souhaitons que ces fichiers sources soient regroupés dans une archive ZIP, voici donc la présentation de l'archive :

![mise en page de l'archive](/tex/images/java/pgfplots-zip-layout.png)

Et voici comment nous spécifions l'accès à ces fichiers sources :

```Java
final Stream zipStream = File.Open("path-to-zip-with-pgfplots-sources"), FileMode.Open))
try {
    ...
    options.setRequiredInputDirectory(new InputZipDirectory(zipStream));
    ...
} finally {
    if (zipStream != null)
        zipStream.close();
}

```

Après avoir exécuté un travail TeX avec cette option, nous obtenons le document de sortie :

![Document de sortie](/tex/images/java/Conversion-RequiredInputZip.png)

Voici le code source complet de l'exemple :

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-RequiredInput-Zip.java" >}}

> **_REMARQUE :_** Le résultat a été vérifié à l'aide du package `pgfplots` version 1.18.1. La version du package `pfg` inclus dans la bibliothèque **Aspose.TeX** est la 3.1.9a.

### Utilisation de packages de polices externes

En règle générale, les distributions LaTeX sont livrées avec une sélection de polices par défaut pouvant être utilisées pour la composition. En plus de ces polices, **Aspose.TeX** propose plusieurs packages de polices non standard, tels que `amsfonts`, `eurosym` et `wasysym`. Comme mentionné précédemment, **Aspose.TeX** prend également en charge l'utilisation de packages externes, même si nous nous sommes principalement concentrés sur les packages qui n'incluent pas de polices.
L'extension du moteur *Object TeX* dans **Aspose.TeX** nécessite des cartes de polices, qui sont des fichiers texte avec l'extension `.map` qui spécifient les polices physiques correspondant au nom de police interne de chaque TeX. Ces cartes de polices doivent être chargées dans la mémoire de TeX pendant la phase d'initialisation et doivent être incluses dans les fichiers du package. Étant donné que le moteur ne connaît pas les noms de toutes les cartes de polices, il recherche tous les fichiers portant l'extension « .map ». Par conséquent, l'implémentation de l'interface [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/) utilisée comme valeur de l'option [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--) doit fournir un moyen d'accéder à des collections de noms de fichiers en fonction de leur extension. Plus précisément, cette implémentation doit également implémenter l'interface [IFileCollector](https://reference.aspose.com/tex/java/com.aspose.tex/ifilecollector/). Les implémentations standards, [InputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputfilesystemdirectory/) et [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/), remplissent déjà cette exigence.

Ci-dessous, nous présentons un exemple de répertoire d'entrée requis personnalisé qui implémente également l'interface [IFileCollector](https://reference.aspose.com/tex/java/com.aspose.tex/ifilecollector/). Notre objectif principal est de rassembler les noms de fichiers en fonction de leur extension, et nous omettons intentionnellement les détails du stockage et de la récupération des fichiers.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-RequiredInputDirectory.java" >}}

### Restrictions

Un package requis par votre fichier LaTeX peut être développé sous le noyau *LaTeX3e*. Un tel package ne fonctionnera probablement pas avec la bibliothèque **Aspose.TeX** puisque cette dernière est basée sur le noyau *LaTeX2e*.

De plus, un package requis par votre fichier LaTeX peut appeler directement des commandes primitives dépendantes du périphérique qui ne sont pas prises en charge par le moteur *Object TeX* de la bibliothèque **Aspose.TeX**. Malheureusement, un tel package ne fonctionnera pas à coup sûr.