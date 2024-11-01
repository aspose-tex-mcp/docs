---
translation: true
template: /templates/_template-net.md
title: E/S LaTeX | Aspose.TeX pour .NET
linktitle: Entrée/sortie LaTeX
weight: 17
url: /net/latex-io/
description: Cette page décrit les particularités du travail avec LaTeX comme format de sortie ou d'entrée et le fichier *.aux* comme obligatoire.
keywords: latex io, latex i, latex o, fichier d'entrée latex, entrée en latex
lastmod: "2024-09-27"
---

{{<section overview>}}

## fichier LaTeX

Si nous avons un [fichier TeX](/tex/{{lang.url-fragment}}net/tex-io/#tex-file) qui a la structure suivante, alors nous appellerons ce fichier un *fichier LaTeX* :


```tex
\documentclass{<a document class>}
% Preamble
...
\begin{document}
% Document body
...
\end{document}
```

où `<une classe de document>` est le nom d'une [classe de document](https://en.wikibooks.org/wiki/LaTeX/Document_Structure#Document_classes) qui est un fichier TeX d'entrée qui définit l'apparence des pages et des macros du document de sortie les plus adaptées à un certain type de document.

Pour être honnête, vous pouvez insérer des séquences de contrôle primitives avant `\documentclass{}`, comme `\nonstopmode`, etc. Mais chaque macro LaTeX vérifie si elle se trouve dans une partie appropriée d'un fichier.

Il y a quelques points à noter à propos de TeX [input](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) et [output](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) dans le contexte de l'utilisation de fichiers LaTeX.

## Fichier de sortie LaTeX

Un travail LaTeX typique crée un fichier de sortie auxiliaire avec le [nom du travail](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) comme nom et l'extension *.aux*. Ce fichier contient généralement des données de référence que le moteur collecte au cours de l'exécution du travail, si vous définissez, par exemple, des étiquettes pour les formules mathématiques (équations), puis que vous y faites référence quelque part dans le texte. Au cas où vous n'utiliseriez rien de ce genre, ce fichier contient uniquement la séquence de contrôle `\relax` (qui est l'une des primitives TeX). Alors ne soyez pas surpris.

Bien que les primitives `\openout`, `\write` et `\closeout` ne soient pas interdites, les packages sont l'endroit le plus approprié pour elles. Par conséquent, vous devriez mieux les utiliser dans vos propres packages personnalisés si vous les développez.

D'autres parties de la sortie sont arbitraires, suivent également le concept général [TeX output](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) et dépendent de ce que votre fichier TeX (programme) est censé faire exactement, des packages (voir ci-dessous) que vous utilisez, etc.

## fichier d'entrée LaTeX

Le fichier *.aux* susmentionné est en même temps une partie obligatoire de la saisie dans LaTeX. Algorithmiquement, LaTeX ne peut pas accomplir ces tâches liées aux références en une seule exécution, donc le même travail doit être exécuté deux fois : la première fois pour collecter des données, la deuxième fois pour utiliser ces données. De nombreux systèmes logiciels basés sur LaTeX exécutent automatiquement les tâches LaTeX deux fois. Spoiler : Il existe une [option](/tex/{{lang.url-fragment}}net/other-options/#how-to-repeat-the-job) dans l'API Aspose.TeX qui nous permet de contrôler ce comportement.

Une autre partie obligatoire est une [classe de document](/tex/{{lang.url-fragment}}net/latex-io/#latex-file). Le fichier de classe de document, à son tour, peut implicitement dépendre d'autres fichiers, qui sont donc également inclus dans l'entrée LaTeX.

Si vous souhaitez utiliser des fonctionnalités dépassant la portée de LaTeX de base et de ses classes de documents, mais prises en charge par une certaine implémentation du moteur TeX, vous utilisez généralement un package dont vous devez informer le moteur dans le préambule. Un *package LaTeX* est un fichier, ou un groupe de fichiers assemblés sous un même nom, qui fournit de telles fonctionnalités. Pour notifier le moteur, vous devez utiliser la commande `\usepackage` avec le nom du package et les options omissables, si le package en définit.

Par exemple,


```tex
\usepackage[a6paper,landscape]{geometry}
```

Bien que les primitives `\input`, `\openin`, `\read` et `\closein` ne soient pas interdites, les packages sont l'endroit le plus approprié pour elles. Par conséquent, vous devriez mieux les utiliser dans vos propres packages personnalisés si vous les développez.

D'autres parties de l'entrée sont arbitraires, suivent également le concept général [TeX input](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) et dépendent de ce que votre fichier TeX (programme) est censé faire exactement, des packages que vous utilisez, etc.