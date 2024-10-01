---
translation: true
template: /templates/_template-java.md
linktitle: Affichage et alignement
title: 2. Affichage et alignement des équations LaTeX | Aligner LaTeX
weight: 10
url: /java/latex-structures-for-equations/
keywords: ams-latex, amsmath, options amsmath, alignement des équations en latex, leqno, eqno, fleqn, étiquette d'équation en latex, étiquette d'équation en latex, équations d'alignement en latex
description: Ceci est une introduction à la composition d'équations LaTeX avec les packages AMS-LATEX et fournit quelques exemples et leurs explications. LaTeX aligne les équations.
lastmod: "2024-09-27"
---

{{<section overview>}}


Le package *amsmath* contient un certain nombre de définitions d'environnements permettant de saisir des formules mathématiques affichées. Ils peuvent être classés selon le nombre de lignes de matériaux (simples ou multiples) et selon le nombre de points d'alignement.

> Dans cette section, nous utiliserons le terme *équation* de la manière suivante : pour désigner une partie *logique* distincte d'un affichage mathématique, qui est souvent numérotée à titre de référence et qui est également étiquetée (par exemple, par son numéro entre parenthèses). De telles étiquettes sont également appelées *balises*.

La liste suivante contient les environnements d'affichage les plus populaires. Le cas échéant, ils ont des formes étoilées dans lesquelles il n'y a pas de marquage des équations.

||
|---|---|---|
| `équation` | `équation*` | Une droite, une équation |
| `multiligne` | `multiligne*` | Une équation à plusieurs droites non alignées, un numéro d'équation |
| `rassembler` | `rassembler*` | Plusieurs équations sans alignement |
| `aligneur` | `aligneur*` | Plusieurs équations avec plusieurs alignements |
| `flaligne` | `flaligne*` | Plusieurs équations : forme étalée horizontalement de « aligner » |
| `diviseur` | | Un alignement simple dans une équation à plusieurs droites |

Tous les exemples de ce chapitre sont composés avec le matériel mathématique centré et les numéros d'équation (balises) à droite. Pour visualiser le positionnement, nous présentons des lignes verticales bleues dans la sortie qui représentent les marges gauche et droite, ainsi que la ligne centrale. Dans le code source LaTeX, nous utilisons le commentaire `% -----...` pour séparer les lignes qui doivent être placées dans le préambule du document de celles qui doivent être placées dans le corps.


```tex
\usepackage[leqno]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![leqno](/tex/images/java/tutorial/latex-ams-math-2-1.png)

Si vous souhaitez positionner les mathématiques à un retrait fixe par rapport à la marge gauche, plutôt que centrées dans la colonne de texte, l'option « fleqn » est disponible. Vous pouvez spécifier la taille du retrait dans le préambule en définissant la valeur de la longueur du caoutchouc `\mathindent`. Sa valeur par défaut est la même que l'indentation d'une liste de premier niveau. Si vous êtes satisfait de cette valeur, vous pouvez ignorer la définition de la longueur de `\mathindent`.


```tex
\usepackage[fleqn,reqno]{amsmath}
\setlength\mathindent{0.2in}
% -------------------------------------------------------------------------------
\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]
```

![fleqn,reqno](/tex/images/java/tutorial/latex-ams-math-2-2.png)

Il n'est pas nécessaire de passer l'option `reqno` ici (car c'est l'option par défaut), mais elle remplace les paramètres de la classe de document, de sorte que le numéro de l'équation est forcé vers la droite quoi qu'il arrive.

Dans LaTeX standard, `&` et `\\` sont utilisés pour la séparation des colonnes et des lignes dans les alignements affichés. Les détails de leur utilisation changent dans les environnements « amsmath ».

## 2.1. Comparaison avec LaTeX standard

Certains environnements d'affichage multilignes vous permettent d'aligner des parties de la formule. Par rapport aux environnements LaTeX standard `eqnarray` et `eqnarray*`, les structures définies dans le package `amsmath` fournissent une manière légèrement différente et plus simple de marquer les points d'alignement. Dans LaTeX standard, `eqnarray*` est similaire à un environnement `array` avec `{rcl}` comme préambule, ce qui signifie que deux caractères `&` sont requis pour indiquer les deux points d'alignement. Dans le package `amsmath`, les structures équivalentes n'ont qu'un seul point d'alignement (comme si `array` avait un préambule `{rl}`), vous devez donc mettre un seul caractère `&` à gauche du symbole (généralement une relation) qui doit être alignée.

L'environnement `eqnarray` produit un espace supplémentaire aux points d'alignement en fonction des paramètres définis pour `array`. Les structures « amsmath », en même temps, donnent un espacement fixe. La différence est clairement illustrée par l’exemple suivant. La même équation est composée à l'aide des environnements `equation`, `align` et `eqnarray`.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
x^2 + y^2 = z^2
\end{equation}
\begin{align}
x^2 + y^2 &= z^2 \\
x^3 + y^3 &< z^3
\end{align}
\begin{eqnarray}
x^2 + y^2 &=& z^2 \\
x^3 + y^3 &<& z^3
\end{eqnarray}
```

