---
translation: true
template: /templates/_template-java.md
linktitle: Schéma de sélection des polices
title: Schéma de sélection des polices LaTeX
weight: 60
url: /java/latex-font-selection/
keywords: latex, polices latex, sélection de polices latex, nfss
description: Cet article décrit brièvement l'utilisation des polices LaTeX dans le traitement des documents. Il mentionne également les métriques de police TeX et les formes de caractères.
lastmod: "2024-09-27"
---

{{<section overview>}}


Lors du traitement du document source, le système de composition LaTeX n'a ​​pas beaucoup de connaissances sur la police qu'il utilise. Il calcule simplement les positions des personnages, sans avoir besoin de connaître les formes. Les informations les plus cruciales dont il a besoin sont les *boîtes noires* des personnages, qui sont définies par leurs largeurs, hauteurs et profondeurs. Ces dimensions sont stockées dans un fichier externe distinct appelé fichier de métrique de police TeX (`.tfm`) pour chaque police.

Les formes de personnages entrent en jeu plus tard. Si un système LaTeX produit un fichier `.dvi`, un programme *pilote* combine les données de placement des caractères du fichier `.dvi` avec des informations sur les formes de caractères du fichier `.pk` ou des descriptions de plan (telles que PostScript) pour produire l'image du personnage sur le support de sortie. Cependant, d'autres systèmes LaTeX comme **PDF TeX** ou **VTEX** contournent la production d'un fichier `.dvi` et génèrent directement une sortie **PDF** ou **PostScript**. Dans ce cas, les formes de caractères sont intégrées lorsque le formateur correspondant produit la sortie finale.