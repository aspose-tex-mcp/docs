---
translation: true
template: /templates/_template-java.md
linktitle: Comment utiliser les polices LaTeX dans le texte
title: 3. Comment utiliser les polices LaTeX dans le texte
weight: 30
url: /java/latex-text-fonts/
keywords: latex, polices latex, commandes de police de texte latex, latex grand, taille de police latex
description: Cet article couvre les commandes de polices LaTeX qui modifient indépendamment différents attributs de police pour une utilisation dans du texte normal.
lastmod: "2024-09-27"
---

{{<section overview>}}

Lorsque vous rédigez un document LaTeX, les balises de balisage utilisées pour structurer le document choisissent automatiquement les polices appropriées. Par exemple, pour un en-tête de section, des attributs de police tels qu'une grande taille et une épaisseur en gras sont définis par la classe du document et appliqués lorsqu'une commande `\section` est utilisée. Par conséquent, vous avez rarement besoin de spécifier directement les attributs de police.

Mais parfois, c'est nécessaire. Par exemple, vous souhaiterez peut-être choisir une famille de polices différente (ou un autre attribut de police global) pour le texte principal. Une telle modification peut souvent être effectuée simplement en spécifiant un package approprié.

Un autre cas est celui où vous souhaitez marquer certains fragments du document comme spéciaux - par exemple, pour désigner des acronymes, des exemples ou des noms de sociétés. Si vous choisissez d'utiliser, par exemple, une police sans empattement pour ces fragments, vous pouvez le faire en entourant les noms de sociétés de `\textsf{...}`. Mais la meilleure pratique consiste à définir une nouvelle commande (par exemple, « \Company ») à cet effet. La définition de commandes individuelles pour des éléments logiquement différents facilite la modification ultérieure du formatage de manière cohérente.

Vous souhaiterez peut-être également composer un tableau dans une taille plus petite pour qu'il tienne sur une page. Étant donné que les classes de documents ne peuvent formater automatiquement les documents que dans une certaine mesure, ce souhait est légitime. Il s’ensuit qu’une mise en forme manuelle, tout comme l’insertion de sauts de page, est souvent nécessaire pour créer une version finale. Malheureusement, le formatage explicite rend l'utilisation ultérieure du document difficile et sujette aux erreurs. Par conséquent, l’utilisation directe de commandes de changement de police dans un document doit être minimisée. Cela est également vrai pour toutes les commandes de formatage visuel.


## 3.1. Comment utiliser les commandes de polices dans LaTeX standard

La police utilisée pour le texte principal d'un document est appelée *police principale*, *police corporelle* ou *police normale*. Il est automatiquement sélectionné au début du document et dans certaines constructions, telles que les notes de bas de page et les figures. Les titres de section et autres balises de balisage logique passent automatiquement à une police ou une taille différente, en fonction de la classe du document. Par conséquent, l’introduction du balisage logique correct est la seule action requise de la part de l’auteur. Cependant, il peut parfois être souhaitable de surligner manuellement certaines parties du texte en choisissant une police de caractères appropriée. Cela se fait avec les commandes décrites ci-dessous.

Il existe deux formes pour la plupart des commandes de changement de police : une commande avec un argument, telle que `\textbf{...}`, et une déclaration, telle que `\bfseries`. La forme déclarative ne prend aucun argument mais indique plutôt à LaTeX qu'à partir de maintenant (jusqu'à la fin du groupe actuel d'accolades ou d'environnements), il doit se comporter d'une manière particulière. Cela signifie que vous ne devriez pas écrire quelque chose comme `\bfseries{...}`, car cela mettrait tout en gras à partir de ce point jusqu'à la fin de l'environnement actuel.

Il est préférable d'utiliser les commandes de police avec un seul argument pour modifier les polices de mots individuels ou de phrases courtes dans votre document. Pour les fragments plus longs, vous devez utiliser le formulaire d'environnement de la déclaration, comme indiqué dans l'exemple ci-dessous :

```tex
Some words in this sentence are \begin{bfseries}typeset in bold letters.
The bold typeface\end{bfseries} continues here. 
```

