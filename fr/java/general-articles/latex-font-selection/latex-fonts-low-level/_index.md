---
translation: true
template: /templates/_template-java.md
linktitle: 5. Interface de bas niveau
title: L'interface de bas niveau
weight: 50
url: /java/latex-fonts-low-level/
keywords: latex, polices latex, substitution de polices latex, familles de polices latex, séries de polices latex, formes de polices latex
description: Cet article couvre l'interface de police de bas niveau LaTeX qui est principalement utilisée dans les définitions de commandes.
lastmod: "2024-09-27"
---

{{<section overview>}}

Contrairement aux commandes de polices de haut niveau, destinées à être utilisées dans un document, les commandes de bas niveau servent principalement à définir de nouvelles commandes dans les packages ou dans le préambule du document. Pour tirer le meilleur parti de ces commandes, il est utile de comprendre l’organisation interne des polices dans le système de sélection de polices (NFSS) de LaTeX.

D'une part, l'objectif du système de sélection de polices de LaTeX est de permettre une sélection rationnelle des polices avec des algorithmes guidés par les principes du balisage générique. À cette fin, il serait souhaitable d’autoriser des modifications indépendantes sur autant d’attributs de police que possible. D’un autre côté, les familles de polices dans la vie réelle ne contiennent normalement qu’un sous-ensemble de la myriade de combinaisons d’attributs de police imaginables. Ainsi, autoriser des modifications indépendantes dans trop d'attributs entraîne un trop grand nombre de combinaisons pour lesquelles aucune véritable police externe n'est disponible, et une valeur par défaut doit être remplacée.

En interne, LaTeX garde la trace de cinq attributs de police indépendants : le *codage actuel*, la *famille actuelle*, la *série actuelle*, la *forme actuelle* et la *taille actuelle*. L'attribut de codage a été introduit dans la version 2 de NFSS lorsqu'il est devenu clair que la prise en charge de plusieurs langues ne serait pas possible sans maintenir le schéma de codage des caractères indépendamment des autres attributs de police.

Les valeurs de ces attributs déterminent la police actuellement utilisée. LaTeX gère également un large ensemble de tables utilisées pour associer des combinaisons d'attributs à des polices externes (c'est-à-dire des fichiers « .tfm » qui contiennent les données requises pour que LaTeX fasse son travail). La sélection des polices se fait ensuite en deux étapes :

1. Un certain nombre d'attributs de police sont modifiés à l'aide des commandes de bas niveau `\fontencoding`, `\fontfamily`, `\fontseries`, `\fontshape` et `\fontsize`.

2. La police correspondant à ces nouveaux paramètres d'attribut est sélectionnée en appelant la commande `\selectfont`.

