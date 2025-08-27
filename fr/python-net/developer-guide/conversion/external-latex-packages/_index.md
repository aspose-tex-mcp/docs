---
translation: true
template: /templates/_template-python-net.md
title: Packages LaTeX externes | Python
linktitle: Packages LaTeX externes
weight: 19
url: /python-net/external-latex-packages/
description: Aspose.TeX pour Python permet l'utilisation de packages non inclus dans la bibliothèque elle-même, tels que les packages fancybox ou pgfplots.
lastmod: "2024-09-27"
---

{{<section overview>}}

## Packages LaTeX externes

La bibliothèque **Aspose.TeX** est livrée avec une variété de [packages LaTeX courants](/tex/{{lang.url-fragment}}net/embedded-packages/), il n'est donc pas nécessaire de fournir manuellement ces packages au moteur TeX. Cependant, il peut y avoir des situations où votre fichier LaTeX nécessite un package qui n'est pas inclus dans le « bundle » de packages de la bibliothèque. Dans de tels cas, vous pouvez essayer de fournir les entrées nécessaires, telles que les fichiers sources du package requis, via l'option [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) de l'instance de classe [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/). Nous allons explorer comment cela fonctionne avec deux exemples.

### Entrée requise fournie sous une forme décompressée (le package `fancybox`).

Supposons que nous ayons le fichier LaTeX de base suivant nommé « require-input-fs.tex », qui fait partie de notre [exemple de solution](https://GitHub.com/aspose-tex/Aspose.TeX-for-Python-.NET) :

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

La 3ème ligne du fichier indique qu'il nécessite le package `fancybox`, qui n'est pas inclus dans le support "natif". Supposons que nous ayons le fichier source du package `fancybox`. Puisqu'il s'agit d'un simple package composé d'un seul fichier, nous pouvons placer ce fichier n'importe où dans notre système de fichiers et spécifier le chemin du répertoire comme suit :

```Python
options.required_input_directory = InputFileSystemDirectory('path-to-directory-where-fancybox.sty-located')
```

Une fois que nous exécutons un travail TeX avec cette option (n'oubliez pas d'ajuster les autres options si nécessaire), nous obtiendrons le document de sortie, qui dans ce cas est une image PNG.

![Document de sortie](/tex/images/python-net/Conversion-RequiredInputFs.png)

Voici le code source complet de l'exemple :

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.py" >}}

### Fournir les entrées requises sous une forme archivée (le package `pgfplots`)

Supposons maintenant que nous ayons le fichier LaTeX suivant nommé « require-input-zip.tex », qui est également un simple fichier de notre exemple de solution :


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

Sur la troisième ligne, on peut observer que le fichier nécessite le package `pgfplots`, qui n'est pas supporté "nativement". Encore une fois, en supposant que nous possédons les fichiers sources du paquet `pgfplots`, ces fichiers sont assez nombreux et se trouvent dans deux répertoires différents au sein du répertoire d'installation de toute application de composition LaTeX. Le dossier `pgfplots` se trouve dans les répertoires `\tex\generic` et `\tex\latex`. Pour que la bibliothèque Aspose.TeX fonctionne correctement, il est nécessaire de fournir le contenu de ces deux dossiers en entrée. Pour y parvenir, nous souhaitons regrouper ces fichiers sources dans une archive ZIP. Vous trouverez ci-dessous la disposition souhaitée pour les archives :

![Mise en page de l'archive](/tex/images/python-net/pgfplots-zip-layout.png)

Et voici la méthode par laquelle nous définissons l'accessibilité à ces fichiers sources :

```Python
with open("path-to-zip-with-pgfplots-sources") as zipStream:
    ...
    options.required_input_directory = InputZipDirectory(zipStream)
    ...
```

Après avoir exécuté un travail TeX avec cette option, nous obtenons le document de sortie :

![Document de sortie](/tex/images/python-net/Conversion-RequiredInputZip.png)

Voici le code source complet de l'exemple :

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-RequiredInput-Zip.py" >}}

> **_REMARQUE :_** Le résultat a été vérifié à l'aide du package `pgfplots` version 1.18.1. La version du package `pfg` inclus dans la bibliothèque **Aspose.TeX** est la 3.1.9a.

<!--
### Utilisation de paquets de polices externes

En général, les distributions LaTeX sont fournies avec un ensemble prédéfini de polices qui peuvent être utilisées pour la composition. Cependant, en plus de ces polices par défaut, **Aspose.TeX** inclut également plusieurs paquets de polices non standard tels que `amsfonts`, `eurosym` et `wasysym`. Comme nous l'avons vu précédemment, Aspose.TeX prend également en charge l'utilisation de paquets externes, bien que la majeure partie de notre discussion précédente se soit concentrée sur les paquets qui n'incluent pas de polices.

L'extension du moteur *Object TeX* d'**Aspose.TeX** nécessite des tables de polices, qui sont des fichiers texte dans un format spécifique avec l'extension `.map`, pour déterminer les polices physiques correspondantes pour chaque nom de police interne de TeX. Ces tables de polices doivent être chargées dans la mémoire de TeX pendant la phase d'initialisation et doivent être incluses dans le package que vous utilisez. Comme le moteur ne connaît pas les noms de toutes les tables de polices, il recherche les fichiers avec l'extension `.map`. Par conséquent, lors de la fourniture d'une valeur pour l'option [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/), l'implémentation de l'interface [IInputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/) doit permettre l'accès aux collections de noms de fichiers par extension. De plus, cette implémentation doit également implémenter l'interface [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/). Les implémentations standard, telles que [InputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputfilesystemdirectory/) et [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/), répondent déjà à ces exigences.

Vous trouverez ci-dessous un exemple de répertoire d'entrée personnalisé requis qui montre comment implémenter l'interface [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/). Cet exemple se concentre sur la collecte des noms de fichiers par extension et omet intentionnellement les détails du stockage et de la récupération des fichiers.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RequiredInput-Zip.py" >}}
-->

### Restrictions

Si vous rencontrez un package développé sous le noyau *LaTeX3e* et requis par votre fichier LaTeX, il est peu probable qu'il fonctionne avec la bibliothèque **Aspose.TeX**. En effet, la bibliothèque est basée sur le noyau *LaTeX2e*.

De plus, il peut arriver qu'un package requis par votre fichier LaTeX utilise directement des commandes primitives dépendantes du périphérique qui ne sont pas prises en charge par le moteur *Object TeX* de la bibliothèque **Aspose.TeX**. Dans de tels cas, le package ne fonctionnera pas avec la bibliothèque.