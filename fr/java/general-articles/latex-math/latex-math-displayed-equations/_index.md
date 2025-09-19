---
translation: true
template: /templates/_template-java.md
linktitle: Équations affichées
title: 9. Équations affichées 
weight: 90
url: /java/latex-math-displayed-equations/
keywords: latex, formules mathématiques en latex, mathématiques en latex, formule affichée en mathématiques en latex, équation affichée en mathématiques en latex, tableau d'équations mathématiques en latex, alignement affiché en mathématiques en latex
description: Découvrez comment afficher des formules mathématiques de grande taille ou d'un grand nombre de formules à l'aide des commandes fournies par LaTeX.
lastmod: "2024-09-27"
---

{{<section overview>}}

Nous avons maintenant discuté de la manière de traiter les formules individuelles ; mais les affichages impliquent souvent tout un tas de formules différentes, ou différents éléments d'une énorme formule, et il peut être difficile de les disposer de manière à ce qu'ils s'alignent correctement les uns avec les autres. Heureusement, les grands écrans se répartissent généralement en quelques modèles simples.

### 9.1. Affichages sur une ligne

Les équations affichées contiennent souvent du texte ordinaire. Nous avons déjà [discuté](/tex/{{lang.url-fragment}}java/latex-math-fine-points/#82-non-italic-letters) comment insérer des caractères romains dans des formules sans quitter le mode mathématique, mais la meilleure façon d'afficher du texte est de le mettre dans une `\hbox`. En fait, il n’est même pas nécessaire d’avoir recours à des mathématiques. Pour saisir un ensemble

![Texte affiché sans aucun calcul](/tex/images/java/tutorial/latex-math-9-1.png)

vous pouvez dire `$$\hbox{Texte affiché}$$`. Mais voici un exemple plus intéressant :

![Texte dans un affichage mathématique](/tex/images/java/tutorial/latex-math-9-2.png)

Dans ce cas, les formules et le texte ont été combinés comme suit :


```tex
$$\X_n=X_k \qquad\hbox{if and only if}\qquad
     Y_n=Y_k \quad\hbox{and}\quad Z_n=Z_k.$$
```

Comme vous pouvez le voir, `\qquad` apparaît autour de "si et seulement si", mais un seul `\quad` entoure "et" ; cela met l'accent sur le fait que les parties *Y* et *Z* de l'affichage sont plus étroitement liées les unes aux autres qu'à la partie *X*. 

Regardons l'affichage suivant :

![Texte dans un affichage mathématique](/tex/images/java/tutorial/latex-math-9-3.png)

Une façon de le spécifier est


```tex
$$Y_n=X_n\bmod p \quad\hbox{and}\quad z_n=X_n\bmod q
    \qquad\hbox{for all }n\ge0.$$
```

Mais la meilleure façon serait (voir la deuxième ligne)


```tex
$$Y_n=X_n\bmod p \quad\hbox{and}\quad z_n=X_n\bmod q
    \qquad\hbox{for all $n\ge0$.}$$
```

Oui, c'est le mode mathématique à l'intérieur du mode horizontal à l'intérieur du mode mathématique d'affichage, mais cette solution semble plus naturelle que la première.

Passons maintenant aux numéros d'équation, ces petites étiquettes qui apparaissent sur le côté des écrans. Si vous tapez


```tex
$$<formula>\eqno<formula>$$
```

TeX affichera la première formule et mettra également un numéro d'équation (la deuxième formule) dans la marge droite. Par exemple,


```tex
$$x^2-y^2 = (x+y)(x-y).\eqno(15)$$
```

produira

![Numéros d'équation à droite](/tex/images/java/tutorial/latex-math-9-4.png)

Vous pouvez également obtenir les numéros d'équation dans la marge de gauche en utilisant `\leqno`. Par exemple,

```tex
$$x^2-y^2 = (x+y)(x-y).\leqno(15)$$
```

produira

![Numéros d'équation à gauche](/tex/images/java/tutorial/latex-math-9-5.png)

Notez que vous donnez toujours le numéro de l'équation en deuxième, même s'il doit apparaître à gauche.

Les équations affichées sont centrées quelle que soit la présence des numéros d'équation. Mais lorsqu'une formule est volumineuse, TeX s'assure qu'elle n'interfère pas avec son nombre ; le numéro d’équation peut même être placé seul sur une ligne.

LaTeX fournit également l'environnement d'équation pour numéroter automatiquement vos équations. Par exemple, en tapant

```tex
\begin{equation}
  f(x)=(x+a)(x+b)
\end{equation}
```

aboutit à

![L'utilisation de l'environnement d'équation](/tex/images/java/tutorial/latex-math-9-6.png)

Il est également possible d'étiqueter et de référencer des équations en utilisant `\label` et `\ref`. Par exemple,

```tex
\begin{equation} \label{eq:someequation}
  f(x)=(x+a)(x+b)
\end{equation}
this references equation \ref{eq:someequation}.
```

aboutit à

![L'utilisation de l'environnement d'équation avec une étiquette et une référence](/tex/images/java/tutorial/latex-math-9-7.png)

### 9.2. Affichages multilignes

Parfois, un affichage peut ne pas correspondre au modèle simple d’une formule sur une seule ligne avec ou sans numéro d’équation. LaTeX fournit des commandes spéciales pour la plupart des cas restants.

Les affichages multilignes incluent généralement plusieurs équations qui doivent être alignées par leurs signes « = », comme dans

![Une équation multiligne composée avec l'environnement de tableau](/tex/images/java/tutorial/latex-math-9-8.png)

La méthode recommandée pour un tel affichage consiste à utiliser l'environnement `array` fourni par LaTeX :

```tex
$$\begin{array}{rl}
  X_1+\cdots+\X_p&=m,\\
  Y_1+\cdots+\Y_q&=n.}
\end{array}$$
```

Cet environnement vous aide à représenter vos équations sous la forme d'un tableau rectangulaire à plusieurs colonnes (deux colonnes dans ce cas). Les lignes contiennent des équations individuelles séparées par la commande `\\` (qui est une nouvelle ligne). Les côtés gauche et droit de chaque équation sont séparés par le symbole « & ». Il n'est pas obligatoire que la dernière ligne se termine par `\\`. L'environnement dispose également d'un argument qui spécifie l'alignement dans chaque colonne. Dans l'exemple, la valeur appropriée est « rl », ce qui signifie que les côtés gauches des équations seront alignés à droite, tandis que les côtés droits seront alignés à gauche.

LaTeX fournit également l'environnement `eqnarray*` qui fonctionne de manière similaire, mais pour que les deux côtés des équations soient correctement alignés, il faut deux points d'alignement, et malheureusement, l'espacement sort quelque peu des conventions de frappe mathématique. Le code suivant

```tex
\begin{eqnarray*}
  X_1+\cdots+X_p&=&m,\\
  Y_1+\cdots+Y_q&=&n.
\end{eqnarray*}
```

produit le résultat suivant :

![Une équation multiligne composée avec l'environnement eqnarray*](/tex/images/java/tutorial/latex-math-9-9.png)

L'environnement « eqnarray » de LaTeX produit le même résultat sauf qu'il numérote automatiquement les équations.

Il peut y avoir n'importe quel nombre d'équations dans un environnement « tableau » ; le schéma général est

```tex
\begin{array}{rl}
  <left-hand side_1>&<right-hand side_1>\\
  <left-hand side_2>&<right-hand side_2>\\
  ...
  <left-hand side_n>&<right-hand side_n>
\end{array}
```

où chaque `<côté droit>` commence par le symbole sur lequel vous souhaitez que l'alignement se produise.

Le résultat de l’environnement « tableau » est une boîte centrée verticalement. Cela permet d'obtenir facilement une formule comme

![Deux groupes d'équations dans un seul affichage](/tex/images/java/tutorial/latex-math-9-10.png)

Vous utilisez simplement l'environnement `array` deux fois dans la ligne :

```tex
$$\left\{
  \begin{array}{rl}
    \alpha&=f(z)\\ \beta&=f(z^2)\\ \gamma&=f(z^3)
  \end{array}
\right\}\qquad\left\{
  \begin{array}{rl}
    x&=\alpha^2-\beta\\ y&=2\gamma
  \end{array}
\right\}.$$
```

Le niveau de complexité suivant se produit lorsque vous disposez de plusieurs équations alignées avec plusieurs numéros d’équation. Certaines lignes peuvent également être numérotées et d'autres non :

![Tableau d'équations numérotées arbitrairement avec des balises à droite](/tex/images/java/tutorial/latex-math-9-11.png)

Malheureusement, même avec l'environnement `eqnarray*` (avec son espacement incorrect), il n'existe aucun moyen de spécifier manuellement les numéros d'équation dans un affichage multiligne. Seul le package `amsmath` peut 
aide. Ainsi, la méthode recommandée pour obtenir le résultat ci-dessus est de taper :

```tex
%% Preamble
\usepackage{amsmath}
%% Body
\begin{align}
  (x+y)(x-y)&=x^2-xy+xy-y^2 \notag \\
            &=x^2-y^2; \tag4\\
  (x+y)^2   &=x^2+2xy+y^2. \tag5
\end{align}
```

Si vous omettez à la fois `\tag` et `\notag` sur une ligne de l'environnement `align`, le numéro d'équation sera généré automatiquement en utilisant la valeur actuelle stockée dans le compteur interne correspondant.

Si vous chargez le package `amsmath` avec l'option `leqno`, les numéros d'équation apparaîtront dans la marge de gauche. Ainsi

```tex
%% Preamble
\usepackage[leqno]{amsmath}
%% Body
\begin{align}
  (x+y)(x-y)&=x^2-xy+xy-y^2 \notag \\
            &=x^2-y^2; \tag4\\
  (x+y)^2   &=x^2+2xy+y^2. \tag5
\end{align}
```
produit

![Tableau d'équations numérotées arbitrairement avec des balises à gauche](/tex/images/java/tutorial/latex-math-9-12.png)

Pour en savoir plus sur la composition de formules mathématiques à l'aide des fonctionnalités du package `amsmath`, consultez ces [articles](/tex/{{lang.url-fragment}}java/what-is-ams-latex/).

### 9.3. Formules longues

Voyons maintenant ce qu'il faut faire lorsqu'une formule est si longue qu'elle ne tient pas sur une seule ligne. Par exemple, supposons que vous rencontriez l'équation

![Formule longue rétrécie qui rend la ligne trop pleine](/tex/images/java/tutorial/latex-math-9-13.png)

Vous devrez le rompre d'une manière ou d'une autre ; TeX a fait de son mieux pour tout rassembler en réduisant les espaces à côté des signes «+» et «-» à zéro, mais la ligne est toujours trop pleine.

Essayons de briser cette équation juste avant le « +7 ». L'environnement `array` laisse trop d'espace à droite du '=' si vous l'utilisez de la même manière que pour les équations multilignes :

```tex
$$\begin{array}{rl}
  \sigma(2^{34}-1,2^{35},1)&=-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1) \\
                   &\qquad{}+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1)
\end{array}$$
```

Il est donc préférable de recourir à nouveau au package « amsmath ». Mais cette fois, vous devez utiliser le tableau `align*` puisque les numéros d'équation ne sont pas nécessaires :

```tex
%% Preamble
\usepackage{amsmath}
%% Body
\begin{align*}
  \sigma(2^{34}-1,2^{35},1)&=-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1) \\
                   &\qquad+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1).
\end{align*}$$
```

Cela donne

![Formule longue découpée à l'aide de l'environnement align*](/tex/images/java/tutorial/latex-math-9-14.png)

L'idée est de traiter une formule longue d'une ligne comme une formule de deux lignes, en utilisant `\qquad` sur la deuxième ligne afin que la deuxième partie de la formule apparaisse bien à droite du signe '=' sur la première ligne. 

Ce n'est en fait pas une tâche facile de décider comment diviser en lignes de longues formules affichées ; TeX ne tente jamais de faire cela, car aucun ensemble de règles n'est vraiment adéquat. L'auteur d'un manuscrit mathématique est généralement le meilleur juge de ce qu'il faut faire, puisque les positions de rupture dépendent de facteurs subtils des explications mathématiques. Par exemple, il est souvent souhaitable de mettre l’accent sur une partie de la symétrie ou sur une autre structure qui sous-tend la formule, et de telles choses nécessitent une solide compréhension de ce qui se passe exactement dans cette formule.

Néanmoins, il est possible d'énoncer quelques règles empiriques sur la façon de traiter les formules longues dans les affichages, car il existe certains principes que le meilleur compositeur mathématique a tendance à suivre :

1. Bien que les formules dans un paragraphe s'interrompent toujours *après* les opérations et relations binaires, les formules affichées s'interrompent toujours *avant* les opérations et relations binaires. C'est pourquoi nous n'avons pas terminé la première ligne de notre exemple précédent par `(2^{34}-1)+` ; nous l'avons terminé par `(2^{34}-1` et avons commencé la deuxième ligne par `+`.

2. Lorsqu'une équation est cassée avant une opération binaire, la deuxième ligne doit commencer au moins deux quads à droite de l'endroit où commence la sous-formule la plus interne contenant cette opération binaire sur la première ligne. Par exemple, si vous souhaitez rompre

```tex
$$\sum_{0<k<n}\left(<formula_1>+<formula_2>\right)$$
```

au niveau du signe plus entre `<formula_1>` et `<formula_2>`, il est presque obligatoire que le signe plus sur la deuxième ligne apparaisse un peu à droite de la grande parenthèse gauche qui correspond à `\left(`.

Dans l'exemple que nous venons de considérer, un soin particulier est nécessaire pour diviser la formule en deux lignes, car les délimiteurs `\left` et `\right` ne peuvent pas être utilisés isolément : vous ne pouvez pas avoir uniquement `\left` sur une seule ligne d'un formule et seulement `\right` dans la seconde. De plus, vous souhaiterez que les deux délimiteurs soient de la même taille, même s'ils apparaissent sur des lignes différentes. La meilleure solution consiste généralement à choisir vous-même la taille du délimiteur ; par exemple, vous pouvez taper

```tex
%% Preamble
\usepackage{amsmath}
%% Body
\begin{align*}
  \sum_{0<k<n}\biggl(&<formula_1>\\
    &\qquad+<formula_2>\biggr)
\end{align*}
```

si les délimiteurs `\bigg` sont les meilleurs. Notez que les marqueurs `&` n'apparaissent pas aux signes `=` dans cet exemple, ils marquent simplement un point d'alignement.

Il existe une autre façon de décomposer de longues formules, parfois appelée forme *à deux lignes*. L'idée est de mettre la première partie de la formule presque à ras de gauche et la deuxième partie presque à ras de droite, où "presque à ras" signifie "à un quad". Ainsi, la forme à deux droites d’une équation sigma longue considérée précédemment est

![Forme à deux lignes d'une équation](/tex/images/java/tutorial/latex-math-9-15.png)

Pour obtenir cet effet sur deux lignes, tapez simplement :

```tex
$$\displaylines{\quad\sigma(2^{34}-1,2^{35},1)
  =-3+(2^{34}-1)/2^{35}+2^{35}\!/(2^{34}-1)\hfill{}\cr
\hfill{}+7/2^{35}(2^{34}-1)-\sigma(2^{35},2^{34}-1,1).\quad\cr}$$
```

Un `{}` supplémentaire a été tapé sur la deuxième ligne ici afin que TeX sache que le `+` est une opération binaire. La forme à deux lignes est particulièrement recommandée pour les équations comportant un long côté gauche ; dans ce cas, la pause intervient généralement juste avant le signe =.