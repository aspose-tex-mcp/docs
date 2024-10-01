---
translation: true
template: /templates/_template-java.md
linktitle: Matrice et environnements similaires
title: 3. Matrice et environnements similaires | Manuel LaTeX
weight: 30
url: /java/latex-ams-matrix/
keywords: ams-latex, amsmath, amscd, matrice latex, cas latex, latex delarray, diagrammes commutatifs latex
description: Cet article fournit une brève introduction à la composition de structures de type matrice LaTeX à l'aide des packages AMS-LATEX.
lastmod: "2024-09-27"
---

{{<section overview>}}

Il existe un certain nombre d'environnements pour la composition de structures de type matricielle définies dans le package `amsmath`. Ils sont tous similaires à l'environnement `array` standard de LaTeX en termes de syntaxe et de mise en page. En général, une grande variété de structures mathématiques bidimensionnelles et de dispositions tabulaires peuvent être décrites sous forme de tableaux.

Trois environnements - `cases`, `matrix` et `pmatrix` - remplacent les commandes du LaTeX standard. Les commandes standard utilisent une notation différente et ne peuvent donc pas être utilisées avec les formulaires d'environnement évoqués ici. Le package `amsmath` produira un message d'erreur si l'une des anciennes commandes est utilisée. À l'inverse, si vous essayez d'utiliser les formulaires de l'environnement `amsmath` sans charger le package, vous obtiendrez très probablement le message d'erreur suivant : `"Caractère de tabulation d'alignement mal placé &"`.


## 3.1. L'environnement des « cas »

L'environnement `case` est utilisé pour gérer les constructions, où une seule équation a quelques variantes. De telles constructions sont très courantes en mathématiques. Il produit un tableau avec deux colonnes, toutes deux alignées à gauche.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
P_{r - j} = \begin{cases}
                     0 & \text{if $r - j$ is odd,} \\
r! \, (-1)^{(r - j)/2} & \text{if $r - j$ is even.}
\end{cases}
\end{equation}
```

![Environnement des dossiers](/tex/images/java/tutorial/latex-ams-math-3-1.png)

Notez l'utilisation de la commande `\text` et du "mode mathématique intégré" dans les chaînes de texte.

## 3.2. Les environnements matriciels

Les environnements matriciels, contrairement au « tableau » de LaTeX, n'acceptent pas d'argument spécifiant les formats des colonnes. Au lieu de cela, ils proposent un format par défaut : jusqu'à 10 colonnes centrées. L'espacement diffère également légèrement de la valeur par défaut dans « array ». Les exemples suivants illustrent les environnements `matrix`, `pmatrix`, `bmatrix`, `Bmatrix`, `vmatrix` et `Vmatrix`.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather*}
\begin{matrix} 0 & 1 \\ 1 & 0 \end{matrix} \quad \begin{pmatrix} 0 & -i \\ i & 0 \end{pmatrix} \\
\begin{bmatrix} 0 & -1 \\ 1 & 0 \end{bmatrix} \quad \begin{Bmatrix} 1 & 0 \\ 0 & -1 \end{Bmatrix} \\
\begin{vmatrix} a & b \\ c & d \end{vmatrix} \quad \begin{Vmatrix} i & 0 \\ 0 & -i \end{Vmatrix}
\end{gather*}
```

![Environnements matriciels](/tex/images/java/tutorial/latex-ams-math-3-2.png)

Le compteur `MaxMatrixCols` détermine le nombre maximum de colonnes dans un environnement matriciel. Vous pouvez le modifier à l'aide de la commande counter standard de LaTeX. La valeur du paramètre de longueur `\arraycolsep` détermine la quantité d'espace entre les colonnes. Tout comme dans les tableaux standards, mais aucun espace n'est ajouté de chaque côté du tableau. Plus de colonnes feront travailler LaTeX plus dur et nécessiteront plus de ressources. Cependant, définir « MaxMatrixCols » sur 20 ou plus est possible sans perte de performances notable, car avec les implémentations TeX typiques d'aujourd'hui, ces limites sont moins importantes.


```tex
\usepackage{amsmath}
\setcounter{MaxMatrixCols}{20}
% -------------------------------------------------------------------------------
\[
\begin{Vmatrix}
\,a&b&c&d&e&f&g&h&i&j &\cdots\,{} \\
&a&b&c&d&e&f&g&h&i &\cdots\,{} \\
& &a&b&c&d&e&f&g&h &\cdots\,{} \\
& & &a&b&c&d&e&f&g &\cdots\,{} \\
& & & &\ddots&\ddots&\hdotsfor[2]{5}\,{}
\end{Vmatrix} \]
```

![Plus de colonnes dans les environnements matriciels](/tex/images/java/tutorial/latex-ams-math-3-3.png)

Dans cet exemple, la commande `\hdotsfor` est utilisée pour produire une ligne de points dans une matrice, s'étendant sur un nombre donné de colonnes. Le paramètre facultatif (ici 2) peut être utilisé pour spécifier un multiplicateur pour l'espace par défaut (3 unités mathématiques) entre les points. L'espace fin et le groupe d'accolades `\,{}` à la fin de chaque ligne améliorent simplement l'apparence de la mise en page ; ensemble, ils produisent deux espaces minces, d'environ 6mu ou 1/3em.

