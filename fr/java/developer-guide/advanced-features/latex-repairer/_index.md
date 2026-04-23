---
translation: true
template: /templates/_template-java.md
title: Réparation de fichiers LaTeX | Java
linktitle: Réparation de fichiers LaTeX
weight: 30
url: /java/latex-repair/
description: La fonctionnalité de réparation de fichiers LaTeX dans l'API Aspose.TeX pour Java est décrite avec les exemples de code.
lastmod: "2026-04-21"
---

{{<section overview>}}

## Comment vérifier et réparer un fichier LaTeX

Si vous ne savez pas si un fichier texte est un fichier LaTeX et souhaitez qu'il soit composé, vous pouvez utiliser la fonctionnalité de vérification et de réparation LaTeX offerte par l'API Aspose.TeX pour Java. Dans l'exemple ci-dessous, nous allons vérifier et réparer un exemple de fichier, « invalid-latex.tex », de l'exemple de projet Aspose.TeX pour Java.

Pour commencer, il est important de noter que l'exemple de fichier semble utiliser la syntaxe TeX mais n'a pas la structure requise par LaTeX. Comme vous le savez peut-être, un fichier LaTeX doit inclure un préambule commençant par la commande `\documentclass`, ainsi qu'un corps inclus dans l'environnement du document, spécifiquement entre `\begin{document}` et `\end{document}`.

Examinons maintenant l'exemple de code Java.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-LaTeXRepairer.java" >}}

Semblable à un travail TeX classique, nous commençons par créer un objet contenant les options du processus que nous sommes sur le point d'exécuter. La plupart de ces options sont les mêmes que celles d'un travail TeX classique. En effet, en appelant la méthode [setInputWorkingDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setInputWorkingDirectory-com.aspose.tex.IInputWorkingDirectory-), on précise l'espace à partir duquel les fichiers d'entrée doivent être lus. Cependant, dans cet exemple, nous ne l'utilisons pas ici car nous fournissons le chemin complet du fichier d'entrée principal dans le système de fichiers et aucun fichier personnalisé ne doit être inclus dans le fichier d'entrée principal. Ensuite, nous appelons la méthode [setOutputWorkingDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setOutputWorkingDirectory-com.aspose.tex.IOutputWorkingDirectory-) pour spécifier l'espace où les fichiers de sortie doivent être écrits. Si elle est appelée, la méthode [setRequiredInputDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-) fait pointer les options vers l'espace où vous pouvez stocker les packages LaTeX qui ne sont pas intégrés dans la bibliothèque Aspose.TeX. Enfin, la méthode [setGuessPackageCallback()](https://reference.aspose.com/tex/java/com.aspose.tex.features/latexrepaireroptions/#setGuessPackageCallback-com.aspose.tex.features.IGuessPackageCallback-) sera abordée plus tard.

Une fois les options attribuées, nous pouvons procéder à l’exécution du processus.

Alors, à quoi ressemble le processus de vérification et de réparation ? Cela commence par la recherche par l'API d'une occurrence `\documentclass` dans le fichier d'entrée. S'il n'est pas trouvé, l'API suppose que `\documentclass{article}` doit être inséré au début du fichier. Ces informations sont enregistrées dans le fichier de rapport de réparation (.log).

Ensuite, le processus commence à analyser le fichier d'entrée ajusté depuis le début. Le moteur TeX équipé du format LaTeX peut, à un moment donné, générer une erreur indiquant que `\begin{document}` n'a pas encore été trouvé alors qu'il aurait déjà dû l'être. De cette façon, la position à laquelle `\begin{document}` doit être inséré est définie et reflétée dans le rapport.

Lors de l'analyse ultérieure du fichier, le moteur peut rencontrer des commandes ou des environnements non définis. Dans de tels cas, l'API peut faire des hypothèses sur les [packages requis intégrés](/tex/{{lang.url-fragment}}net/embedded-packages/) (ceux qui définissent les commandes et les environnements qui ne sont pas définis tant que ces packages ne sont pas inclus) pour certaines des commandes et environnements les plus courants. Cependant, il est possible de faire de telles hypothèses en externe par une classe qui implémente l'interface [IGuessPackageCallback](https://reference.aspose.com/tex/java/com.aspose.tex.features/iguesspackagecallback/). Une fois que vous avez développé une telle classe, une instance de celle-ci doit être transmise au processus en appelant la méthode `setGuessPackageCallback()`.

Voici un exemple de base qui mappe simplement la commande `\head` au package `fancyhdr` :

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Features-LaTeXRepairer-PackageGuessingCallback.java" >}}

Comme pour le fichier exemple, le moteur rencontre d'abord la commande `\chapter`, qui n'est pas définie dans la classe de document `article` mais est définie dans la classe de document `book`. L'API ajuste la classe du document afin que la version finale du fichier réparé commence par `\documentclass{book}`. Ensuite, le moteur trouve la commande `\lhead` susmentionnée et détermine que `\usepackage{fancyhdr}` doit être inséré dans le préambule. Les commandes `\href` et `\includegraphics` qui apparaissent plus tard dans le fichier obligent le réparateur à insérer `\usepackage{hyperref}` et `\usepackage{graphics}` dans le préambule, respectivement. Ces décisions sont prises sur la base des mappages internes de l'API. Comme auparavant, toutes ces réparations sont enregistrées dans le fichier de rapport.

Enfin, le moteur se termine anormalement car la conclusion appropriée d'un document LaTeX manque. En conséquence, le réparateur ajoute `\end{document}` à la fin du fichier et inclut ces informations dans le rapport.

Après avoir créé la version corrigée du fichier original, le réparateur exécute un travail TeX dessus pour la vérification finale. Dans notre exemple, cette exécution ne détecte aucune erreur critique, la version corrigée peut donc être composée plus ou moins comme prévu.

Voici le rapport complet :

```
Trying to repair the original file...
--------------------------------------------------------------------------------
\documentclass is missing in the original file. Inserted at the beginning.
\begin{document} is missing in the original file. Inserted at line 3, pos. 0.
The command \chapter at line 3, pos. 0 is undefined. Consider using \usepackage{package_name} in the preamble,
    where 'package_name' is the name of the package which defines this command.
The command \lhead at line 5, pos. 0 is undefined. \usepackage{fancyhdr} is inserted in the preamble
    since the 'fancyhdr' package supposedly defines the command.
The command \href at line 8, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 17, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 20, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 27, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 32, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \includegraphics at line 54, pos. 2 is undefined. \usepackage{graphicx} is inserted in the preamble
    since the 'graphicx' package supposedly defines the command.
The command \href at line 67, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 95, pos. 57 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 96, pos. 0 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
The command \href at line 98, pos. 100 is undefined. \usepackage{hyperref} is inserted in the preamble
    since the 'hyperref' package supposedly defines the command.
\end{document} is missing in the original file. Inserted at the end.

Checking the repaired file...
--------------------------------------------------------------------------------
There are no critical errors in the fixed file.
```

**Vous pouvez également consulter notre application Web gratuite [**AI LaTeX Repairer**](https://products.aspose.ai/tex/latex-repairer), qui est construite sur la base de la fonctionnalité implémentée dans [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) et implique une fonctionnalité plus avancée. implémentation de l'interface `IGuessPackageCallback`.**