![Amsmath comparé au LaTeX standard](/tex/images/java/tutorial/latex-ams-math-2-3.png)

Notez que les espaces dans l'environnement `eqnarray` sont trop larges pour les normes conventionnelles de composition mathématique.
Comme dans LATEX standard, les lignes d'un affichage `amsmath` sont marquées par `\\` (ou la fin de l'environnement). Étant donné que le saut de ligne dans un affichage mathématique nécessite généralement une compréhension approfondie de la structure de la formule, il est généralement considéré comme dépassant les capacités logicielles actuelles.

## 2.2. Une seule équation sur une ligne

Une seule équation peut être produite par l’environnement « équation ». Un tag est automatiquement généré et placé à l'extrême gauche ou à droite selon l'option utilisée. L'environnement `equation*` produit la même équation sans balise. Le LaTeX standard a également une « équation », mais pas une « équation* », car cette dernière est similaire à l'environnement mathématique affiché standard.

Un fait notable est que la présence de la balise n'affecte pas le positionnement du contenu. La balise sera décalée vers le haut ou vers le bas au cas où il n'y aurait pas assez de place pour elle sur une ligne : vers la ligne précédente lorsque les balises d'équation sont à gauche, et vers la ligne suivante lorsque les balises sont à droite.


```tex
\usepackage[leqno]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation*}
n^2 + m^2 = k^2
\end{equation*}
\begin{equation}
n^p + m^p \neq k^p \qquad p > 2
\end{equation}
```

![Une seule équation sur une ligne](/tex/images/java/tutorial/latex-ams-math-2-4.png)

## 2.3. Une seule équation sur plusieurs droites sans alignement

Une variante de l'environnement « équation » est l'environnement « multiligne ». Il n'est utilisé que pour les équations qui ne tiennent pas sur une seule ligne. Le caractère `\\` doit être utilisé pour marquer les sauts de ligne, car ils ne sont pas trouvés automatiquement.

La première ligne de la 'multline' sera alignée sur une indentation à partir de la marge gauche et la dernière sur la même indentation à partir de la marge droite. La valeur de la longueur `\multlinegap` définit la taille de cette indentation.

Chaque ligne autre que la première et la dernière est centrée individuellement dans la largeur d'affichage (sauf si l'option `fleqn` est utilisée). Cependant, si vous ajoutez la commande `\shoveleft` ou `\shoveright` dans une ligne, cette ligne sera forcée vers la gauche ou vers la droite.

