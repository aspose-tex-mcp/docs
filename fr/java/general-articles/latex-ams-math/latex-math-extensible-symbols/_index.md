---
translation: true
template: /templates/_template-java.md
linktitle: Symboles extensibles et réglables
title: 5. Symboles extensibles et réglables | Manuel LaTeX
weight: 50
url: /java/latex-math-extensible-symbols/
keywords: ams-latex, amsmath, amsxtra, opérateurs mathématiques en latex, délimiteurs mathématiques en latex, supports mathématiques en latex, accolades mathématiques en latex, accents mathématiques en latex
description: Cet article traite des fonctionnalités de LaTeX liées à l'utilisation de symboles mathématiques extensibles et réglables.
lastmod: "2024-09-27"
---

{{<section overview>}}

Dans LaTeX, certaines fonctionnalités permettent de produire des structures pouvant atteindre n'importe quelle taille requise. La composition mathématique a cruellement besoin d’une telle variabilité. Nous en aborderons certains aspects dans cet article. Toutes les commandes couvertes dans cette section (sauf indication contraire) sont fournies par LaTeX standard.


## 5.1. Ellipse...

Le package `amsmath` remplace (dans presque tous les cas) tous ces `\ldots`, `cdots`, etc. de LaTeX standard par la seule commande `\dots`. La position verticale des points de suspension et l'espace qui l'entoure sont automatiquement sélectionnés en fonction du type de symbole suivant `\dots`. Si le symbole suivant est, par exemple, un signe plus, les points apparaîtront centrés ; s'il s'agit d'une virgule, ils tomberont sur la ligne de base. Il s'agit toujours de trois points mais l'espacement est variable.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dots, H_n$, a sum
$H_1 + H_2 + \dots + H_n$, an orthogonal product
$H_1 \times H_2 \times \dots \times H_n$.
```

![Ellipse avec espacement déterminé automatiquement](/tex/images/java/tutorial/latex-ams-math-5-1.png)

Cependant, lorsque les points apparaissent à la fin d'une formule, l'objet suivant sera quelque chose comme `\end` ou `\)` ou `$`, et cela ne donne à LaTeX aucune idée sur le positionnement des points. Dans un tel cas, vous devez aider en utilisant `\dotsc` pour les points suivis de virgules, `\dotsb` pour les points suivis de *Opérateur binaire* ou *Symbole de relation*, `\dotsm` pour les points suivis de points de multiplication, ` \dotsi` pour les points suivis d'intégrales, ou `\dotso` dans tout autre cas.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
A series $H_1, H_2, \dotsc\,$, a sum
$H_1 + H_2 + \dotsb\,$, an orthogonal product
$H_1 \times H_2 \times \dotsm\,$, and an infinite
integral: \[ \int_{H_1} \int_{H_2} \dotsi \;
{-\Gamma}\, d\Theta \]
```

