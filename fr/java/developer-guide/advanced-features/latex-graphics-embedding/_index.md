---
translation: true
template: /templates/_template-java.md
title: Graphiques intégrés LaTeX | API pour Java
linktitle: Graphiques intégrés LaTeX
weight: 18
url: /java/latex-graphics-embedding/
keywords: includegraphics latex, graphiques latex embed base64, graphiques codés latex base64, write18, shell-escape, commande shell latex
description: Découvrez comment injecter des images encodées en Base64 dans le code source LaTeX et découvrez la fonctionnalité \write18 qui rend cela possible.
lastmod: "2024-09-27"
---

{{<section overview>}}

## Une autre façon d'inclure des images

Certains systèmes TeX/LaTeX permettent l'inclusion d'images qui ne sont pas stockées en externe par rapport au fichier LaTeX lui-même ; au lieu de cela, ces images sont intégrées directement dans le fichier LaTeX. Cependant, comme les fichiers TeX/LaTeX sont du texte brut et ne peuvent pas contenir de données binaires, nous avons besoin d'une méthode pour représenter les données binaires dans un format texte. Cela signifie que les données binaires doivent être codées dans une représentation textuelle. Le défi est qu’un moteur TeX ne peut pas interpréter directement ces images codées. En fin de compte, les images sont incluses à l'aide de la commande bien connue `\includegraphics` du package `graphicx`, mais cette commande est limitée à la gestion des fichiers image externes. Par conséquent, un fichier image externe (ainsi qu'un fichier intermédiaire supplémentaire) doit toujours être créé en dehors du fichier LaTeX, mais cela ne se produira que lors de la composition. L'avantage est que vous n'avez besoin de distribuer que le fichier LaTeX lui-même, plutôt qu'un ensemble de fichiers.

Très bien, supposons que nous ayons intégré d'une manière ou d'une autre une image codée dans le fichier LaTeX. Comment décoder cette image ? Malheureusement, nous ne pouvons pas le décoder directement en le lisant à partir du fichier LaTeX et en l'écrivant dans un fichier image externe. Au lieu de cela, la chaîne de texte qui représente l'image codée doit d'abord être écrite dans un fichier texte externe, qui peut ensuite être décodé pour générer le fichier image.

À ce stade, nous pouvons décrire les étapes suivantes pour atteindre le résultat souhaité :

1. Encodez l'image.
2. Insérez la chaîne de texte représentant les données d'image dans le fichier LaTeX.
3. Écrivez la chaîne de texte représentant les données d'image dans un fichier externe.
4. Décodez le fichier externe créé à l'étape 3.
5. Incluez l'image décodée.

Les deux premières étapes sont réalisées par l'auteur du fichier LaTeX. Le moteur TeX gérera les étapes restantes, à condition bien sûr qu'il soit correctement instruit.

Passons à l'**étape 1**. Comment encoder notre image pour obtenir une chaîne de caractères ? L'une des méthodes pour ce faire (et probablement la plus populaire) est **Base64**.

## Encodage de données binaires en Base64

[**Base64**](https://en.wikipedia.org/wiki/Base64) est un groupe de schémas de codage binaire en texte qui transforme les données binaires en une séquence de caractères imprimables, en utilisant un ensemble de 64 caractères uniques. Plus précisément, les données binaires sources sont traitées en groupes de 6 bits, chaque groupe étant mappé à l'un des 64 caractères uniques. Comme tous les systèmes de codage binaire en texte, Base64 est destiné à faciliter la transmission de données stockées au format binaire sur des canaux prenant principalement en charge le contenu textuel.

Cette brève explication montre que **Base64** est exactement ce dont nous avons besoin. Pour encoder un fichier image en **Base64**, vous pouvez utiliser un utilitaire de ligne de commande (si disponible sur votre système d'exploitation), des fonctionnalités standard ou tierces de presque tous les langages de programmation, ou des outils en ligne tels que [Base64.guru](https://base64.guru/converter/encode/file) ou similaire.

## Intégration de l'image codée dans le fichier LaTeX

La chaîne de caractères générée à partir du processus d'encodage doit être placée dans l'environnement standard LaTeX `filecontents` dans le préambule d'un fichier LaTeX, comme suit :

```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

C'est ici! **L'étape 2** est terminée. Nous avons intégré avec succès l'image dans le fichier LaTeX ! Mais que se passera-t-il lorsque nous lancerons la composition de ce fichier avec LaTeX ?"

Un processeur LaTeX écrira la chaîne de caractères de l'environnement dans un fichier externe nommé « sample-image.64 ». Grâce à l'option « écraser », le fichier sera écrasé s'il existe déjà (par exemple, s'il a été créé lors d'une exécution précédente). C'est ainsi que l'**Étape 3** est également accomplie !

## Décoder une chaîne base64

**L'étape 4** de notre plan est celle où les différences dans les implémentations de TeX entrent en jeu. Le décodage d'une chaîne de caractères Base64 est effectué au moyen d'une chose plus courante connue sous le nom de fonctionnalité `\write18`.

### `\write18`

Dans les moteurs TeX classiques, `\write<number>(<token list>)` est la primitive utilisée pour écrire une *liste de jetons*. Lorsqu'elle est utilisée, cette primitive est suivie d'un entier. Si l'entier est négatif, les jetons sont écrits dans le fichier de transcription (journal). Si l'entier est supérieur à « 15 », les jetons sont envoyés au terminal. Si l'entier est compris entre « 0..15 », les jetons sont écrits dans un fichier dont le nom est spécifié par une occurrence précédente de la primitive « \openout ». La primitive `\openout<4-bit integer>=<file name>` associe un nom de fichier à un numéro.

Les implémentations TeX plus récentes, telles que PDF TeX, permettent l'utilisation de `\write18`. Dans ce cas, ils interprètent la « <token list> » comme une ligne de commande à exécuter dans le shell du système d'exploitation. Étant donné que cette fonctionnalité présente évidemment un risque de sécurité potentiel, vous pourriez ressentir une touche de mystère chaque fois qu'elle est référencée dans la documentation relative à TeX ou sur Internet. Pour cette raison, les exécutables PDF TeX/LaTeX proposent des options de commande pour contrôler l'accès à cette fonctionnalité.

En règle générale, il existe trois niveaux d'accessibilité : désactivé, activé avec des restrictions et entièrement activé.

Dans **Aspose.TeX**, il existe une option de travail TeX appelée « ShellMode », qui peut prendre l'une des deux valeurs possibles : « NoShellEscape » et « ShellRestricted ». La valeur `NoShellEscape` indique que la fonctionnalité est désactivée. Cette dernière valeur signifie que toute commande nécessitant une exécution doit être implémentée par l'utilisateur en tant qu'extension de la classe `Executable`. Nous n'entrerons pas ici dans les détails de telles implémentations, mais il est important de noter que l'émulation de commande `base64` est déjà implémentée dans Aspose.TeX et est incluse par défaut dans la propriété de collection `Executables` de la classe `TeXOptions`. exemple.

### Décodage des données codées en Base64

Pour décoder le contenu d'un fichier censé contenir des données codées en Base64, nous utiliserions normalement la ligne de commande suivante :


```
base64 -d  FILE1 > FILE2
```

où FILE1 est le fichier « codé » et `> FILE2` redirige la sortie vers le fichier `FILE2`.

Par conséquent, nous devrions inclure la ligne suivante dans le corps de notre fichier LaTeX :


```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> Le préfixe `\immediate` est nécessaire pour garantir que l'opération `\write` est exécutée immédiatement lorsque le scanner TeX rencontre cette primitive. Sinon, elle sera traitée lors de l'envoi de la page.

Si nous exécutons la composition du fichier maintenant, nous constaterons que le fichier image `sample-image.png` a été créé. Allez-y et ouvrez-le dans une visionneuse pour vérifier !

## Y compris l'image décodée

Comme nous l'avons noté au début de l'article, pour inclure l'image décodée, nous utilisons la célèbre commande LaTeX `\includegraphics` :


```tex
\includegraphics[options]{sample-image.png}
```

Ainsi, le fichier LaTeX complet (presque) pourrait apparaître comme suit :


```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
  \write18{base64 -d  sample-image.64 > sample-image.png}
  \includegraphics[options]{sample-image.png}
\end{document}
```

Et le code Java utilisant l'API **Aspose.TeX** est similaire à ce que l'on peut trouver dans d'autres articles, à l'exception de la spécification de l'option de mode shell :

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-EmbeddedBase64EncodedImage.java" >}}

Et maintenant, l'**étape 5** est terminée. Pour des exemples vraiment complets, explorez notre [Exemple de projet](https://github.com/aspose-tex/Aspose.TeX-for-Java).

**Vous pouvez également consulter la conversion gratuite [application Web](https://products.aspose.app/tex/conversion/latex/) construite sur la base de [Aspose.TeX pour l'API .NET](https://products.aspose.com/tex/net/).**