![La forme d'environnement de \bfseries](/tex/images/java/tutorial/latex-font-selection-3-1.png)

Les formes déclaratives elles-mêmes sont souvent meilleures dans la définition de nouveaux environnements ou commandes.

> Il est également important que les commandes de police avec un argument n'autorisent pas de sauts de paragraphe dans leurs arguments.

### La police principale du document
En utilisant la commande `\textnormal` ou la déclaration `\normalfont`, vous pouvez passer à la police principale du document. Ils n'apparaissent généralement que dans les définitions de commandes ou d'environnements lorsqu'il est important de définir un moyen de toujours composer dans la même police, quelles que soient les conditions environnantes. Par exemple, la commande permettant de saisir les noms des commandes LaTeX ressemblerait à ceci :

```tex
\newcommand\Lcs[1]{{\normalfont\ttfamily\textbackslash#1}%}
```

L'utilisation de `\normalfont` empêche les noms de commandes d'apparaître en italique, même dans le texte composé en italique.

### Familles de polices standards

Par défaut, LaTeX gère trois familles de polices : une police de texte avec empattement, accessible avec la commande `\textrm` ; une police de texte sans empattement, accessible par `\textsf` ; et une police de machine à écrire (à espacement fixe), accessible par `\texttt`. Les formes de déclaration de ces commandes sont respectivement `\rmfamily`, `\sffamily` et `\ttfamily`.

Les noms exacts des familles de polices externes accessibles par ces commandes dépendent de la classe du document mais peuvent être modifiés dans le préambule ou par packages. Par défaut, la famille de polices avec empattement est **Computer Modern Roman**, la famille sans empattement est **Computer Modern Sans** et la famille de machines à écrire est **Computer Modern Typewriter**. Si vous utilisez une configuration différente, veillez à définir ces familles de polices par défaut afin que les polices puissent être mélangées sans conflits visuels. Il est également important de s'assurer que les polices externes sont disponibles dans la résolution appropriée pour le périphérique de sortie ciblé.

La plupart des classes de documents définissent la police avec empattement, accessible par `\textrm`, comme police principale du document, donc la commande `\textrm` n'est pas souvent utilisée. Mais si un concepteur de documents a choisi une police sans empattement comme police principale, `\textrm` serait la famille de polices avec empattement alternative.

### Série de polices standard

Dans LaTeX, la *série* est une combinaison de deux attributs : la largeur et le poids (audace). LaTeX permet de changer la série avec deux commandes : `\textmd` et `\textbf`. Les déclarations correspondantes sont respectivement `\mdseries` et `\bfseries`. La première commande sélectionne une police avec des valeurs moyennes pour la largeur et le poids, tandis que la seconde passe à une série plus grasse. Encore une fois, les valeurs réelles dépendent de la classe de document et de ses options ou packages ultérieurs. Dans une configuration par défaut, `\textbf` passe à une version étendue en gras de la police actuelle, tandis que `\textmd` revient à la version de largeur moyenne et de poids moyen de la police actuelle.

### Formes de police standard

La *forme* de la police actuelle est le troisième attribut de police qui peut être modifié indépendamment des autres. La forme par défaut pour la plupart des documents est la forme verticale, accessible avec la commande `\textup` ou la déclaration `\upshape` si nécessaire.

Les commandes les plus couramment utilisées semblent être `\textit` et `\textsc`, qui passent respectivement à une forme de police en italique ou en petites majuscules. Les déclarations correspondantes sont `\itshape` et `\scshape`.

La commande `\textsl` (sa forme de déclaration est `\slshape`) passe à la forme inclinée. Une famille de polices contient souvent uniquement une forme italique ou inclinée, bien que Computer Modern Roman contienne les deux.

Au moment où l'on passe d'un caractère incliné à un caractère vertical, les personnages se rapprochent généralement trop près, surtout si le dernier caractère incliné est doté d'un ascendant. La quantité appropriée d'espace supplémentaire qui doit être ajoutée à cette limite est appelée **correction italique**. La largeur exacte de cet espace dépend du caractère individuel et est stockée dans le fichier `.tfm`. Les commandes de police avec arguments ajoutent automatiquement la correction italique, mais lorsque des déclarations sont utilisées, elle doit être insérée manuellement en utilisant `\/`. Pour une police verticale, la correction italique des caractères est généralement nulle ou très faible, bien qu'il existe quelques exceptions. L'exemple suivant montre comment utiliser correctement les déclarations de changement de forme qui passent à des formes inclinées.

```tex
\raggedright
When switching back from {\itshape italic\/} or {\slshape slanted\/} shapes to an upright font one
should add the {\itshape italic correction}, except when a small punctuation character follows.
```

![La correction italique](/tex/images/java/tutorial/latex-font-selection-3-2.png)
Les petites majuscules sont parfois utilisées dans les titres ou pour formater les noms. Pour ce dernier cas, vous pouvez par exemple définir la commande `\name` comme suit :

```tex
\newcommand\name[1]{\textsc{#1}}
```

Alternativement, vous pouvez utiliser deux déclarations :

```tex
\newcommand\name[1]{{\normalfont\scshape #1}}
```

La première commande passe simplement à la forme en petites majuscules, tandis que la seconde forme réinitialise initialement tous les attributs de police à leurs valeurs par défaut. L'option à choisir dépend des polices disponibles et du type de document. Avec Computer Modern, seules les familles Roman et Typewriter contiennent des formes en petites majuscules, donc la deuxième définition pourrait être préférée dans certaines applications car elle utilisera des petites majuscules (bien que avec empattements) même dans un contexte `\sffamily`. La première commande demanderait une police de forme de série moyenne, en petites majuscules, dans la famille Computer Modern Sans. Cette police n'est pas disponible, donc LaTeX essaiera de trouver un substitut en modifiant d'abord l'attribut shape par défaut. Par conséquent, vous n’obtiendrez pas de petites capitalisations.

Une autre commande de forme spéciale LaTeX est la commande `\emph`, qui met l'accent sur les fragments dans le texte normal. Sa forme déclarative est `\em`. Par tradition, les mots soulignés dans le texte sont mis en italique ; mais si l'on souhaite mettre l'accent sur un fragment du texte déjà en italique, on revient généralement à la police verticale. La commande `\emph` prend en charge cette convention en passant à la forme `\itshape` si la police actuelle est verticale, et à la forme `\upshape` si la police actuelle est déjà inclinée (c'est-à-dire si la forme est `\itshape ` ou `\slshape`). Ainsi, l'utilisateur n'a pas à se soucier de l'état actuel du texte lorsqu'il utilise la commande `\emph` ou la déclaration `\em`.

