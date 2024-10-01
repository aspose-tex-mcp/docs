---
translation: true
template: /templates/_template-java.md
linktitle: Classes de documents LaTeX
title: Classes de documents LaTeX | Aspose.TeX pour Java
weight: 20
url: /java/latex-document-classes/
keywords: classe d'articles en latex, classe de documents en latex, modèle de document en latex, article en latex, livre en latex, diapositives en latex, rapport en latex, lettre en latex, classe de documents en latex
description: Cet article est un résumé concis des classes de documents LaTeX et de leurs options. Il fournit également quelques exemples.
lastmod: "2024-09-27"
---

{{<section overview>}}

## Qu’est-ce qu’une classe de documents dans LaTeX ?

LaTeX définit certaines règles que tout auteur de document doit suivre. Il définit également la structure du fichier source, qui est essentiellement un programme de composition. Selon cette structure, le code source du document doit contenir une partie responsable du contenu du document lui-même - *body* - qui est enfermée dans une paire de commandes : `\begin{document}` et `\end{document}`. LaTeX ignore tout ce qui suit la fin du corps. La partie du code source précédant `\begin{document}` est appelée le *préambule*.

En règle générale, la première commande du préambule doit être « \documentclass », qui prend un seul argument obligatoire qui est le nom de la **classe de document**. La classe de document elle-même est un ensemble de paramètres de formatage, de mesures de mise en page, de macros, etc. adaptés et utiles au développement de documents d'un certain type et rassemblés sous un nom unique. Dans cet article, nous discuterons des classes de documents LaTeX **prédéfinies** qui sont intégrées à LaTeX et montrerons leurs utilisations, différences et similitudes. Nous mentionnerons également quelques arguments facultatifs que la commande `\documentclass` peut prendre, et qui personnalisent l'apparence du document.

## Classes de documents LaTeX prédéfinies

Le LaTeX standard contient les classes de documents suivantes :

| <div style="text-align:center;">LaTeX<br>document<br>class</div> | <div style="text-align:center;">Usage</div> |
|---|---|
| **article** | La classe d'article LaTeX est utilisée pour créer des articles pour des revues scientifiques, des rapports courts, de la documentation de programme et en général tout document court qui ne nécessite pas une division complexe en chapitres et parties. |
| **report** | La classe de rapport LaTeX est utilisée pour les articles longs qui peuvent contenir plusieurs chapitres (quelque chose comme des petits livres et des thèses). |
| **book** | Elle est utilisée pour composer de vrais livres. Elle comprend toutes sortes de normes de composition adaptées aux livres imprimés : chapitres et parties, deux types de pages, matière de début, matière de fin, etc. |
| **slides** | Elle peut être utilisée pour produire des diapositives, bien qu'il existe le package externe [beamer](https://ctan.org/pkg/beamer) qui est beaucoup plus puissant à cet effet. |
| **letter** | Cette classe de document est utilisée pour écrire des lettres. |

Les deux premières classes de documents sont basiques. Alors, commencez par **article** chaque fois que vous n'êtes pas sûr du cours dont vous avez besoin.

La classe **report** est très similaire. La principale différence avec **article** est que vous pouvez insérer des chapitres avec la commande `\chapter`, alors que la classe de document **article** ne définit pas une telle unité de section.

## La classe LaTeX **livre**

Les livres, dans les normes typographiques, ont une partie avant et une partie arrière, qui constituent la principale différence entre les livres et, par exemple, les rapports ou les articles. La première page d'un livre se compose généralement d'une page de faux-titre, d'une page de titre principale, d'une page de droit d'auteur, d'une préface ou d'un avant-propos et d'une table des matières. Les parties moins obligatoires sont les remerciements, une dédicace, une liste de figures, une liste de tableaux, une liste d'autres livres de la même série et d'autres contenus éditoriaux et promotionnels. Le dossier comprend généralement un index et peut contenir une postface, ainsi que des remerciements, une bibliographie, un colophon, etc.

La classe de document livre vous propose des commandes pour produire les structures logiques susmentionnées, tandis que les autres classes de document ne peuvent pas vous fournir de tels outils. Cependant, différents éditeurs disposent généralement de leurs propres packages avec des commandes supplémentaires pour disposer les structures selon leur propre style.

## Commandes de sujet initial, principal et secondaire

L'essentiel est ce qui comprend le corps du livre, en commençant par le premier chapitre ou partie et en terminant par les annexes. Les éléments avant, principal et arrière commencent respectivement par les commandes `\frontmatter`, `\mainmatter` et `\backmatter`.

> Dans la classe de livre standard, les pages de couverture sont numérotées avec des chiffres romains, tandis que les pages principales et les pages de fin sont numérotées avec des chiffres arabes.

