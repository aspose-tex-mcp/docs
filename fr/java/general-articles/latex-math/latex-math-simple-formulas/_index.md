---
translation: true
template: /templates/_template-java.md
linktitle: 1. Formules simples
title: Formules simples | Manuel LaTeX
weight: 10
url: /java/latex-math-simple-formulas/
keywords: latex, formules mathématiques en latex, mathématiques en latex, lettres mathématiques en latex, lettres grecques en latex, chiffres en latex
description: Cet article explique comment créer des expressions mathématiques atomiques simples pour des formules plus complexes avec TeX et LaTeX.
lastmod: "2024-09-27"
---

{{<section overview>}}

La formule la plus simple est une seule lettre « *x* » ou un seul chiffre « 4 ». Pour insérer une telle formule dans un texte LaTeX, vous tapez respectivement « $x$ » ou « $4$ ». Toutes les formules mathématiques sont entourées de parenthèses mathématiques spéciales ($`).

Lorsque vous tapez `$x$`, le '*x*' apparaît en italique, mais `$2$` produit '2' en caractères romains. En général, tous les caractères de votre clavier ont une interprétation spéciale dans les formules mathématiques, conformément aux conventions normales de l'impression mathématique. Les lettres désignent les lettres italiques, tandis que les chiffres et les signes de ponctuation désignent les chiffres romains et la ponctuation. Un trait d'union (-) désigne un signe moins. Le `$` de gauche met TeX en "mode mathématique" et celui de droite le supprime. Donc, si vous oubliez un « $ » ou tapez un « $ » supplémentaire, vous recevrez probablement un message d'erreur car TeX sera confus.

TeX effectue l'essentiel de son propre espacement dans les formules mathématiques. En même temps, il ignore tous les espaces que vous mettez entre les « $ ». Vous pouvez taper `$(x + y)/(x - y)$` ou `$(x+y) / (x-y)$`, mais les deux donneront une formule ![Indices et exposants à un seul caractère](/tex/images/java/tutorial/latex-math-1-1.png) dans lequel il y a un peu d'espace supplémentaire autour des signes '+' et '-' mais aucun autour du signe '/'. Ainsi, vous n'avez pas besoin de vous souvenir de la règle compliquée de l'espacement mathématique et vous êtes libre d'utiliser les espaces comme bon vous semble. Lorsqu'il est nécessaire de marquer la fin des séquences de contrôle (commandes), les espaces sont toujours utilisés de manière normale. Dans la plupart des cas, l'espacement de TeX répondra aux attentes d'un mathématicien ; mais si vous souhaitez remplacer les règles d'espacement de TeX, vous pouvez le faire avec des séquences de contrôle, dont nous parlerons plus tard.

L’une des choses courantes que l’on peut trouver dans les formules mathématiques est l’utilisation de lettres grecques. Dans LaTeX, vous pouvez taper `$\alpha, \beta, \gamma, \delta$` pour obtenir les quatre premières lettres grecques. Et `$\Gamma$`, par exemple, produit une lettre gamma majuscule. Ne confondez pas les lettres grecques `\kappa` et `\nu` avec les lettres italiques *v* et *x* ; le grec `\phi` est différent du zéro barré appelé `\emptyset`. Un `\epsilon` minuscule est différent du symbole désignant l'appartenance à un ensemble. Certaines lettres grecques minuscules ont des formes variantes dans les polices italiques LaTeX : `$\phi, \theta, \epsilon, \rho$` donne ![Indices et exposants à un seul caractère](/tex/images/java/tutorial/latex-math-1-2.png) tandis que `$\varphi, \vartheta, \varepsilon, \varrho$` donne ![Indices et exposants à un seul caractère](/tex/images/java/tutorial/latex-math-1-3.png)

Outre les lettres grecques, il existe de nombreux symboles mathématiques comme « à peu près égal » (`$\approx$`) et « mappe vers » (`$\mapsto$`). Vous pouvez trouver une liste complète de ces séquences de contrôle et leurs symboles correspondants [ici](/tex/{{lang.url-fragment}}java/latex-math-symbols-commands/).