```tex
{\em Nevertheless, one has to be careful about the\/ {\em proper\/} use of italic corrections
on both ends of the emphasized text}. It is therefore better to use the \verb=\emph= command,
which \emph{automatically} takes care of the italic correction on both sides.
```

![Mise en valeur des fragments de texte](/tex/images/java/tutorial/latex-font-selection-3-3.png)

### Tailles de police standard

Il existe 10 commandes de changement de taille dans LaTeX. Ces commandes n'ont pas de forme de commande correspondante avec un seul argument puisque les changements de taille de police ne sont normalement utilisés que dans les définitions des commandes.

![Tailles de police standard](/tex/images/java/tutorial/latex-font-selection-3-4.png)

La taille sélectionnée par ces commandes dépend des paramètres de la classe de document et éventuellement des options (par exemple, « 11pt ») spécifiées avec celle-ci. En général, `\normalsize` correspond à la taille principale du document, et les commandes de changement de taille forment une séquence ordonnée commençant par `\tiny` comme la plus petite et allant jusqu'à `\Huge` comme la plus grande taille. Il peut arriver que plusieurs commandes fassent référence à la même taille. Par exemple, lorsqu'un grand `\normalsize` est choisi, `\Huge` peut être identique à `\huge`. Mais la commande est toujours honorée.

