---
translation: true
template: /templates/_template-python-net.md
title: Fonctionnalité de conversion | Aspose.TeX pour Python via .NET
linktitle: Conversion
weight: 10
url: /python-net/conversion/
description: La fonctionnalité de conversion de la solution API Aspose.TeX pour Python prend en charge les prochains formats de sortie TeX, XPS, PDF, PNG, JPEG, TIFF et PNG.
lastmod: "2024-09-27"
---

{{<section overview>}}

Si vous avez déjà parcouru le contenu de ["Introduction to TeXs"](/tex/{{lang.url-fragment}}net/introduction-to-tex/), vous avez peut-être remarqué que les termes *convert* et *conversion* ne sont pas entièrement adaptés au contexte de TeX, car le processus de composition d'un Le fichier TeX n'implique pas de mappage d'un format à un autre. Cependant, conformément à la tradition et aux préférences de l'utilisateur, nous autorisons l'utilisation de ces termes et, dans cette partie, nous les utiliserons lorsqu'ils seront le plus appropriés. De plus, nous pouvons occasionnellement utiliser les mots *transform* et *transformation*.

Les chapitres de cette partie fourniront une présentation étape par étape des capacités de conversion de **Aspose.TeX pour Python**, en commençant par des scénarios d'utilisation de base pour les formats de sortie les plus couramment utilisés et en terminant par des options de personnalisation avancées. Compte tenu de la prévalence des [fichiers LaTeX](/tex/{{lang.url-fragment}}net/latex-io/#latex-file) par rapport aux autres formats TeX, nous nous concentrerons sur la conversion des fichiers LaTeX plutôt que des fichiers TeX. Cependant, nous aborderons brièvement la conversion de fichiers TeX plus tard.

Il convient de mentionner que le support LaTeX d'Aspose.TeX englobe tous les fichiers du système LaTeX de base ainsi que les fichiers des [paquets les plus courants](/tex/{{lang.url-fragment}}net/embedded-packages/), y compris « amsmath », « géométrie », « graphiques » et autres. Dans la plupart des cas, si vous rencontrez une erreur liée à un package manquant, votre situation est légèrement plus complexe que le scénario le plus simple. [Ici](/tex/{{lang.url-fragment}}python-net/latex-to-image/#regarding-input-options), nous fournissons un indice vers la solution.