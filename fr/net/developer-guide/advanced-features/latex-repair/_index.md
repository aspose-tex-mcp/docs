---
translation: true
template: /templates/_template-net.md
title: Réparation de fichiers LaTeX | .NET
linktitle: Réparation de fichiers LaTeX
weight: 30
url: /net/latex-repair/
description: Aspose.TeX pour la réparation .NET LaTeX est décrite dans cet article. Découvrez les exemples de code sur la façon d’utiliser la fonctionnalité.
lastmod: "2026-06-12"
---

{{<section overview>}}

## Comment vérifier et réparer un fichier LaTeX

Si vous avez un fichier texte que vous pensez être un fichier LaTeX et que vous souhaitez qu'il soit composé, mais que vous n'êtes pas sûr qu'il s'agisse réellement d'un fichier LaTeX (vous êtes peut-être nouveau dans le monde LaTeX), vous pouvez essayer d'utiliser la vérification et réparation de la fonctionnalité LaTeX fournie par l'API Aspose.TeX pour .NET. Dans l'exemple suivant, nous allons vérifier et réparer un exemple de fichier, « invalid-latex.tex », de l'exemple de projet Aspose.TeX pour .NET.

Tout d'abord, il convient de mentionner que bien que l'exemple de fichier semble utiliser la syntaxe TeX, il n'a pas la structure requise par LaTeX. Comme vous le savez peut-être, un fichier LaTeX doit avoir un préambule qui commence par la commande `\documentclass` et un corps dans l'environnement `document`, c'est-à-dire entre `\begin{document}` et `\end{document}`.

Examinons maintenant l'exemple de code C#.

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Examples_LaTeXRepairerExample" >}}

Comme pour un travail TeX classique, nous créons d'abord un objet qui contient les options du processus que nous sommes sur le point d'exécuter. La plupart d'entre elles sont identiques aux options d'un travail TeX classique. En effet, le [InputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/inputworkingdirectory/) est l'espace à partir duquel les fichiers d'entrée doivent être lus. Nous ne l'utilisons pas ici car nous fournissons le chemin complet du fichier d'entrée principal dans le système de fichiers, et aucun fichier personnalisé n'est censé être inclus dans le fichier d'entrée principal. Ensuite, [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/outputworkingdirectory/) est l'espace où les fichiers de sortie doivent être écrits. [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/requiredinputdirectory/), s'il est attribué, pointe vers l'espace où vous pouvez stocker les packages LaTeX qui ne sont pas intégrés dans la bibliothèque Aspose.TeX. La propriété [GuessPackageCallback](https://reference.aspose.com/tex/net/aspose.tex.features/latexrepaireroptions/guesspackagecallback/) sera abordée plus tard.

Après avoir attribué les options, nous lançons simplement le processus !

Alors, à quoi ressemble le processus de vérification et de réparation ? Tout d'abord, l'API recherche dans le fichier d'entrée une occurrence `\documentclass`. S'il échoue, il suppose que `\documentclass{article}` doit être inséré au tout début du fichier. Ce fait est reflété dans le fichier de rapport de réparation (`.log`).

Ensuite, il commence à analyser le fichier d'entrée ajusté depuis le tout début. Le moteur TeX chargé du format LaTeX peut générer une erreur à un moment donné, signalant qu'aucun `\begin{document}` n'a été trouvé jusqu'à présent, alors que cela aurait déjà dû se produire. Ainsi, la position à laquelle `\begin{document}` doit être inséré est définie et reflétée dans le rapport.