Les commandes de changement de taille pour les principales tailles de texte (c'est-à-dire `\normalsize`, `\small` et `\footnotesize`) affectent généralement l'espacement autour des listes et des affichages. Par conséquent, pour changer leur comportement, il ne faut pas simplement remplacer leur définition par un appel à `\fontsize`, mais plutôt partir de leur définition originale, comme documentée dans `classes.dtx`.

## 3.2. Comment combiner les commandes de polices standard

Comme nous l'avons déjà montré, les commandes et déclarations standard de changement de police peuvent être combinées, ce qui aboutit à la sélection d'une police qui correspond à la combinaison d'attributs de police. Voir l'exemple ci-dessous :

```tex
One can typeset a text {\sffamily\bfseries\large in a large sans serif
bold typeface} but note the unchanged leading! \LaTeX{} uses the value
in force at the \emph{end} of the paragraph!
```

![Combinaisons de commandes de polices LaTeX](/tex/images/java/tutorial/latex-font-selection-3-5.png)

En interne, la commande `\sffamily` passe à la famille par défaut sans empattement, puis `\bfseries` passe à la série grasse par défaut dans cette famille, et enfin `\large` sélectionne une grande taille mais laisse tous les autres attributs inchangés. L'interligne semble rester inchangé car la portée de `\large` se termine avant la fin du paragraphe. Les fichiers de métriques de polices sont chargés pour toutes les polices intermédiaires, même si ces polices ne sont jamais utilisées. Dans l'exemple ci-dessus, ils seraient "sans serif medium 10pt" après le `\sffamily`, puis "sans serif bold extended 10pt" après le `\bfseries`, et, enfin, "sans serif bold extended 14pt", qui est la police réellement utilisée. Par conséquent, de telles commandes de haut niveau peuvent forcer la sélection de polices de LaTeX à charger inutilement des polices qui ne sont jamais utilisées. Il n'y a qu'une légère perte de vitesse de traitement lorsqu'une combinaison donnée est utilisée pour la première fois. Mais si vous avez de nombreuses combinaisons différentes de ce type, vous devriez mieux envisager de les définir en termes de [déclarations primitives de changement de police](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/).

## 3.3. Comparaison des commandes et déclarations de polices

Les commandes de changement de police avec arguments commencent toutes par `\text...` (sauf `\emph`) pour souligner qu'elles sont destinées à être utilisées dans du texte normal. L'utilisation de telles commandes au lieu des formulaires déclaratifs présente l'avantage de maintenir la cohérence avec les autres constructions LaTeX. Ils sont destinés à la composition de courts morceaux de texte dans une famille, une série ou une forme spécifique. Le tableau suivant montre l'effet de ces commandes.

![Commandes et déclarations](/tex/images/java/tutorial/latex-font-selection-3-6.png)

Un autre avantage de ces commandes est qu'elles insèrent automatiquement toute correction italique nécessaire de part et d'autre de leur argument. Ainsi, vous n'avez pas à vous soucier de manquer des corrections en italique lors du changement de police.

La correction italique insérée automatiquement est erronée dans très peu de situations. Il est généralement recommandé d'omettre la correction de l'italique si un petit caractère de ponctuation (une virgule ou un point) suit directement le changement de police. Vous pouvez définir dans quels cas la correction de l'italique doit être supprimée. Cela se fait en spécifiant les caractères qui doivent annuler une correction italique précédente dans la liste `\nocorrlist`. La définition par défaut de cette commande est

```tex
\newcommand{\nocorrlist}{,.}
```

Il est également possible de supprimer la correction de l'italique dans des cas individuels. A cet effet, la commande `\nocorr` est fournie. Notez que vous devez mettre `\nocorr` à l'extrémité gauche ou droite à l'intérieur de l'argument des commandes `\text...`, selon le côté du fragment qui nécessite la suppression de la correction de l'italique.

```tex
\emph{When using the \LaTeX{} high-level font commands, the \emph{proper} use of
italic corrections is automatically taken care of}. Only \emph{sometimes} one has
to help \LaTeX{} by adding a \verb=\nocorr= command.
```

![La correction italique](/tex/images/java/tutorial/latex-font-selection-3-7.png)

En revanche, les formulaires de déclaration sont souvent plus adaptés pour définir vos propres commandes ou environnements.

```tex
% Part of the preamble
\newenvironment{bfitemize}{\begin{itemize}%
  \normalfont\bfseries\raggedright}{\end{itemize}}
-----------------------------------------------
\begin{bfitemize}
\item This environment produces boldface items.
\item It is defined in terms of \LaTeX's
\texttt{itemize} environment and NFSS declarations.
\end{bfitemize}
```

![La liste des éléments en gras](/tex/images/java/tutorial/latex-font-selection-3-8.png)

## 3.4. Comment accéder à tous les caractères d'une police

Même si un caractère existe dans une police, il est parfois impossible de le saisir depuis le clavier. De nombreux caractères utiles sont accessibles via des commandes comme `\ss` ou `\AE`. Certains caractères peuvent être implicitement générés à partir de séquences de lettres comme `ffi`, qui produit la ligature "ffi", et `---`, qui produit le long tiret dans les polices TeX standard.

De plus, la commande `\symbol` vous permet d'accéder à n'importe quel caractère d'une police en donnant son numéro dans le schéma de codage actuel sous forme de nombre décimal, octal (précédé de `'`) ou hexadécimal (précédé de `"`). .

```tex
\fontencoding{T1}\selectfont
-----------------------------------------------
In the font encoding (\texttt{T1}), characters like \symbol{"DE},
symbol{'237}, and \symbol{32} are included and can be accessed with
the \verb=\symbol= command.
```

![La commande \symbol](/tex/images/java/tutorial/latex-font-selection-3-9.png)

## 3.5. Comment changer les polices de texte par défaut

Si vous souhaitez modifier facilement l'apparence générale d'un document, vous pouvez utiliser les hooks intégrés de LaTeX qui modifient le comportement des commandes de changement de police de haut niveau évoquées précédemment. Les valeurs de ces hooks peuvent être définies dans les fichiers du package ou dans le préambule d'un document en utilisant `\renewcommand`. Voici la liste des crochets :

![Les hooks pour le changement de police de haut niveau](/tex/images/java/tutorial/latex-font-selection-3-10.png)
Par exemple, si vous écrivez dans le préambule

```tex
\renewcommand\familydefault{cmss}
```

un document entier sortirait dans Computer Modern Sans, car cette redéfinition modifie la famille de polices de la police principale utilisée par LaTeX. En détail, la police principale du document est déterminée par les valeurs de `\encodingdefault`, `\familydefault`, `\seriesdefault` et `\formedefault`. Cela signifie que vous devez vous assurer que ces commandes sont définies de telle manière que leur combinaison pointe vers une forme de police existante dans les tables internes de LaTeX.

La valeur par défaut de `\encodingdefault` (`OT1`) sert en fait à la compatibilité. Cela signifie que LaTeX suppose que la plupart des polices utilisent l'encodage d'origine. Dans la plupart des cas, il est préférable d'utiliser le codage « T1 » car il contient de nombreux glyphes supplémentaires qui ne sont pas disponibles avec « OT1 » et permet une césure appropriée pour les mots avec des caractères accentués. De nos jours, certaines polices ne prennent pas du tout en charge « OT1 » car elles sont conçues pour être utilisées avec « T1 ».

Il est important de se rappeler que toutes les polices ne peuvent pas être utilisées par défaut pour l’encodage de documents. Une condition préalable est que le codage inclue la plupart des lettres ASCII visibles dans leurs positions standard. Le `\encodingdefault` peut être modifié en chargeant le package `fontenc` avec une ou plusieurs options.

Le paramètre initial de `\familydefault` signifie que la modification de `\rmdefault` changera implicitement `\familydefault` à la nouvelle valeur, tant qu'aucun paramètre spécial pour `\familydefault` n'est défini. Mais si `\familydefault` est modifié, `\rmdefault` n'est pas affecté.