La deuxième étape consiste en plusieurs actions. Tout d'abord, LaTeX vérifie si la police correspondant aux paramètres d'attribut souhaités est connue du système (c'est-à-dire que le fichier « .tfm » est déjà chargé), et si c'est le cas, cette police est sélectionnée. Sinon, les tables internes sont recherchées pour trouver le nom de police externe associé à ces paramètres. Si un tel nom de police est trouvé, le fichier `.tfm` correspondant est lu en mémoire, puis la police est sélectionnée pour la composition. Si le nom de la police n'est pas trouvé, LaTeX essaie de trouver une police alternative, comme expliqué plus loin dans cet article.


## 5.1. Définition d'attributs de police individuels

Il existe une commande pour chaque attribut de police permettant de modifier sa valeur actuelle. Toutes ces commandes acceptent plus ou moins n'importe quelle chaîne de caractères comme argument, mais seules quelques valeurs ont du sens. Ces valeurs ne sont pas intégrées au NFSS, mais sont plutôt des conventions définies dans les tableaux internes. Les sections suivantes présentent les conventions de dénomination utilisées dans la configuration standard de LaTeX, mais n'importe qui peut modifier cette configuration en ajoutant de nouvelles déclarations de polices dans les tables internes. Normalement, toute personne créant de nouvelles polices à utiliser avec LaTeX devrait essayer de respecter ces conventions autant que possible, car seule une convention de dénomination cohérente peut garantir que les polices appropriées sont sélectionnées dans un document balisé de manière générique.

Si vous souhaitez sélectionner une police spécifique à l'aide de cette interface - par exemple, Computer Modern Dunhill bold condensed italic 14pt - la connaissance des conventions de l'interface seule ne suffit pas puisqu'il n'existe aucune police externe pour chaque combinaison de valeurs d'attribut. Vous pouvez essayer de spécifier quelque chose comme ce qui suit :

```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{bc}\fontshape{it}%
\fontsize{14}{16pt}\selectfont
```

Ce code serait correct selon les conventions de dénomination, comme nous le verrons ci-dessous. Cependant, étant donné que cette combinaison d'attributs ne correspond pas à une police réelle, LaTeX devrait la remplacer par une police différente. Le mécanisme de substitution peut choisir une police très différente de celle souhaitée, vous devez donc consulter les tables de polices pour vérifier si la combinaison souhaitée est disponible. Voici plus de détails sur le [processus de substitution de police](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/#53-automatic-substitution-of-fonts).

### Choisir la famille de polices

La famille de polices est sélectionnée par la commande `\fontfamily`. Comme argument, il prend une chaîne de caractères faisant référence à une famille de polices déclarée dans les tables internes. La chaîne de caractères a été définie lors de la création de ces tables et est généralement une courte séquence de lettres - par exemple, `cmr` pour la famille Computer Modern Roman. Les noms de famille ne doivent pas comporter plus de cinq lettres, car ils seront combinés avec éventuellement trois lettres supplémentaires pour former un nom de fichier qui, sur certains systèmes, peut contenir au maximum huit lettres.

### Choisir la série de polices

La commande `\fontseries` modifie l'attribut series. La série combine un poids et une largeur dans son argument, ce qui signifie qu'il est impossible de modifier la largeur de la police courante indépendamment de son poids. Ceci est acceptable car il est peu probable qu’il soit nécessaire de modifier le poids ou la largeur individuellement. Au contraire, un changement de poids s'accompagne souvent d'un changement de largeur dans les spécifications du concepteur. Ce n’est pas vraiment une surprise puisque les changements de poids modifient l’apparence horizontale des lettres et nécessitent donc des ajustements dans l’expansion (largeur) pour produire un aspect bien équilibré.

Les noms du poids et de la largeur sont abrégés dans les noms de séries, de sorte que chaque combinaison soit unique. Ces conventions de dénomination sont présentées dans le tableau ci-dessous. Toute instance de « m » (qui signifie moyen en poids ou en largeur) est omise, sauf lorsque le poids et la largeur sont moyens, auquel cas un seul « m » est utilisé. Par exemple, le gras développé serait « bx », tandis que le moyen développé serait « x » et le gras moyen serait « b ».

![Conventions de dénomination des séries de polices](/tex/images/java/tutorial/latex-font-selection-5-1.png)

### Choisir la forme de la police

La commande `\fontshape` modifie l'attribut de forme. Pour les formes standard, des abréviations à une ou deux lettres sont utilisées. Ces formes sont répertoriées dans le tableau ci-dessous :

![Conventions de dénomination des formes de police](/tex/images/java/tutorial/latex-font-selection-5-2.png)

### Choisir la taille de la police

La commande `\fontsize{<size>}{<skip>}` modifie la taille de la police. Il faut deux arguments : le `<size>` vers lequel basculer et la ligne de base `<skip>` (la distance entre les lignes de base pour cette taille). Les tailles de police sont normalement mesurées en points, donc par convention, l'unité est omise. Il en va de même pour le deuxième argument. Cependant, si le saut de ligne de base doit être une longueur élastique, vous devez spécifier une unité. Par conséquent, un changement de taille valide pourrait être demandé par


```tex
\fontsize{14.4}{17}\selectfont
```

Même si une telle demande est valide, il se peut qu'il n'y ait pas de police externe correspondante dans cette taille. Dans un tel cas, LaTeX tentera de trouver une taille proche si ses tables internes permettent une correction de taille ou signalera une erreur dans le cas contraire.

Si vous utilisez des polices existant dans des tailles arbitraires, vous pouvez bien sûr sélectionner la taille de votre choix :


```tex
\fontsize{1in}{1.2in}\selectfont A text in an arbitrary font size
```

### Choisir l'encodage

La commande `\fontencoding` est utilisée pour changer l'encodage. L'argument est le nom interne de l'encodage souhaité. Ce nom doit être connu de LaTeX, soit comme l'un des encodages prédéfinis (chargés par le noyau), soit comme déclaré avec la commande `\DeclareFontEncoding`. Voici plus d'informations sur la [déclaration des encodages de polices](/tex/{{lang.url-fragment}}java/latex-fonts-setup/#64-how-to-declare-a-new-font-encoding-scheme). Les noms d’encodage de police standard sont répertoriés dans le tableau ci-dessous :

![Noms d'encodage de police standard](/tex/images/java/tutorial/latex-font-selection-5-3.png)
NFSS repose sur l'hypothèse que la plupart (ou mieux, toutes) les polices du texte sont disponibles dans le même codage tant qu'elles sont utilisées pour la composition dans la même langue. En d’autres termes, des modifications d’encodage ne devraient être nécessaires que si vous passez d’une langue à une autre. Dans ce cas, les packages de support linguistique (par exemple, du système `babel`) sont normalement censés s'occuper des encodages en coulisses.

Dans l'exemple suivant, nous modifions l'encodage manuellement en définissant un environnement `Cyr` pour la composition en cyrillique. Dans cet environnement, le codage de la police et le codage d'entrée sont modifiés localement. Bien entendu, pour une prise en charge linguistique appropriée, des travaux supplémentaires seraient nécessaires, comme la modification des règles de césure. Les encodages sont déclarés à LaTeX en les chargeant avec le package `fontenc`. « T2A » spécifie l'un des codages cyrilliques standard. `T1` devient l'encodage par défaut puisqu'il est chargé en dernier.

![Encondings exemple de code source](/tex/images/java/tutorial/latex-font-selection-5-4.png)

![Exemple de sortie d'encondings](/tex/images/java/tutorial/latex-font-selection-5-5.png)

Malheureusement, « T1 » ne peut pas être entièrement implémenté pour la plupart des polices PostScript. Cinq caractères dans l'exemple suivant sont susceptibles d'être affichés sous forme de taches d'encre, indiquant des glyphes manquants dans la police. Notez que les symboles « pour mille » et « pour dix mille » sont en fait formés en joignant un signe de pourcentage et un ou deux petits zéros supplémentaires ; seul ce dernier glyphe manque.


```tex
\usepackage[T1]{fontenc}
-----------------------------------------
\fontfamily{cmr}\selectfont
\j{} \ng{} \NG{} \textperthousand{}\textpertenthousand \par
\fontfamily{ptm}\selectfont
\j{} \ng{} \NG{} \textperthousand{}\textpertenthousand{}

```

![T1 pour les polices PostScript](/tex/images/java/tutorial/latex-font-selection-5-5.png)

## 5.2. Définition de plusieurs attributs de police

Lors de la conception de styles de page ou de commandes orientées mise en page, vous souhaitez souvent sélectionner une police particulière, c'est-à-dire que vous devez spécifier des valeurs pour tous les attributs. Pour cela, LaTeX fournit la commande `\usefont`, qui prend quatre arguments : l'encodage, la famille, la série et la forme. La commande met à jour ces attributs puis appelle `\selectfont`. Si vous souhaitez également spécifier la taille et le saut de ligne de base, placez une commande `\fontsize` avant `\usefont`. Par exemple,


```tex
\fontsize{14}{16pt}\usefont{OT1}{cmdh}{bc}{it}
```

produirait le même résultat que les commandes suivantes :


```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{bc}\fontshape{it}%
\fontsize{14}{16pt}\selectfont
```

LaTeX fournit également la déclaration `\DeclareFixedFont`, qui peut être utilisée pour définir de nouvelles commandes qui basculent vers une police complètement fixe. De telles commandes sont très rapides car elles ne nécessitent pas de recherche de tables internes. Par conséquent, ils sont très utiles dans les définitions de commandes qui doivent basculer entre les polices. Par exemple, si nous voulons déclarer une commande pour composer certains textes en taille de script, nous pouvons le faire comme suit :


```tex
\DeclareFixedFont\ScriptSizeFont{\encodingdefault}{\familydefault}
    {\seriesdefault}{\shapedefault}{7pt}
\newcommand\theScript[1]{{\ScriptSizeFont #1}}
```

Vous pouvez voir que `\DeclareFixedFont` a six arguments. Le nom de la commande à définir est suivi des cinq attributs de police dans les classifications NFSS. Au lieu de transmettre des valeurs fixes (sauf pour la taille), les hooks intégrés qui décrivent la police principale du document sont utilisés. Par conséquent, dans l'exemple ci-dessus, `\ScriptSizeFont` dépend toujours de la présentation globale du document. Cependant, une fois la définition exécutée, sa signification est figée, donc les modifications ultérieures des valeurs par défaut ne modifieront pas la police `\ScriptSizeFont`.

## 5.3. Substitution automatique des polices

Lorsqu'une demande de changement de police ne peut pas être effectuée car la combinaison n'est pas connue de LaTeX, il tente de la récupérer en utilisant une police avec des attributs similaires. Voici ce qui se passe en détail : si la combinaison du schéma d'encodage, de la famille, de la série et de la forme n'est pas déclarée, LaTeX essaie de trouver une combinaison connue en changeant d'abord l'attribut de forme par défaut. Si la combinaison résultante est encore inconnue, il essaie de modifier la série par défaut. En dernier recours, la famille prend une valeur par défaut. Enfin, il recherche l'entrée du tableau interne pour trouver la taille demandée. Par exemple, si vous demandez `\ttfamily\bfseries\itshape` - une police de machine à écrire en série grasse et en italique (qui n'existe généralement pas) - alors vous obtiendrez une police de machine à écrire en série moyenne et de forme verticale car LaTeX est d'abord réinitialise la forme avant de réinitialiser la série. Dans un tel cas, si vous préférez une police de machine à écrire avec une forme italique, vous devez annoncer vos préférences à LaTeX à l'aide de la fonction `sub`, qui est expliquée dans l'article [Comment configurer de nouvelles polices](/tex/{{lang.url-fragment}}java/latex-fonts-setup/).

Le processus de substitution ne modifie jamais le schéma de codage car toute modification peut produire des caractères incorrects dans la sortie. Comme vous vous en souviendrez peut-être, le schéma de codage définit comment interpréter les caractères d'entrée, tandis que les autres attributs définissent l'apparence de la sortie. Par conséquent, il ne serait pas approprié que, par exemple, le signe dièse soit remplacé par le signe dollar dans un contrat simplement parce que le logiciel s’est efforcé d’être intelligent.

Ainsi, chaque schéma de codage doit avoir une famille, une série et une forme par défaut, et au moins la combinaison constituée du schéma de codage avec les valeurs par défaut correspondantes doit avoir une définition dans LaTeX.

## 5.4. Comment utiliser les commandes de bas niveau dans le document

Les commandes de bas niveau décrites dans les sections précédentes sont destinées à être utilisées dans les définitions de commandes de haut niveau, soit dans les fichiers de classe ou de package de document, soit dans le préambule du document.

Si vous pouvez utiliser des commandes de haut niveau comme `\textsf`, vous devez éviter autant que possible d'utiliser les commandes de bas niveau directement dans le document. La raison en est que les commandes de bas niveau sont des instructions très précises pour passer à une police particulière, alors que les commandes de haut niveau peuvent être personnalisées à l'aide de packages ou de déclarations dans le préambule. Supposons que vous ayez sélectionné Computer Modern Sans dans votre document en utilisant `\fontfamily{cmss}\selectfont`. Si vous décidez plus tard de composer l'ensemble du document avec les polices du bundle PSNFSS - par exemple Times - l'application d'un package ne modifiera que les parties du document qui ne contiennent pas de commandes explicites `\fontfamily`.