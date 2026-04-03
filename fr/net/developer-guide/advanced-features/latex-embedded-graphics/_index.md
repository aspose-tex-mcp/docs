---
translation: true
template: /templates/_template-net.md
title: Inclure des graphiques dans le code LaTeX | .NET
linktitle: Graphiques intégrés LaTeX
weight: 18
url: /net/latex-embedded-graphics/
keywords: includegraphics latex, graphiques latex embed base64, graphiques codés latex base64, write18, shell-escape, commande shell latex
description: Cet article explique comment inclure des images codées en base64 dans le code source de LaTeX, ainsi que la fonctionnalité \write18 qui rend cela possible.
lastmod: "2026-04-03"
---

{{<section overview>}}

## Une autre façon d'inclure des images

Certains systèmes TeX/LaTeX permettent d'inclure des images qui ne sont pas stockées en externe par rapport au fichier LaTeX lui-même, mais plutôt incluses directement dans le fichier LaTeX. Cependant, comme les fichiers TeX/LaTeX sont des fichiers texte brut et ne peuvent donc pas contenir de données binaires, nous avons besoin d'un moyen de représenter les données binaires sous forme de texte. En d’autres termes, les données binaires doivent être codées dans une représentation textuelle. Le problème est qu’un moteur TeX ne peut pas interpréter directement de telles images codées. En fait, l'inclusion d'une image se fait à l'aide de la bonne vieille commande `\includegraphics` du package `graphicx`. Cependant, cette commande ne peut traiter que les fichiers image externes. Oui, un fichier image externe (ainsi qu'un autre fichier intermédiaire) sera toujours créé en dehors du fichier LaTeX. Le point clé est qu’il vous suffit de distribuer le fichier LaTeX seul.

D'accord, disons que nous avons placé d'une manière ou d'une autre une image codée dans le fichier LaTeX. Mais comment décoder l’image ? Malheureusement, nous ne pouvons pas décoder le fichier en le lisant à partir du fichier LaTeX et en l'écrivant dans le fichier image externe. La chaîne de texte représentant l'image codée doit d'abord être écrite dans un fichier texte externe, qui peut ensuite être décodé pour produire un fichier image.

À présent, nous pouvons décrire les étapes suivantes pour obtenir le résultat souhaité :

1. Encodez l'image.
2. Injectez la chaîne de texte représentant les données d'image dans le fichier LaTeX.
3. Générez la chaîne de texte représentant les données d'image dans un fichier externe.
4. Décodez le fichier externe de l'étape 3.
5. Incluez l'image décodée.

Les deux premières étapes sont complétées par l'auteur du fichier LaTeX. Un moteur TeX se chargera des étapes restantes, à condition bien sûr qu’il soit correctement instruit.

Commençons par le tout début. Comment encoder notre image pour obtenir une chaîne de caractères ? L'une des méthodes pour ce faire (et probablement la plus populaire) est **Base64**.

## Encodage de données binaires en Base64