Pour produire une petite matrice en ligne à utiliser dans du texte, vous pouvez utiliser l'environnement « smallmatrix ».


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
To show the effect of the matrix on surrounding lines inside a paragraph, we put it here:
$ \left( \begin{smallmatrix}
1 & 0 \\ 0 & -1
\end{smallmatrix} \right) $
and follow it with enough text to ensure that there is at least one full line below the matrix.
```

![L'environnement smallmatrix](/tex/images/java/tutorial/latex-ams-math-3-4.png)

Notez que les lignes de texte ne sont pas écartées même si la ligne précédant la petite matrice contient des lettres avec des descendants.

## 3.3. Empilement en indices et en exposants

Parfois, vous devrez peut-être composer plusieurs lignes dans un indice ou un exposant. Pour ce faire, vous pouvez utiliser la commande `\substack` avec les lignes délimitant `\\`.

L'environnement « subarray » est une structure légèrement plus générale qui vous permet d'aligner les lignes à gauche ou à droite, plutôt que de les centrer.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
\sum_{\substack{0 \le i \le m \\ 0 < j < n}} P(i, j) \\
\sum_{\begin{subarray}{l}
i \in \Lambda \\
0 \le i \le m \\
0 < j < n
\end{subarray}} P(i, j)
\end{gather}
```

![Empilement en indice et exposant](/tex/images/java/tutorial/latex-ams-math-3-5.png)

> Notez que les deux environnements doivent être entourés d’accolades lorsqu’ils apparaissent sous forme d’indice ou d’exposant.

## 3.4. Diagrammes commutatifs
Le package `amscd` définit quelques commandes pour produire des diagrammes commutatifs simples basés sur des tableaux. Il existe quelques formes abrégées utiles pour spécifier les flèches décorées et autres connecteurs. Cependant, cela présente des limites : par exemple, ces connecteurs ne peuvent être qu'horizontaux ou verticaux.

Dans l'environnement `CD`, les notations `@>>>`, `@<<<`, `@VVV` et `@AAA` produisent respectivement des flèches droite, gauche, bas et haut. L'exemple suivant montre également l'utilisation de la commande `\DeclareMathOperator`.


```tex
\usepackage{amsmath,amscd}
\DeclareMathOperator\add{add}
\DeclareMathOperator\cf {cf}
\DeclareMathOperator\cov{cov}
\DeclareMathOperator\non{non}
% -------------------------------------------------------------------------------
\[ \begin{CD}
\cov (L) @>>> \non (K) @>>> \cf (K) \\
@VVV @AAA @AAA \\
\add (L) @>>> \add (K) @>>> \cov (K) \\
\end{CD} \]
```

![Diagramme commutatif simple](/tex/images/java/tutorial/latex-ams-math-3-6.png)

Voyons comment les décorations sont spécifiées. Pour les flèches horizontales, le contenu entre le premier et le deuxième symbole `>` ou `<` sera composé en exposant, et le contenu entre le deuxième et le troisième sera composé en indice. De même, le contenu entre le premier et le deuxième, ou le deuxième et le troisième, les « A » ou « V » des flèches verticales sera composé comme un « side-script » gauche ou droit. Nous verrons l'utilisation de ce format dans l'exemple suivant.

Les notations `@=` et `@|` donnent des lignes doubles horizontales et verticales.

Au lieu d'une flèche visible, vous pouvez utiliser une « flèche nulle » (« @. ») pour remplir un tableau si nécessaire.


```tex
\usepackage{amsmath, amscd}
\DeclareMathOperator{\End}{End}
% -------------------------------------------------------------------------------
\[ \begin{CD}
S^{W_\Lambda}\otimes T @>j>> T \\
@VVV @VV{\End P}V \\
(S \otimes T)/I @= (Z\otimes T)/J
\end{CD} \]

```

![Diagramme commutatif avec scripts](/tex/images/java/tutorial/latex-ams-math-3-7.png)

Une mise en page similaire peut être produite dans LaTeX standard. Mais ça n'a pas l'air aussi bien.


```tex
\[\begin{array}{ccc}
S^{\mathcal{W}_\Lambda}\otimes T & \stackrel{j}{\longrightarrow} & T \\
\Big\downarrow & & \Big\downarrow\vcenter{\rlap{$\scriptstyle{\mathrm{End}}\,P$}} \\
(S\otimes T)/I & = & (Z\otimes T)/J
\end{array}\]
```

![Diagramme commutatif en LaTeX standard](/tex/images/java/tutorial/latex-ams-math-3-8.png)

Cet exemple montre assez clairement à quel point les résultats du package `amscd` sont meilleurs : la notation est plus facile, les flèches horizontales sont plus longues, l'espacement entre les éléments est bien amélioré. Les forfaits plus spécialisés vous aideront à obtenir des résultats encore plus beaux.

## 3.5. Délimiteurs entourant un tableau : le package `delarray`

Dans cette section, nous discuterons d'une extension générale utile du package `array`. En utilisant cette extension, l'utilisateur peut spécifier des délimiteurs extensibles d'ouverture et de fermeture pour entourer un environnement de « tableau » mathématique. Regardons l'exemple :


```tex
\usepackage{delarray}
% -------------------------------------------------------------------------------
\[ \mathcal{Q} =
\begin{array}[t] ( {cc} ) X & Y \end{array}
\begin{array}[t] [ {cc} ] A & B \\ C & D \end{array}
\begin{array}[b] \lgroup{cc}\rgroup L \\ M \end{array}
\]
```

![L'utilisation du paquet delarray](/tex/images/java/tutorial/latex-ams-math-3-9.png)

> Notez que le package `delarray` est indépendant de `amsmath` mais il charge automatiquement le package `array` si nécessaire.

Les délimiteurs sont placés de part et d'autre du `{cc}`.

Cet exemple illustre également la fonctionnalité la plus utile du package `delarray` : l'utilisation des arguments facultatifs `[t]` et `[b]`, qui ne sont pas autorisés avec les environnements matriciels `amsmath`. Ceux-ci montrent que l'utilisation de la syntaxe `delarray` n'équivaut pas à entourer l'environnement `array` avec `\left` et `\right`, puisque les délimiteurs sont élevés ainsi que le tableau lui-même.