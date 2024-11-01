---
translation: true
template: /templates/_template-java.md
linktitle: 4. Différents caractères dans les formules mathématiques
title: Différents caractères dans les formules mathématiques
weight: 40
url: /java/latex-math-symbol-classes/
keywords: latex, formules mathématiques en latex, mathématiques en latex, symboles mathématiques en latex, variables mathématiques en latex, opérations binaires mathématiques en latex, relations mathématiques en latex, accents mathématiques en latex
description: Cet article traite de la division des symboles mathématiques TeX en classes et de la signification de ces classes en mathématiques.
lastmod: "2024-09-27"
---

{{<section overview>}}

Les 52 lettres (« A » à « Z » et « a » à « z ») désignent des symboles italiques, qu'un mathématicien appellerait « variables ». TeX les appelle simplement des « symboles ordinaires », car ils constituent l'essentiel des formules mathématiques. LaTeX traite également les 18 caractères suivants

``0 1 2 3 4 5 6 7 8 9 ! ? . | ` @ "``

comme des symboles ordinaires, ce qui signifie qu'il n'insère aucun espace supplémentaire lorsque ces symboles apparaissent les uns à côté des autres ou à côté des lettres. Contrairement aux lettres, ces 18 caractères restent en caractères romains dans les formules.

Les trois caractères `+`, `-` et `*` sont appelés « opérations binaires », car ils opèrent sur deux parties de la formule. L'astérisque (*) est rare, mais il se comporte également comme une opération binaire. Voici quelques exemples d’opérations binaires de composition lorsqu’elles apparaissent à côté de symboles ordinaires :

![Opérations binaires](/tex/images/java/tutorial/latex-math-4-1.png)

TeX ne traite pas `/` comme une opération binaire car cela entraînerait un espacement incorrect dans des formules telles que `$1/2$`. Ainsi, TeX traite `/` comme un symbole ordinaire.

Voici quelques autres exemples d'opérations binaires :

![Opérations binaires plus complexes](/tex/images/java/tutorial/latex-math-4-2.png)

Par ailleurs, les opérations binaires sont traitées comme des symboles ordinaires si elles ne se produisent pas entre deux quantités sur lesquelles elles peuvent opérer. Ainsi, aucun espace supplémentaire n'est inséré à côté de +, - et * dans des cas comme les suivants :

![Opération binaire comme symboles ordinaires](/tex/images/java/tutorial/latex-math-4-3.png)

Les exemples suivants montrent que les opérations binaires peuvent être utilisées comme symboles ordinaires dans les exposants et les indices :

![Opération binaire comme symboles ordinaires en exposant et en indice](/tex/images/java/tutorial/latex-math-4-4.png)

LaTeX traite les quatre caractères `=`, `<`, `>` et `:` comme des « relations » car ils expriment une relation entre deux quantités. De telles relations ont une signification assez différente des opérations binaires, et les symboles sont composés quelque peu différemment :

![Relations](/tex/images/java/tutorial/latex-math-4-5.png)

Les deux caractères ',' (virgule) et ';' (point-virgule) sont traités comme des signes de ponctuation dans les formules, ce qui signifie que TeX met un peu d'espace supplémentaire après eux mais pas avant eux.

![Marques de ponctuation](/tex/images/java/tutorial/latex-math-4-6.png)

Il n'est pas habituel de mettre un espace supplémentaire après un « ». (point) dans les formules, donc TeX traite un point comme un symbole ordinaire. Si vous souhaitez que le caractère ':' soit un signe de ponctuation au lieu d'une relation, appelez-le simplement `\colon`. Et si vous souhaitez qu’une virgule soit traitée comme un symbole ordinaire, mettez-la simplement entre accolades. TeX traite tout ce qui est entre accolades comme un symbole ordinaire.

![Côlon comme ponctuation et virgule comme symbole ordinaire](/tex/images/java/tutorial/latex-math-4-7.png)

Les caractères `(` et `[` sont appelés « ouvertures », tandis que `)` et `]` sont appelés « fermetures ». Ils agissent un peu comme des symboles ordinaires, mais ils aident TeX à décider quand une opération binaire n'est pas réellement utilisée de manière binaire.

Enfin, LaTeX réserve les 10 autres caractères :

`\ $ % # & ~ { } _ ^`

Vous ne pouvez pas les utiliser en mode mathématique. Bien que '{' et '}' spécifient un regroupement, les commandes `\{` et `\}` peuvent être utilisées pour obtenir '{' comme ouverture et '}' comme fermeture.

Les caractères spéciaux `^` et `_` ne doivent être utilisés que dans les formules. À l'inverse, les noms des symboles mathématiques comme `\alpha` et `\approx`, ainsi que les commandes pour les opérations mathématiques comme `\overline`, ne doivent pas apparaître dans le texte ordinaire. De plus, une ligne vide ou `\par` n'est pas autorisée en mode mathématique.

Les mathématiciens aiment également utiliser les accents sur les lettres pour indiquer efficacement les relations entre les objets mathématiques. Il augmente également considérablement le nombre de symboles disponibles sans augmenter le nombre de polices nécessaires. Les accents mathématiques sont quelque peu différents des accents utilisés dans le texte ordinaire. L'espacement n'est pas le même ; TeX suit des règles spéciales pour les accents dans les formules, afin que les deux types d'accents ne soient pas confondus. LaTeX fournit les accents mathématiques suivants :

![Accents](/tex/images/java/tutorial/latex-math-4-8.png)

Les neuf premiers d'entre eux sont appelés `\^`, `\v`, `\~`, `\'`, ``\` ``, `\.`, `\"`, `\u` et `\=`, respectivement, lorsqu'ils apparaissent dans le texte ; `\vec` est un accent qui apparaît uniquement dans les formules. TeX émettra un message d'erreur si vous essayez d'utiliser `\^` ou `\v`, etc., dans des formules, ou si vous essayez d'utiliser `\hat` ou `\check`, etc., dans du texte ordinaire.

Il est généralement préférable de définir des macros pour les lettres accentuées dont vous avez fréquemment besoin. Vous pouvez mettre

```tex
\def\Ahat{{\hat A}}
\def\chat{{\hat c}}
\def\scheck{{\check s}}
```

au début d'un fichier LaTeX. Cela vous évite beaucoup de frappes au clavier et rend le fichier plus facile à lire.

Lorsque les lettres *i* et *j* sont accentuées dans les formules mathématiques, vous devez utiliser des bases de symboles sans points appelées « \imath » et « \jmath ». Ainsi, un article qui utilise hat'ed i et j pourrait commencer par les définitions suivantes :

```tex
\def\ihat{{\hat\imath}}
\def\jhat{{\hat\jmath}}
```

Il est possible de mettre des accents mathématiques sur n'importe quelle sous-formule. Mais cela ne sert généralement pas à grand-chose, car TeX centre simplement l'accent sur l'ensemble de la sous-formule. En particulier, un accent `\bar` reste toujours de la même taille ; ce n'est pas comme `\overline`, qui grandit avec la formule en dessous. Certaines personnes préfèrent la ligne plus longue de `\overline` même lorsqu'elle s'applique à une seule lettre. Cependant, LaTeX propose deux accents qui grandissent ; ils sont appelés `\widehat` et `\widetilde`. Regardons maintenant les exemples de cas évoqués dans le présent paragraphe.

![Accents larges](/tex/images/java/tutorial/latex-math-4-9.png)

Le dernier exemple montre la taille maximale disponible.