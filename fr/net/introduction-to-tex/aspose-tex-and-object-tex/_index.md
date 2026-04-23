---
translation: true
template: /templates/_template-net.md
linktitle: Object TeX
title: Aspose.TeX et Object TeX 
weight: 11
url: /net/aspose-tex-and-object-tex/
description: TeX est un format d'entrée et de sortie de cette solution API, nous allons donc expliquer l'Object TeX et comment il est transformé en format cible.
lastmod: "2026-04-22"
---

{{<section overview>}}

## Object TeX

Considérons maintenant le format de sortie.

Le TeX original était capable de produire des fichiers uniquement au format *DVI* (DeVice Independent). Il est arrivé que le format DVI ne définisse pas les métriques d'un support sur lequel un fichier va être imprimé : la taille de la page et la position du coin supérieur gauche de l'ensemble du contenu de la page. Une fois que nous avons décidé de rendre le moteur TeX capable de produire des fichiers, par exemple au format PDF, nous devons définir de telles métriques. Ainsi, nous devons inclure de nouvelles primitives dans l'ensemble du moteur TeX d'origine. Et ce serait une extension du moteur lui-même.

C'est ce qu'est *Object* TeX. Encore une fois, **d'une part, il s'agit d'un langage de programmation avec l'ensemble de primitives de VirTeX, étendu avec de nouvelles primitives imposées par de nouvelles exigences de sortie. D'un autre côté, il s'agit d'un moteur TeX étendu qui comprend également les nouvelles primitives. Et, d'autre part, Object TeX est un tout nouveau système de composition.**

Il y a la quatrième main. Le format Object TeX est également un format basé sur Plain TeX qui contient des définitions qui impliquent de nouvelles primitives, par exemple attribuer des valeurs par défaut aux métriques multimédias.

## Aspose.TeX

Et Aspose.TeX n'est qu'une API du système Object TeX.

## Pourquoi le nouveau TeX est Object ?

Alors pourquoi avons-nous utilisé « Objet » dans le nom du système ? La raison en est que la sortie réelle du moteur Object TeX n'est pas un fichier au format de sortie, mais un modèle *objet* intermédiaire, qui est ensuite transformé en un format cible.