> La commande `\chapter` ne produit pas de numéro de chapitre dans les pages de couverture et de fin, bien qu'elle crée une entrée dans la table des matières. Elle est généralement utilisée pour créer une section de préface ou de remerciements. Dans de tels chapitres, seules les versions étoilées des autres commandes de sectionnement (comme `\section*` et `\subsection`) doivent être utilisées.

## Un exemple d'utilisation de la classe de livre LaTeX

```tex
% Book document class
\documentclass{book}

\title{My first book}
\author{Me}
\date{\today}

\begin{document}

\maketitle

\frontmatter
\chapter{Dedication}
\chapter{Copyright}
\chapter{Acknowledgements}

\tableofcontents

\listoffigures
\listoftables

\mainmatter
\part{The first part}
\chapter{Chapter one}
\chapter{Chapter two}

\part{Last part}
\chapter{Chapter three}

\appendix
\chapter{First and only appendix}

\backmatter
\chapter{Bibliography}
\chapter{Other titles in this collection}

\end{document}
```

Vous trouverez ci-dessous la structure du document généré par ce code LaTeX :

<a href="/tex/java/latex-document-classes/latex-document-classes-1.png" style="display:inline-block;width:49%;">![Exemple de sortie](/tex/images/java/tutorial/latex-document-classes-1.png) </a>

<a href="/tex/java/latex-document-classes/latex-document-classes-2.png" style="display:inline-block;width:49%;">![Exemple de sortie](/tex/images/java/tutorial/latex-document-classes-2.png) </a>

Et voici la table des matières en détail :

<a href="/tex/java/latex-document-classes/latex-document-classes-3.png">![Table des matières](/tex/images/java/tutorial/latex-document-classes-3.png)</a>

## Pages **impaires** et **paires** dans les livres
Dans les livres, les pages **impaires** et **paires** ne se ressemblent pas. Les marges, et généralement les en-têtes et pieds de page, diffèrent pour rendre le livre plus lisible une fois relié. La classe de document LaTeX gère cela, et vous constaterez peut-être que :

- Les pages **gauches (pairs)** ont une marge gauche plus grande, le numéro de page est en haut à droite de la page et le titre du chapitre en cours est à droite ;
- Les pages **droites (impaires)** ont une marge droite plus grande et uniquement le numéro de page en haut à droite de la page.

Notez que les nouveaux chapitres commencent toujours sur la page de droite, où l'en-tête de la page est vide, ne laissant que le numéro de page au centre du pied.

## La section **Résumé** est manquante

Les articles académiques, tels que les articles ou les rapports, comprennent généralement une section d'introduction appelée ** « Résumé » **. Son objectif est de donner un aperçu rapide du sujet abordé dans le document. Vous pouvez le trouver imprimé juste après le titre et avant la table des matières, avec le titre « Résumé » en gras. Dans LaTeX, une telle structure est implémentée sous le nom d'environnement « abstrait ».

L'environnement **abstract** n'est pas fourni par la classe de document book, et c'est une autre différence par rapport aux classes article et report.

## Classe LaTeX **lettre**

À l’heure actuelle, la classe des documents sous forme de lettres semble quelque peu démodée (tout comme la classe des documents sous forme de diapositives, en fait). Si vous avez besoin de réaliser des lettres traditionnelles, de les mettre sous enveloppe et de les envoyer par courrier, cette classe de documents vous sera probablement utile. Bien qu’il s’agisse d’un moyen de communication obsolète, il existe encore des cas où vous devrez peut-être préparer un document semblable à une lettre. Par exemple, une lettre de recommandation ou une lettre de présentation.

Voici donc un bref aperçu de la classe.

Vous pouvez générer n'importe quel nombre de lettres avec un seul fichier d'entrée. Votre nom et votre adresse, qui sont généralement les mêmes pour toutes les lettres, sont généralement spécifiés dans le préambule du document. L'adresse de retour est déclarée par une commande `\address`, qui accepte plusieurs lignes séparées par `\\` (la commande de saut de ligne LaTeX) comme argument. De même, la commande `\signature` accepte plusieurs lignes, y compris votre nom, votre titre, etc. Cependant, vous pouvez modifier l'adresse de retour et la signature à tout moment.

Chaque lettre est générée par un environnement de « lettre » distinct qui nécessite le nom et l'adresse du destinataire comme argument. La lettre commence par une commande `\opening`, produisant la salutation, et se termine par une commande `\closing`, produisant la phrase de clôture et la signature. Le corps de la lettre est une entrée LaTeX normale.

Toutes ces commandes sont faciles à utiliser et très puissantes car LaTeX se charge automatiquement du formatage des lettres. Alors ne vous laissez pas effrayer ou dérouter le nombre de commandes.