Un environnement « multiligne » a une seule balise, car il s'agit logiquement d'une seule équation. Par conséquent, aucune des lignes individuelles ne peut être modifiée par l'utilisation de `\tag` ou `\notag`. La balise, si elle est présente, est placée à droite/gauche sur la dernière/première ligne lorsque l'option `reqno`/`leqno` est utilisée.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{multline}
\text{First line of a multline} \\
\text{Centered Middle line} \\
\shoveright{\text{A right Middle}} \\
\text{Another centered Middle} \\
\text{Yet another centered Middle} \\
\shoveleft{\text{A left Middle}} \\
\text{Last line of the multline}
\end{multline}
```

![Une seule équation sur plusieurs lignes](/tex/images/java/tutorial/latex-ams-math-2-5.png)

L'exemple suivant montre comment `\multlinegap` affecte le résultat. Dans le premier cas, les "*dy*" s'alignent, ce qui donne l'impression qu'il manque une balise dans la première ligne de l'équation. Lorsque `\multlinegap` est défini sur `0`, l'espace à gauche de la deuxième ligne ne change pas à cause de la balise, tandis que la première ligne est décalée vers la marge de gauche, indiquant clairement qu'il s'agit d'une seule équation. .


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{multline} \tag{2}
\sum_{t \in \mathbf{T}} \int_a^t \biggl\lbrace \int_a^t f(t - x)^2 \, g(y)^2 \,dx \biggr\rbrace \,dy \\
= \sum_{t \notin \mathbf{T}} \int_t^a \biggl\lbrace g(y)^2 \int_t^a f(x)^2 \,dx \biggr\rbrace \,dy
\end{multline}
\setlength\multlinegap{0pt}
\begin{multline} \tag{2}
\sum_{t \in \mathbf{T}} \int_a^t \biggl\lbrace \int_a^t f(t - x)^2 \, g(y)^2 \,dx \biggr\rbrace \,dy \\
= \sum_{t \notin \mathbf{T}} \int_t^a \biggl\lbrace g(y)^2 \int_t^a f(x)^2 \,dx \biggr\rbrace \,dy
\end{multline}
```