![Points de suspension à la fin d'une formule](/tex/images/java/tutorial/latex-ams-math-5-2.png)

## 5.2. Symboles extensibles horizontalement

Fondamentalement, LaTeX permet de configurer n'importe quelle commande d'accent mathématique pour produire le glyphe approprié à partir d'une plage de largeurs lorsque celles-ci sont fournies par les polices disponibles. Cependant, dans LaTeX standard, il n'existe que deux commandes de ce type : `\widehat` et `\widetilde`.

Dans l'exemple suivant, nous démontrons l'utilisation de quelques commandes qui produisent des constructions similaires aux accents extensibles susmentionnés. Ils produisent tous des symboles composés du cours de mathématiques *Ordinaire*.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align*}
\widehat {\psi_\delta(t) E_t h}
&= \widetilde {\psi_\delta(t) E_t h} \\
\overline {\psi_\delta(t) E_t h}
&= \underline {\psi_\delta(t) E_t h} \\
\overbrace {\psi_\delta(t) E_t h}
&= \underbrace {\psi_\delta(t) E_t h}
& & \text{Do not change style} \\
\overrightarrow {\psi_\delta(t) E_t h} 
&= \overleftarrow {\psi_\delta(t) E_t h}
& & \text{Do not change style} \\[-3pt]
& & & \text{without \textsf{amsmath}} \\
\underrightarrow {\psi_\delta(t) E_t h}
&= \underleftarrow {\psi_\delta(t) E_t h}
& & \text{Do need \textsf{amsmath}} \\
\overleftrightarrow {\psi_\delta(t) E_t h}
&=\underleftrightarrow{\psi_\delta(t) E_t h}
& & \text{Do need \textsf{amsmath}}
\end{align*}
```

![Accents extensibles](/tex/images/java/tutorial/latex-ams-math-5-3.png)

Ici, « changer de style » signifie que le symbole utilisé est affecté par le style mathématique utilisé afin qu'il ait un aspect correct lorsqu'il est utilisé, par exemple, en fractions ou en indice/exposant. Ceux qui ne changent pas de style n'apparaîtront qu'au niveau supérieur des formules affichées.

## 5.3. Symboles extensibles verticalement

L'extensibilité verticale est beaucoup plus large. Le tableau suivant répertorie tous les symboles extensibles verticalement.

*Symboles extensibles verticalement*

|||||||
|:---:|---|:---:|---|:---:|---|
| !["Parenthèses"](/tex/images/java/tutorial/latex-ams-math-delim-5-1.png) | `(` `)` | !["Accoudoirs ouverts"](/tex/images/java/tutorial/latex-ams-math-delim-5-11.png) | `\{` `\}` | !["Doubles barres verticales"](/tex/images/java/tutorial/latex-ams-math-delim-5-18.png) | *`\lVert` `\rVert`* |
| !["Crochets angulaires"](/tex/images/java/tutorial/latex-ams-math-delim-5-2.png) | `\langle` `\rangle` | !["Accoudoirs fermés"](/tex/images/java/tutorial/latex-ams-math-delim-5-11.png) | `\lbrace` `\rbrace` | !["Barres verticales simples"](/tex/images/java/tutorial/latex-ams-math-delim-5-19.png) | *`\lvert` `\rvert`* |
| !["Lgroup et Rgroup"](/tex/images/java/tutorial/latex-ams-math-delim-5-3.png) | `\lgroup` `\rgroup` | !["Crochets ouverts"](/tex/images/java/tutorial/latex-ams-math-delim-5-12.png) | `[` `]` | !["Barre verticale"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `|` |
| !["Moustaches"](/tex/images/java/tutorial/latex-ams-math-delim-5-4.png) | `\lmoustache` `\rmoustache` | !["Crochets fermants"](/tex/images/java/tutorial/latex-ams-math-delim-5-12.png) | `\lbrack` `\rbrack` | !["Barre verticale"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `\vert` |
| !["Flèche vers le bas"](/tex/images/java/tutorial/latex-ams-math-delim-5-5.png) | `\Downarrow` | !["Supports de plafond ouverts"](/tex/images/java/tutorial/latex-ams-math-delim-5-13.png) | `\lceil` `\rceil` | !["Barre de flèche verticale"](/tex/images/java/tutorial/latex-ams-math-delim-5-20.png) | `\arrowvert` |
| !["Flèche vers le haut"](/tex/images/java/tutorial/latex-ams-math-delim-5-6.png) | `\Uparrow` | !["Fermeture des crochets de plancher"](/tex/images/java/tutorial/latex-ams-math-delim-5-14.png) | `\lfloor` `\rfloor` | !["Barre verticale d'accolade"](/tex/images/java/tutorial/latex-ams-math-delim-5-21.png) | `\bracevert` |
| !["Flèche haut bas"](/tex/images/java/tutorial/latex-ams-math-delim-5-7.png) | `\Updownarrow` | !["Doubles crochets ouverts"](/tex/images/java/tutorial/latex-ams-math-delim-5-15.png) | ***`\llbracket` `\rrbracket`*** | !["Double barre verticale"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\Arrowvert` |
| !["Flèche simple vers le bas"](/tex/images/java/tutorial/latex-ams-math-delim-5-8.png) | `\downarrow` | !["Barre oblique"](/tex/images/java/tutorial/latex-ams-math-delim-5-16.png) | `/` | !["Double ligne verticale"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\|` |
| !["Flèche simple vers le haut"](/tex/images/java/tutorial/latex-ams-math-delim-5-9.png) | `\uparrow` | !["Barre oblique inverse"](/tex/images/java/tutorial/latex-ams-math-delim-5-17.png) | `\backslash` | !["Double ligne verticale"](/tex/images/java/tutorial/latex-ams-math-delim-5-22.png) | `\Vert` |
| !["Flèche simple vers le haut et vers le bas"](/tex/images/java/tutorial/latex-ams-math-delim-5-10.png) | `\updownarrow` | | `.` | !["Signe de racine carrée"](/tex/images/java/tutorial/latex-ams-math-delim-5-23.png) | `\sqrtsign` |


> *Les symboles en italique nécessitent soit le package `amsmath`, soit, s'ils sont en plus saisis en gras, le package `stmaryrd`. Un point (.) n'est pas en soi un symbole extensible, mais il peut être utilisé pour produire un délimiteur « invisible ». Le symbole `\sqrtsign` ne peut pas être utilisé avec `\left`, `\right` ou `\middle`.*

> *Synonymes : [ - `\lbrack`, `[`; ] - `\rbrack`, `]`; { - `\lbrace`, `\{`; } - `\rbrace`, `\}`; | - `\vert`, `|`; || - `\Vert`, `\|`.*

Ces symboles ne deviennent extensibles que dans certains usages. Ils doivent reposer sur la construction suivante :

```tex
\left <ext-Open> <sub-formula> \right <ext-Close>
```

> Si LaTeX utilise le programme eTeX, vous pouvez également utiliser ces symboles extensibles avec `\middle`.

Ici, `<ext-Open>` et `<ext-Close>` peuvent être n'importe lequel des symboles (sauf `\sqrtsign`) répertoriés dans le tableau ci-dessus. Il doit s'agir de symboles configurés pour être extensibles comme décrit dans le [fntguide](https://www.latex-project.org/help/documentation/fntguide.pdf). Ainsi, un symbole représentant l’absence de glyphe réel doit être disponible. Il se trouve que ce symbole, également connu sous le nom de *délimiteur nul*, est le point (.). Les tailles des glyphes réels pour la composition d'un symbole extensible sont choisies pour s'adapter à la hauteur et à la profondeur de la sous-formule qui se situe entre eux.

Le symbole radical `\sqrtsign` s'agrandit à la fois verticalement et horizontalement pour s'adapter à la taille de son argument. Dans LaTeX, vous préférez utiliser la commande `\sqrt` pour obtenir ce symbole.


```tex
\[
  \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 +
    \sqrtsign{1 + \sqrtsign{1 + \sqrtsign{1 + x}}}}}}
\]
```

![Radicaux étendus](/tex/images/java/tutorial/latex-ams-math-5-24.png)