L'exemple ci-dessous montre comment tout cela fonctionne.

```tex
% Example of a letter document class
\documentclass{letter}
 
\address{1234 Heart Avenue\\ Thoraxland, 12555}

\signature{Dr.~Lung\\ Head of Department}

\begin{document}

\begin{letter}
{Dr.~Gallbladder \\ University of Digestion\\ 66 Liver Street\\ Abdomenia, 45888}

\opening{Appreciated Anything,}

I write you a letter, and this is the body of the
letter.

\closing{I look forward to your reply,}

\end{letter}

\end{document}
```

<a href="/tex/java/latex-document-classes/latex-document-classes-4.png">![Un exemple de classe de document de lettre](/tex/images/java/tutorial/latex-document-classes-4.png)</a>

Notez que la date actuelle est également produite automatiquement. Cependant, vous pouvez redéfinir la commande `\today` pour changer la date dans vos lettres. Voici comment procéder :

```tex
\renewcommand{\today}{01th of March of 2492}
```

Si vous insérez cette déclaration dans un certain environnement de « lettre », cela changera la date uniquement pour cette lettre. Sinon, si vous l'insérez dans le préambule, il sera en vigueur pour toutes les lettres générées par le fichier d'entrée (sauf s'il est inséré dans un certain environnement `lettre`).

## Options de classe de document LaTeX

Jetons maintenant un œil aux options de commande `\documentclass` mentionnées au début de l'article.

### Taille de la police

La taille de la police est contrôlée par trois options : 10 pt, 11 pt, 12 pt. Par défaut, 10pt est en vigueur. Ces options déterminent la taille de police de base utilisée dans tout le document, à moins qu'elle n'ait été modifiée à un moment donné. Ils affectent également les facteurs d’échelle pour certaines dimensions de formatage.

```tex
\documentclass[12pt]{article}
```

> Ces options ne sont pas reconnaissables par la classe `slides`.

### Format du papier
Le « format papier » fait ici référence au format de la feuille de papier sur laquelle vous **prévoyez** d'imprimer le document. Cela n'affecte pas la taille de la représentation de la page dans la sortie des systèmes de composition tels que **PDF TeX**. Il est contrôlé par 6 options : "letterpaper" (8,5 pouces x 11 pouces), "legalpaper" (8,5 pouces x 14 pouces), "executive paper" (7,25 pouces x 10,5 pouces), "a4paper" (210 mm x 297 mm), "a5paper". » (148 mm x 210 mm) et « papier b5 » (176 mm x 250 mm). La valeur par défaut est « papier à lettres ».

```tex
\documentclass[a4paper]{article}
```

### Orientation des pages

L'option « paysage » rend la sortie formatée pour une impression en mode paysage sur le format de papier sélectionné. En effet, cela permet à LaTeX d'échanger les dimensions de largeur et de hauteur partout où elles sont utilisées tout au long du processus de composition. L'option `portrait` n'a pas un tel effet et est utilisée par défaut.

```tex
\documentclass[landscape]{article} % landscape printing on the letterpaper
```

### Mode brouillon

Chaque fois que TeX ne parvient pas à faire un saut de ligne suffisamment bon (il dispose d'un algorithme d'estimation de « qualité ») au cours du processus de construction du paragraphe, il produit une ligne qui s'étend sur la bordure droite de la zone de texte. Il signale également de tels incidents dans le fichier de transcription (et sur le terminal) avec des avertissements « boîtes trop pleines ». L'option `draft` amène LaTeX à marquer ces lignes avec des cases noires dans la sortie. L'option `final` ne produit aucune boîte noire et est utilisée par défaut.

### Impression recto verso

L'option « openany » permet aux chapitres de commencer sur n'importe quelle page, tandis que l'option « openright » fait commencer tous les chapitres sur une page de droite. La valeur par défaut est « openany » dans la classe « report » et « openright » dans la classe « book ». Les deux options ne sont pas reconnues dans les autres classes de documents.

### Page pour le titre

Avec l'option `titlepage`, LaTeX crée une page séparée pour le titre produit par la commande `\maketitle`. Cela amène également l'environnement « abstrait » à démarrer le résumé sur une nouvelle page et à faire un saut de page après celui-ci. La valeur par défaut est `titlepage` pour toutes les classes sauf `article`, pour laquelle il s'agit de `notitlepage`. 

> Ces options ne sont pas reconnues par la classe `letter`.

### Formules affichées numérotées

L'option `leqno` permet à LaTeX de placer les numéros d'équation (formule mathématique affichée), ou les balises, sur le côté gauche, au lieu du côté droit, ce qui est le comportement par défaut.

### Alignement des formules affichées

L'option `fleqn` aligne les formules affichées vers la gauche. Sinon, ils sont centrés par défaut.