[**Base64**](https://en.wikipedia.org/wiki/Base64) est un groupe de schémas de codage binaire en texte qui transforme les données binaires en une séquence de caractères imprimables, limitée à un ensemble de 64 caractères uniques. Plus précisément, les données binaires sources sont prises 6 bits à la fois, puis ce groupe de 6 bits est mappé sur l'un des 64 caractères uniques. Comme pour tous les schémas de codage binaire vers texte, **Base64** est conçu pour transporter les données stockées au format binaire sur des canaux qui ne prennent en charge de manière fiable que le contenu textuel.

Nous pouvons voir à partir de cette courte explication que **Base64** est ce dont nous avons besoin. Pour encoder un fichier image en **Base64**, vous pouvez utiliser un utilitaire de ligne de commande (si disponible sur votre système d'exploitation), des fonctionnalités standard ou tierces de presque tous les langages de programmation, ou des outils en ligne tels que [Base64.guru](https://base64.guru/converter/encode/file) ou similaire.

## Placer l'image codée dans le fichier LaTeX

La chaîne de caractères que vous obtenez suite à l'encodage doit être placée dans l'environnement standard LaTeX `filecontents` dans le préambule d'un fichier LaTeX comme suit :


```tex
\documentclass{article}
\begin{filecontents*}[overwrite]{sample-image.64}
iVBORw0KGgoAAAANSUhEUgAAAPgAAABdCAYAAAH/B5vAAAAAGXRFWHRTb2Z0d2FyZQBBZ......
\end{filecontents*}
\begin{document}
...
\end{document}
```

C'est ici. L'étape 2 est accomplie. Nous avons l'image dans le fichier LaTeX ! Mais que se passera-t-il lorsque nous lancerons la composition de ce fichier avec LaTeX ?

Un processeur LaTeX écrira la chaîne de caractères de l'environnement dans un fichier externe nommé « sample-image.64 ». En raison de l'utilisation de l'option « écraser », le fichier sera écrasé s'il existe déjà (par exemple, s'il a été produit lors d'une exécution précédente). Et c’est également ce qui accomplit l’étape 3 !

## Décoder une chaîne base64

L'étape 4 de notre plan est celle où les différences dans les implémentations de TeX entrent en jeu. Le décodage d'une chaîne de caractères Base64 se fait au moyen d'une chose plus courante connue sous le nom de fonctionnalité `\write18`.

### `\write18`

Dans les moteurs TeX classiques, `\write<number>(<token list>)` est la primitive qui écrit une *liste de jetons*. Lorsqu'elle est utilisée, cette primitive est suivie d'un entier. Si ce nombre est négatif, les jetons sont écrits dans le fichier de transcription (journal). Si le nombre est supérieur à « 15 », les jetons sont écrits sur le terminal. Si le nombre est compris entre « 0..15 », les jetons sont écrits dans un fichier dont le nom est spécifié par une occurrence précédente de la primitive « \openout ». La primitive `\openout<4-bit integer>=<file name>` mappe un nom de fichier à un nombre.

Les implémentations TeX plus récentes (telles que PDF TeX) permettent l'utilisation de `\write18`. Dans ce cas, ils interprètent la « <token list> » comme une ligne de commande à exécuter dans le shell du système d'exploitation. Étant donné que cette fonctionnalité est évidemment une porte dérobée potentielle, vous pourriez ressentir une touche de mystère chaque fois qu'elle est mentionnée dans la documentation relative à TeX ou sur Internet. Pour cette raison, les exécutables PDF TeX/LaTeX disposent d'options de commande pour gérer l'accessibilité de cette fonctionnalité.

Généralement, il existe trois niveaux d'accessibilité : désactivé, activé avec des restrictions et entièrement activé.

Dans **Aspose.TeX**, il existe une option de travail TeX appelée « ShellMode », mais il n'y a que deux valeurs appropriées : « NoShellEscape » et « ShellRestricted ». La valeur `NoShellEscape` signifie que la fonctionnalité est désactivée. La deuxième valeur indique que toute commande qui doit être exécutée doit être implémentée par l'utilisateur en tant qu'extension de la classe « Executable ». Ici, nous n'entrerons pas dans les détails de telles implémentations, mais nous mentionnerons que l'émulation de commande « base64 » est déjà implémentée dans Aspose.TeX. Par défaut, vous pouvez trouver son instance prototype dans la propriété de collection `Executables` de l'instance de classe `TeXOptions`.

### Décodage des données codées en Base64

Pour décoder le contenu d'un fichier censé être des données codées en Base64, nous utiliserions normalement la ligne de commande suivante :


```
base64 -d  FILE1 > FILE2
```

où FILE1 est le fichier « codé » et `> FILE2` signifie que la sortie doit être redirigée vers le fichier `FILE2`.

Ainsi, dans le corps de notre fichier LaTeX, nous devrions ajouter la ligne suivante :


```tex
\immediate\write18{base64 -d  sample-image.64 > sample-image.png}
```

> Le préfixe `\immediate` est nécessaire pour garantir que l'opération `\write` est exécutée dès que la commande primitive est rencontrée par le scanner TeX. Sinon, elle sera traitée au moment de l'envoi de la page.

Si nous exécutons la composition du fichier maintenant, nous verrons que le fichier image `sample-image.png` est créé. Allez, ouvrez-le dans une visionneuse pour vérifier !

## Y compris l'image décodée

Comme nous l'avons mentionné au début de l'article, pour inclure l'image décodée, nous utilisons la célèbre commande LaTeX `\includegraphics` :


```tex
\includegraphics[options]{sample-image.png}
```

Ainsi, le fichier LaTeX complet (presque) pourrait ressembler à ceci :


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

Et le code C# utilisant l'API **Aspose.TeX** est similaire à celui d'autres articles, à l'exception de la spécification de l'option `ShellMode` :

{{< gist "aspose-com-gists" "7f54d335270200ebf5987d071bad028a" "Examples_LaTeXEmbeddedBase64EncodedImage" >}}

Et maintenant, nous en avons terminé avec l'**étape 5**. Pour des exemples vraiment complets, explorez notre [Exemple de projet](https://github.com/aspose-tex/Aspose.TeX-for-.NET).

**Vous pouvez également consulter la conversion gratuite [application Web](https://products.aspose.app/tex/conversion/latex/) construite sur la base de [Aspose.TeX pour l'API .NET](https://products.aspose.com/tex/net/).**