Au fur et à mesure que le moteur analyse le fichier, il peut trouver des commandes ou des environnements non définis. L'API peut faire des hypothèses sur les [packages requis intégrés](/tex/{{lang.url-fragment}}net/embedded-packages/) (ceux qui définissent les commandes et les environnements qui ne sont pas définis tant que ces packages ne sont pas inclus) pour certaines des commandes et environnements les plus courants. Cependant, il existe un moyen de faire de telles hypothèses en externe en implémentant l'interface [IGuessPackageCallback](https://reference.aspose.com/tex/net/aspose.tex.features/iguesspackagecallback/). Une instance d'une telle classe doit être affectée à l'option `GuessPackageCallback`.

Voici un exemple très simple qui mappe simplement la commande `\head` au package `fancyhdr` :

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Examples_PackageGuessingCallback" >}}

Comme pour le fichier exemple, le moteur rencontre d'abord la commande `\chapter`, qui n'est pas définie dans la classe de document `article` mais est définie dans la classe de document `book`. L'API ajuste la classe du document afin que la version finale du fichier corrigé commence par `\documentclass{book}`. Ensuite, le moteur trouve la commande `\lhead` susmentionnée et décide que `\usepackage{fancyhdr}` doit être inséré dans le préambule. Les commandes `\href` et `\includegraphics` qui se produisent plus tard obligent le réparateur à insérer `\usepackage{hyperref}` et `\usepackage{graphics}` dans le préambule, respectivement. Ces décisions sont basées sur les mappages internes de l'API. Encore une fois, tous ces correctifs sont enregistrés dans le fichier de rapport.

Enfin, le moteur se termine anormalement puisque la fin normale d'un document LaTeX est manquante. Cela oblige le réparateur à ajouter `\end{document}` à la fin du fichier et à refléter ce fait dans le rapport.

Une fois la version corrigée du fichier d'origine créée, le réparateur exécute le travail TeX dessus pour la vérification finale. Dans notre exemple, cette exécution ne trouve aucune erreur critique, la version corrigée peut donc être composée plus ou moins comme prévu.

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

## Création d'un agent d'IA pour la correction de formules mathématiques LaTeX

Ce flux de travail combine la validation structurelle de l'API de réparation native d'Aspose.TeX avec l'inférence contextuelle d'un noyau LLM afin d'obtenir un pipeline de rendu sans erreur. Il peut s'agir d'un agent indépendant pour vérifier et corriger les erreurs dans les fichiers LaTeX existants, ou d'une partie du processus d'écriture mathématique.

### Architecture du flux de travail d'un agent d'IA qui corrige la syntaxe LaTeX

![Schéma fonctionnel du flux de travail de correction de formules LaTeX par IA](/tex/images/net/tutorial/blockscheme-for-math-repairing.png)

1. Traitement syntaxique et extraction des intentions (couche LLM)

L'utilisateur fournit des instructions conversationnelles, des extraits de texte brut, des formules copiées ou un fichier `.latex`. L'agent sollicite le noyau LLM pour extraire les intentions mathématiques principales et génère un bloc mathématique LaTeX ciblé.

2. Correction automatique de la structure native (Réparateur Aspose.TeX)

Le fragment mathématique généré est traité par le cycle de vie de réparation natif d'Aspose.TeX afin de définir des limites structurelles standard, sans que les développeurs aient besoin d'écrire de fonctions d'encapsulation regex codées en dur.

L'agent crée une instance LaTeXRepairer en arrière-plan. Le moteur analyse les flux de données, intercepte les erreurs et ajoute en toute sécurité les balises `\begin{document}` et `\end{document}` autour des chaînes mathématiques pour garantir la validité du pipeline de compilation.

4. Exécution et génération des ressources/rapports (Moteur de rendu)

Une fois la chaîne de script réparée et empaquetée compilée avec succès, l'agent crée un rapport ou convertit la sortie du système de fichiers propre dans les formats visuels cibles.

**Vous pouvez également consulter notre application Web gratuite [**AI LaTeX Repairer**](https://products.aspose.ai/tex/latex-repairer), qui est construite sur la base de la fonctionnalité implémentée dans [Aspose.TeX for .NET API](https://products.aspose.com/tex/net/) et implique une fonctionnalité plus avancée. implémentation de l'interface `IGuessPackageCallback`.**
