---
translation: true
template: /templates/_template-java.md
linktitle: AMS-LATEX
title: 1. Introduction à AMS-LATEX 
weight: 10
url: /java/introduction-to-ams-latex/
keywords: ams-latex, amsmath, options amsmath, amsopn, amstext, amscd, amsthm, amsxtra, upref
description: Cet article est une brève introduction au package amsmath et couvre brièvement ses options ainsi que les sous-packages et extensions disponibles.
lastmod: "2024-09-27"
---

{{<section overview>}}


La version 1.0 de *AMS*-LATEX a été publiée en 1990 et présentait la conversion originale vers LaTeX des capacités mathématiques de *AMS*-TEX de Michael Spivak par Frank Mittelbach et Rainer Schopf, qui ont travaillé comme consultants auprès de *AMS*, avec l'aide de Michael Downes de l'équipe technique *AMS*. En 1994, la poursuite du travail a été réalisée avec David M. Jones.

Le package *Amsmath* accepte quelques options qui affectent principalement le positionnement des *limites* sur divers opérateurs mathématiques ou le positionnement des balises d'équation.

## Options de forfait *amsmath* disponibles

Les trois options suivantes peuvent être utilisées comme options globales de document (spécifiées dans la commande `\documentclass`) ou comme options du package *amsmath* lorsqu'il est chargé avec la commande `\usepackage`.

|||
|---|---|
| `reqno` **(par défaut)** | Placer les numéros d'équation (balises) à droite. |
| `leqno` | Placer les numéros d'équation (balises) à gauche (par défaut, lors de l'utilisation des classes de document *AMS*-LATEX). |
| `fleqn` | Positionner les équations à un retrait fixe par rapport à la marge gauche plutôt qu'au centre de la colonne de texte. |

## Sous-packages disponibles

Dans la distribution *AMS*-LATEX, vous pouvez également trouver des composants qui peuvent être chargés indépendamment par la commande `\usepackage`. Les petits packages suivants fournissent certaines fonctionnalités du package *amsmath* :

|||
|---|---|
| `amsopn` | Fournit `\DeclareMathOperator` pour définir de nouveaux noms d'opérateurs tels que `\Ker` et `\esssup`. |
| `amstext` | Fournit la commande `\text` pour composer un fragment de texte dans la taille de police correcte. |

## Forfaits d'extension

Les packages répertoriés ci-dessous fournissent des fonctionnalités supplémentaires et doivent être chargés explicitement.

|||
|---|---|
| `amscd` | Définit certaines commandes pour faciliter la génération de diagrammes commutatifs. |
| `amsthm` | Fournit une méthode pour déclarer des structures de type théorème et offre un environnement `proof`. |
| `amsxtra` | Fournit certains éléments nécessaires à la compatibilité historique, tels que `\fracwithdelims`, `\accentedsymbol` et des commandes pour placer des accents en exposants. |
| `upref` | Fait en sorte que `\ref` imprime les numéros de référence croisée dans une police droite/romaine quel que soit le contexte. |