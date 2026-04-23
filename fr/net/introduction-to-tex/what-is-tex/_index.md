---
translation: true
template: /templates/_template-net.md
title: Qu’est-ce que TeX ? 
linktitle: Qu’est-ce que TeX ?
weight: 10
url: /net/what-is-tex/
keywords: qu'est-ce que TeX
description: Cette page répond à la question "Qu'est-ce que TeX ?" Est-ce un langage de programmation ou un format de document ?
lastmod: "2026-04-22"
---

{{<section overview>}}

## Ce que TeX n'est PAS

TeX n'est définitivement pas un format du tout.

## Qu’est-ce que TeX ?

Alors, qu’est-ce que TeX ? Eh bien, telle est la question, comme le disait Hamlet[^1]. Essayons d'y répondre le plus simplement possible.

Imaginez que nous ayons un langage de programmation composé de deux commandes élémentaires (appelées *séquences de contrôle*), ou *primitives*, `\a` et `\b`. Et dans ce langage, nous pouvons écrire des programmes pour la composition de documents (livres, articles, etc.). Appelons ce langage **(L1)**. Pour que ces programmes soient exécutés d’une certaine manière, nous disposons d’un certain moteur qui interprète les commandes de ce langage.

Supposons maintenant que lors de l'écriture d'un programme de composition pour un document, nous ayons constaté que la sous-séquence `\a \b \a` apparaît assez fréquemment. Et supposons également que dans notre langage il existe une autre primitive `\def`, qui nous permet de définir des sous-programmes, ou macros. Appelons ce langage **(L2)**. Dans ces circonstances, nous pouvons définir la macro `\def\c{\a \b \a}` au début du programme et remplacer chaque occurrence de la sous-séquence par `\c` à la fois pour une meilleure lisibilité et réduction.

Maintenant, si nous voulons composer un autre document, dans le programme duquel cette sous-séquence de commandes apparaît également fréquemment, nous devrons définir à nouveau cette macro. Mais supposons que notre moteur soit capable de charger la macro `\c` dans son état interne, puis de sauvegarder cet état sous forme de fichier binaire (un *dump*), qui sera ensuite automatiquement chargé ("au-dessus" du **(L2)** jeu de commandes de langage) avant de traiter les programmes de composition de chaque document dans lequel la macro `\c` est requise. Nous appellerons l'ensemble des primitives étendues par la macro `\c` un *format*. Ainsi, notre format est une *macroextension* du langage primitif de bas niveau **(L2)**.

Le moteur contient également un certain nombre de registres internes, ou *paramètres internes*, accessibles à l'aide de séquences de contrôle. En plus des définitions de macro, un format peut contenir des expressions d'initialisation pour ces paramètres.

Il est arrivé que <a href="https://en.wikipedia.org/wiki/Donald_Knuth" target=_blank rel="nofollow">Donald E. Knuth</a> ait défini un langage similaire à **(L2) **, mais avec un ensemble de primitives beaucoup plus large, qu'il a appelé TeX. Il a également créé un moteur qui comprenait (et comprend toujours) le langage TeX. Il l'a également appelé TeX.

Heureusement, ce n’était pas la seule chose qu’il faisait. Il a également proposé l'extension macro, ou format, qu'il a appelé *Plain* TeX, qui rendait l'écriture de programmes plus pratique. L'ensemble initial des primitives de TeX est parfois appelé VirTeX (« Vir » pour « vierge ») et, formellement, est également un format, lorsqu'il est considéré avec les valeurs par défaut des paramètres internes.

**Donc, d'une part, TeX EST un langage de programmation. Et d’un autre côté, c’est un moteur d’interprétation qui comprend ce langage. Et, d'autre part, TeX est un concept plus général désignant un système de composition dans son ensemble.**

La seule chose qui reste à noter ici est qu'en fait, les caractères du texte en cours de composition sont également des commandes qui forcent le moteur TeX à saisir les caractères correspondants (en tenant compte de l'encodage d'entrée actuel) en utilisant les paramètres de police actuels (qui, à leur tour, sont contrôlables par des séquences de contrôle). Ainsi, lors de la définition des macros, nous pouvons également utiliser des caractères.

Nous espérons que désormais la question « Qu'est-ce que TeX ? » n'existe plus dans votre esprit.
[^1]: Le personnage de "The Tragical Historie of Hamlet, Prince of Denmarke" de W. Shakespeare.