![L'effet \multilinegap](/tex/images/java/tutorial/latex-ams-math-2-6.png)

## 2.4. Une seule équation sur plusieurs droites avec alignement

Lorsque vous avez besoin d'aligner une seule équation multiligne, l'environnement « split » est à votre service. Utilisez simplement un seul caractère `&` sur chaque ligne pour marquer les points d'alignement.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
\begin{split}
(a + b)^4 &= (a + b)^2 (a + b)^2 \\
          &= (a^2 + 2ab + b^2)(a^2 + 2ab + b^2) \\
          &= a^4 + 4a^3b + 6a^2b^2 + 4ab^3 + b^4
\end{split}
\end{equation}
```

![Une seule équation avec un alignement simple](/tex/images/java/tutorial/latex-ams-math-2-7.png)

Un « split » ne crée pas lui-même une balise d'équation (la variante étoilée n'est donc pas nécessaire), car elle est toujours utilisée comme contenu d'une seule équation. A cet effet, vous pouvez le placer dans un environnement extérieur.

Par défaut, la balise (ainsi que toute partie de l'équation en dehors du « split ») est centrée verticalement sur la hauteur totale du matériau de l'environnement « split ». Ce comportement correspond à l'option `centertags`. Lorsque vous spécifiez l'option `tbtags`, la balise est placée sur la dernière ligne du `split` lorsque la balise est à droite, et sur la première ligne lorsque la balise est à gauche.


```tex
\usepackage[tbtags]{amsmath}
% -------------------------------------------------------------------------------
\begin{equation}
\begin{split}
(a - b)^3 &= (a - b) (a - b)^2 \\
          &= (a - b)(a^2 - 2ab + b^2) \\
          &= a^3 - 3a^2b + 3ab^2 - b^3
\end{split}
\end{equation}
```

![Une seule équation avec un alignement simple et la balise sur la dernière ligne](/tex/images/java/tutorial/latex-ams-math-2-8.png)

## 2.5. Groupes d'équations sans alignement

Lorsque vous avez besoin de mettre deux ou plusieurs équations sur un seul affichage sans alignement entre les équations, vous pouvez utiliser l'environnement « rassembler ». Il centre également séparément chaque équation dans la largeur d'affichage et est équipé d'une balise individuelle, si nécessaire. Chaque ligne d'un « rassemblement » est logiquement une seule équation.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
(a + b)^2 = a^2 + 2ab + b^2 \\
(a + b) \cdot (a - b) = a^2 - b^2
\end{gather}
```

![Groupe d'équations sans alignement](/tex/images/java/tutorial/latex-ams-math-2-9.png)

Vous devrez peut-être supprimer le numéro d’équation pour une certaine ligne. La commande `\notag`, placée dans la ligne logique, est la réponse. L'environnement `gather*` ne marque pas du tout les équations.

```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{gather}
D(a,r) \equiv \{ z \in \mathbf{C} \colon |z - a| < r \} \notag \\
\operatorname{seg} (a, r) \equiv \{ z \in \mathbf{C} \colon \Im z < \Im a, \ |z - a| < r \} \\
C (E, \theta, r) \equiv \bigcup_{e \in E} c (e, \theta, r)
\end{gather}
```

![Groupe d'équations avec balises omises](/tex/images/java/tutorial/latex-ams-math-2-10.png)

## 2.6. Groupes d'équations avec alignement simple

Lorsque vous devez composer plusieurs équations sur un seul écran et les aligner verticalement, l'environnement « aligner » vient à la rescousse. Dans le cas le plus simple, vous utilisez un seul « & » sur chaque ligne pour marquer le point d'alignement.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
(a - b)^3 &= (a - b) (a - b)^2 \\
          &= (a - b)(a^2 - 2ab + b^2) \\
          &= a^3 - 3a^2b + 3ab^2 - b^3
\end{align}
\begin{align}
x^2 + y^2 &= 1 \\
        y &= \sqrt{1-x^2}
\end{align}
```

![Groupes d'équations avec alignement simple](/tex/images/java/tutorial/latex-ams-math-2-11.png)

## 2.7. Alignements multiples

Un environnement « aligner » peut définir plusieurs points d'alignement. La mise en page contient autant de paires de colonnes que nécessaire et est similaire à un « tableau » avec le préambule de type « {rlrl...} ». En supposant qu'il se compose de *n* de telles paires de colonnes `rl`, le nombre de `&` par ligne sera de *2n - 1* : un pour l'alignement dans chaque paire de colonnes donnant *n* ; et *n - 1* `&` pour séparer les paires de colonnes.

L'environnement « aligner » répartit le matériau uniformément sur la largeur de l'écran. S'il y a de l'espace supplémentaire, il est réparti équitablement entre les paires de colonnes adjacentes et les deux marges d'affichage.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\begin{align} \text{Compare }
x^2 + y^2 &= 1 &                      x^3 + y^3 &= 1 \\
x              &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{align}
This example has three column-pairs.
\begin{align}
     x &= y        &        X &= Y      &   a &= b+c \\
    x' &= y'       &       X' &= Y'     &  a' &= b \\
x + x' &= y + y'   &   X + X' &= Y + Y' & a'b &= c'b
\end{align}
```

![Alignements multiples](/tex/images/java/tutorial/latex-ams-math-2-12.png)

La disposition du `flalign` est similaire, mais il n'y a pas d'espace dans les marges. Dans l'exemple suivant, vous pouvez voir que l'équation (3) tient sur une seule ligne de ce fait (alors que l'équation (2) ne le fait toujours pas).


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\begin{flalign} \text{Compare }
x^2 + y^2 &= 1               &   x^3 + y^3 &= 1 \\
        x &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{flalign}
This example has three column-pairs.
\begin{flalign}
     x &= y        &        X  &= Y        &     a &= b+c \\
    x' &= y'       &       X'  &= Y'       &    a' &= b \\
x + x' &= y + y'   &   X + X'  &= Y + Y'   &   a'b &= c'b
\end{flalign}
```

![flaligne](/tex/images/java/tutorial/latex-ams-math-2-13.png)

Dans les deux cas, l'espace minimum entre les paires de colonnes peut être défini en modifiant `\minalignsep`. La valeur par défaut est « 10pt » et peut être modifiée avec « \renewcommand », car il s'agit d'une macro-commande plutôt que d'un paramètre de longueur. L'exemple suivant démontre l'effet de la modification de `\minalignsep`.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
This example has two column-pairs.
\renewcommand\minalignsep{0pt}
\begin{align} \text{Compare }
x^2 + y^2 &= 1               &   x^3 + y^3 &= 1 \\
        x &= \sqrt {1-y^2}   &           x &= \sqrt[3]{1-y^3}
\end{align}
This example has three column-pairs.
\renewcommand\minalignsep{15pt}
\begin{flalign}
     x &= y        &        X  &= Y        &     a &= b+c \\
    x' &= y'       &       X'  &= Y'       &    a' &= b \\
x + x' &= y + y'   &   X + X'  &= Y + Y'   &   a'b &= c'b
\end{flalign}
```

![\effet minalignsep](/tex/images/java/tutorial/latex-ams-math-2-14.png)

L'exemple suivant illustre une utilisation très courante de « align ». Notez l'utilisation de `\text` pour produire du texte normal dans le matériel mathématique.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
     x &= y        &&   \text{by hypothesis} \\
    x' &= y'       &&   \text{by definition} \\
x + x' &= y + y'   &&   \text{by Axiom 1}
\end{align}
```

![L'utilisation de \text](/tex/images/java/tutorial/latex-ams-math-2-15.png)

## 2.8. Interruption des affichages : `\intertext`

Vous souhaiterez peut-être placer un petit morceau de texte entre les lignes d'un alignement d'affichage. Cela se fait avec la commande `\intertext`. Il est très important que toutes les propriétés d'alignement ne soient pas affectées par le texte, tandis que le texte lui-même est composé comme un paragraphe normal réglé sur la largeur d'affichage. L'alignement ne fonctionnera pas si vous terminez simplement l'affichage puis en démarrez un nouveau après le texte. Cette commande doit toujours suivre immédiatement une commande `\\` ou `\\*`.


``` tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
A_1 &= N_O (\lambda ; \Omega') - \phi ( \lambda ; \Omega') \\
A_2 &= \phi (\lambda ; \Omega') \phi (\lambda ; \Omega) \\
\intertext{and finally}
A_3 &= \mathcal{N} (\lambda ; \omega)
\end{align}
```

![La commande \intertext](/tex/images/java/tutorial/latex-ams-math-2-16.png)

> Les mots « et enfin » sont en dehors de l’alignement, dans la marge de gauche, mais les trois équations sont alignées.

## 2.9. Numérotation et balises des équations

Dans LaTeX, les balises pour les équations sont généralement générées automatiquement et sont essentiellement une représentation imprimée de « l’équation » du compteur LaTeX. Ceci est réalisé par LaTeX en trois étapes : définir la valeur du compteur « équation » ; formater la balise ; et l'imprimer dans la bonne position.

Les deux premières étapes sont étroitement liées, car la valeur du compteur « équation » n'est augmentée que lorsque l'étiquette correspondante est automatiquement imprimée. Jetons un coup d'œil à un environnement d'affichage comportant à la fois des formes avec et sans étoile. Seule la forme sans étoile modifie la valeur du compteur « équation », car elle marque automatiquement chaque équation logique, contrairement à la forme étoilée.
Lorsque vous devez supprimer le paramètre d'une balise pour une certaine équation logique dans la forme sans étoile, vous mettez `\notag` (ou `\nonumber`) *avant* le `\\`. Vous pouvez également remplacer les balises par défaut par celles de votre propre conception en utilisant la commande `\tag` *avant* le `\\`. L'argument de cette commande peut être un texte normal arbitraire qui est composé, entre parenthèses, comme balise pour cette équation.

Notez que l'incrémentation de la valeur du compteur est également supprimée lorsque `\tag` est utilisé. Cela signifie que le paramètre de balise par défaut n'est visuellement identique à `\tag{\theequation}` ; ils ne sont pas équivalents. La forme étoilée, `\tag*`, compose le texte dans son argument sans les parenthèses (et sans aucun autre élément qui pourrait autrement être ajouté avec une classe de document particulière).


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{align}
x^2+y^2 &= z^2 \label{eq:A} \\
x^3+y^3 &= z^3 \notag \\
x^4+y^4 &= r^4 \tag{$*$} \\
x^5+y^5 &= r^5 \tag*{$*$} \\
x^6+y^6 &= r^6 \tag{\ref{eq:A}$'$} \\
A_1 &= N_0 (\lambda ; \Omega') - \phi ( \lambda ; \Omega') \\
A_2 &= \phi (\lambda ; \Omega') \, \phi (\lambda ; \Omega) \tag*{ALSO (\theequation)} \\
A_3 &= \mathcal{N} (\lambda ; \omega)
\end{align}
```

![\tag, \tag*, \notag, \label et \ref](/tex/images/java/tutorial/latex-ams-math-2-17.png)

> Remarquez comment les commandes `\label` et `\ref` sont utilisées pour fournir une sorte de « numérotation relative » pour les équations.

## 2.10. Séquences de numérotation subordonnées

Le package *amsmath* prend également en charge ce que l'on appelle la « sous-numérotation des équations ». L'environnement « sous-équations » produit des balises de la forme (2a), (2b), (2c), etc. Ce schéma de numérotation est basé sur deux compteurs LaTeX normaux : "parentequation" et "equation". Toutes les équations étiquetées dans un environnement de « sous-équations » utilisent ce schéma.

L'exemple suivant montre que la balise peut être redéfinie dans une certaine mesure, mais notez que la redéfinition de `\theequation` doit être placée dans l'environnement `subequations`.


```tex
\usepackage{amsmath}
% -------------------------------------------------------------------------------
\begin{subequations} \label{eq:1}
\begin{align}
           f &= g \label{eq:1A} \\
          f' &= g' \label{eq:1B} \\
\mathcal{L}f &= \mathcal{L}g \label{eq:1C}
\end{align}
\end{subequations}

\begin{subequations} \label{eq:2}
\renewcommand\theequation{\theparentequation\roman{equation}}
\begin{align}
           f &= g \label{eq:2A} \\
          f' &= g' \label{eq:2B} \\
\mathcal{L}f &= \mathcal{L}g + K \label{eq:2C}
\end{align}
\end{subequations}
Note the relationship between~\eqref{eq:1}
and~\eqref{eq:2}: only~\ref{eq:1C} and~\ref{eq:2C} differ.
```

![Séquences de numérotation subordonnées](/tex/images/java/tutorial/latex-ams-math-2-18.png)

> L'environnement `subequations` doit apparaître *en dehors* des affichages qu'il affecte. Il ne doit pas non plus être imbriqué dans lui-même. Le compteur d'équations « principales » est incrémenté à chaque utilisation de cet environnement. Une commande `\label` dans l'environnement `subequations` mais en dehors de toute équation individuelle (logique) produira un `\ref` vers le numéro parent (par exemple, vers 2 plutôt que vers 2i).

## 2.11. Réinitialisation du compteur d'équation

Il est courant d'avoir des équations numérotées dans des sections ou des chapitres avec des balises de la forme (1.1), (1.2), ..., (2.1), (2.2), ... . Le package `amsmath` fournit un moyen simple de configurer cela avec la déclaration `\numberwithin`.

Par exemple, pour obtenir des balises d'équation incluant le numéro de section, le compteur d'équation étant automatiquement réinitialisé pour chaque section, mettez cette déclaration dans le préambule : `\numberwithin{equation}{section}`.

## Annexe A. Rendu d'équations LaTeX avec l'API Aspose.TeX

Nous allons maintenant voir comment l'API Aspose.TeX vous permet d'obtenir des équations LaTeX sous forme de figures autonomes.

Disons que vous devez obtenir une équation sous forme d'image raster afin de pouvoir l'utiliser dans une publication non-TeX (une page Web, par exemple). À l'aide de l'API Aspose.TeX, vous pouvez procéder comme suit :


```csharp
string equation = @"\begin{equation} (a-b)^2 = a^2-2ab+b^2 \end{equation}
\[ \cos2\eta = \cos^2\eta-\sin^2\eta \]";
Aspose.TeX.Features.PngMathRendererOptions options = new Aspose.TeX.Features.PngMathRendererOptions();
using (Stream stream = File.Open("your-file-name-and-path", FileMode.Create))
{
    new Aspose.TeX.Features.PngMathRenderer().Render(equation, stream, options, out System.Drawing.SizeF size);
    // Below is the short version for rendering with SVG
    // new Aspose.TeX.Features.SvgMathRenderer().Render(equation, stream, new Aspose.TeX.Features.SvgMathRendererOptions(), out System.Drawing.SizeF size);
}
```

Comme vous pouvez le constater, l'API est également capable de convertir une équation LaTeX en fichier SVG. Et c'était un exemple d'utilisation d'Aspose.TeX pour .NET. Vous trouverez ci-dessous le code équivalent pour la version Java.


```java
String equation = "\\begin{equation} (a-b)^2 = a^2-2ab+b^2 \\end{equation}\r\n" +
		"\\[ \\cos2\\eta = \\cos^2\\eta-\\sin^2\\eta \\]";
Size2D size = new Size2D.Float();
com.aspose.tex.PngMathRendererOptions options = new com.aspose.tex.PngMathRendererOptions();
final OutputStream stream = new FileOutputStream(Helper.getOutputFile(Path.combine(getCurrentPath(), "doc.png")));
try
{
    new com.aspose.tex.PngMathRenderer().render(equation, stream, options, size);
}
finally {
    stream.close();
}
```

Vous pouvez trouver des détails sur l'utilisation des options du moteur de rendu dans l'article sur le rendu des formules mathématiques LaTeX avec [Aspose.TeX pour .NET](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) ou [Aspose.TeX pour Java](/tex/{{lang.url-fragment}}java/latex-math-formula-rendering/). Mais l’un d’eux est important pour nous ici. En utilisant cette option, vous pouvez spécifier le préambule du document LaTeX dont vous auriez besoin pour obtenir le résultat souhaité. (Ci-après, nous présenterons uniquement la version C# du code source.)


```csharp
// The preamble for the very first example on this page
options.Preamble = @"\usepackage[leqno]{amsmath}";
```

Vous pouvez également utiliser cette option lorsque vous avez besoin de disposer une équation dans une zone plus étroite que celle définie par LaTeX `\textwidth` par défaut. Vous avez deux options pour atteindre cet objectif :


```csharp
// The preamble for the 2.7 examples
options.Preamble = @"\usepackage[textwidth=232pt]{geometry}
\usepackage{amsmath}";
// or
options.Preamble = @"\usepackage{amsmath}
\setlength{\textwidth}{232pt}";
```

Dans l'API Aspose.TeX, le préambule suivant est utilisé par défaut, donc à moins que vous n'ayez besoin de transmettre des options au package `amsmath` ou de modifier la valeur par défaut `\textwidth` ou autre chose, il n'est pas nécessaire de spécifier le préambule dans les options du moteur de rendu :


```tex
\usepackage{amsmath}
\usepackage{amsfonts}
\usepackage{amssymb}
```

## Annexe B. Rendu d'équations LaTeX avec l'application Web Aspose LaTeX Equation

Il existe également l'[application Web LaTeX Equation Editor](https://products.aspose.app/tex/equation-editor) qui vous permet de modifier et d'afficher des équations LaTeX. Vous pouvez saisir votre équation dans le champ de texte et cliquer sur le bouton *Afficher* pour voir le résultat. Vous pouvez également utiliser le panneau de configuration situé au-dessus du champ pour créer l'équation en sélectionnant une catégorie de sous-expression, puis une sous-expression, puis en modifiant l'argument, le cas échéant. Vous pouvez trouver le préambule et d'autres options sous le champ *Formule*.