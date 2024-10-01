---
translation: true
template: /templates/_template-java.md
linktitle: 2. Caractéristiques des polices
title: Caractéristiques de la police
weight: 20
url: /java/latex-font-attributes/
keywords: latex, polices latex, encodages de polices latex, nfss
description: Cet article couvre les classifications des polices LaTeX en ce qui concerne diverses caractéristiques des polices. Il mentionne également le concept d'encodage de polices LaTeX.
lastmod: "2024-09-27"
---

{{<section overview>}}

Les polices peuvent être divisées en classes individuelles qui se chevauchent en fonction de diverses caractéristiques. Il s’avère souvent utile de connaître ces caractéristiques lorsque l’on doit décider quelle famille de polices utiliser dans un contexte spécifique. Voir également l'article de documentation de [Aspose.Font](https://products.aspose.com/font/) sur les [différents types de polices](/font/net/what-is-font/font-types/).

## 2.1. Polices proportionnelles et à espacement fixe

Les polices peuvent être proportionnelles ou à espacement fixe. Dans une police proportionnelle, les glyphes ont des largeurs différentes selon leur forme.  Dans le même temps, dans une police à espacement fixe, tous les glyphes ont la même largeur. Les espaces supplémentaires autour des glyphes des polices à espacement fixe rendent plus difficile la reconnaissance des limites des mots et rendent ainsi le texte saisi dans de telles polices moins lisible. En revanche, les polices proportionnelles (ou *typographiques*) permettent généralement de placer plus de mots sur une page et sont plus lisibles que les polices à espacement fixe. Voir la figure ci-dessous :

![Polices proportionnelles et à espacement fixe](/tex/images/java/tutorial/latex-font-selection-2-1.png)
 
Bien que les polices à espacement fixe semblent moins lisibles, elles ont toujours leur utilité. Un exemple est celui des tableaux ou des listes de programmes où un bon alignement du contenu est important. Vous trouverez toujours des programmes informatiques affichés dans une police à espacement fixe sur n'importe quel ordinateur depuis le livre. Cela distingue facilement les programmes du texte environnant.

Vous pouvez même choisir une police à espacement fixe comme police de base pour un document complet, car une telle police semble faite à la main lorsqu'elle est utilisée avec des paragraphes injustifiés, ce qui lui donne une saveur de machine à écrire.

## 2.2. Polices avec et sans empattement

Dans certaines polices, les glyphes ont des *serifs*, alors que dans d'autres, ils n'en ont pas. Ce fait nous amène à une autre classification utile. Les empattements sont de minuscules traits horizontaux aux extrémités des glyphes. À l’origine, ils étaient fabriqués au ciseau lorsque les chapiteaux romains étaient gravés dans la pierre. C'est pourquoi les polices avec empattement sont souvent appelées polices *Roman*.

![Polices avec et sans empattement](/tex/images/java/tutorial/latex-font-selection-2-2.png)
 
Les polices à empattement ont longtemps été considérées comme plus lisibles car elles donnaient à l'œil plus d'indices d'identification. Mais des recherches spécialisées ont montré que la vitesse de lecture n’est pas sensiblement affectée par l’absence d’empattements.

## 2.3. Familles de polices et leurs attributs

Outre les classifications grossières évoquées ci-dessus, les polices sont regroupées en familles de polices. Les membres d’une famille de polices partagent des principes de conception communs et se distinguent par des variations de taille, d’épaisseur, de largeur et de forme.

### Formes de police

Presque toutes les familles de polices ont une forme appelée forme *droite*. La police que vous lisez actuellement est de forme verticale. Cette forme de police est généralement utilisée pour saisir du texte normal.

Une autre forme importante incluse dans la plupart des familles est la forme *italique*, qui ressemble à

![Texte en italique](/tex/images/java/tutorial/latex-font-selection-2-3.png)
 
Les glyphes italiques sont inclinés vers la droite et les lettres sont dessinées différemment de leurs homologues verticaux, comme le montre la figure ci-dessous :

![Comparaison des formes verticales, verticales italiques et italiques](/tex/images/java/tutorial/latex-font-selection-2-4.png)
 
La première ligne montre les lettres de la famille Computer Modern Serif en forme verticale, et la troisième ligne montre les mêmes lettres en italique. Pour rendre plus apparente la différence de dessin, la deuxième ligne donne les lettres italiques sans l'inclinaison habituelle. En d’autres termes, ce sont des lettres italiques en position verticale.

Les familles de polices San Serif n'ont souvent pas de forme italique appropriée ; au lieu de cela, ils ont une forme *inclinée* dans laquelle les caractères droits réguliers sont inclinés vers la droite. Ces polices sont aussi souvent appelées *oblique* ou *inclinée*.
Une autre forme de police courante est la forme *petites majuscules*, dans laquelle les lettres minuscules sont représentées comme des majuscules avec une hauteur réduite. Si la forme en petites majuscules n'est pas disponible pour une police spécifique, les typographes utilisent parfois des majuscules verticales de plus petite taille, mais cela ne produit pas la même qualité qu'une police en petites majuscules bien conçue. Les vraies petites majuscules ont des largeurs et des poids différents de ceux des lettres majuscules de la même police qui ont été réduites à la hauteur des petites majuscules conçues. Vous pouvez voir sur la figure ci-dessous que les traits dans les fausses majuscules sont beaucoup trop fins.

![Comparaison de petites capitalisations vraies et fausses](/tex/images/java/tutorial/latex-font-selection-2-5.png) 

### Poids et largeur

Les polices d'une certaine forme au sein d'une famille peuvent différer en *poids*. Cette caractéristique est liée à l'épaisseur des traits utilisés pour dessiner les formes individuelles. Certains fabricants de polices appellent les épaisseurs de police destinées à être utilisées pour le texte normal *book*, tandis que d'autres les appellent *medium*. Pour les traits fins, le nom *léger* est courant, tandis que les traits plus épais sont généralement appelés *gras*. Dans les grandes familles de polices, on retrouve parfois une gamme commençant par *ultra light*, passant par *extra light*, *light*, *semi light*, etc., et se terminant par *ultra bold* à l'autre extrémité. Mais souvent, seuls quelques poids sont disponibles dans certaines familles. La famille Computer Modern Roman, par exemple, n'a que des graisses moyennes et grasses.

La *largeur* de la police est un autre attribut important. Il fait référence au degré d'expansion ou de contraction par rapport à la largeur normale ou moyenne de la famille. Computer Modern Roman a des polices grasses en *largeur moyenne* et *largeur étendue*. Les polices condensées sont souvent utilisées dans les titres et les titres, où les polices de largeur moyenne, lorsqu'elles sont utilisées dans de grandes tailles, prendraient trop de place.

### Tailles de police

L'unité de mesure des tailles de police est le point d'imprimante (pt). Il y a 72,27 points dans un pouce. La taille de la police ne fait référence à aucune caractéristique particulière, mais c'est plutôt une valeur choisie par le concepteur de la police pour guider l'utilisateur. Par exemple, dans une police de 10 pts, les lettres de l’alphabet mesurent généralement moins de 10 pts de hauteur et seuls les caractères tels que les parenthèses ont approximativement cette hauteur.

L'apparence d'une police dépend de nombreux facteurs, tels que la hauteur des lettres minuscules (la *hauteur x*), la largeur du trait et la profondeur des descendeurs (la partie des lettres située en dessous de la ligne de base, comme dans le lettre 'q'). C’est pourquoi deux polices de même taille peuvent ne pas bien se mélanger.

Dans le monde LaTeX, les polices sont souvent disponibles dans des tailles de puissance 1,2, ce qui signifie qu'elles suivent une progression géométrique. Cet agencement facilite la production d'une copie originale agrandie qui peut ensuite être réduite photographiquement, augmentant ainsi efficacement la résolution de sortie finale. De nos jours, les polices sont généralement vectorisées et peuvent donc être mises à l'échelle à volonté. En conséquence, de nombreuses familles de polices commerciales sont proposées dans une seule taille de conception.

L’utilisation de polices mises à l’échelle au lieu de polices conçues pour une taille spécifique donne souvent des résultats moins satisfaisants. Cela est dû au fait que les polices ne s’adaptent pas de manière linéaire à l’œil humain. Vous pouvez voir la différence dans la figure ci-dessous :

![Une vraie police de 10 pts et une police agrandie de 5 pts](/tex/images/java/tutorial/latex-font-selection-2-6.png)
 
Les glyphes des polices artisanales de plus grande taille sont généralement plus étroits que les polices agrandies à partir d'une taille plus petite de la même famille. Il convient d'utiliser des polices conçues pour la taille souhaitée dans la mesure du possible, bien qu'il soit acceptable de redimensionner les polices dans une petite plage de tailles si nécessaire.

## 2.4. Encodages de polices

Comme nous l'avons mentionné en introduction, TeX fait référence aux glyphes d'une police en les adressant via des codes. Un tel mappage est appelé *codage de police*. Dans LaTeX, deux polices ayant le même encodage de police sont censées être interchangeables dans le sens où, avec la même entrée, elles produisent les « mêmes » glyphes sur la page imprimée.
En classant les polices selon leurs encodages de police, il est possible de modifier d'autres caractéristiques, telles que la famille de polices ou la série de polices, tout en garantissant que le résultat de la composition restera compréhensible.

À l'origine, les distributions TeX incluaient des polices qui ne contenaient que 128 glyphes par police. Par conséquent, ces polices n’incluent aucun caractère accentué en tant que glyphes individuels. Tous ces glyphes devaient être construits en utilisant la primitive `\accent` de TeX ou par des méthodes similaires. De ce fait, tout mot contenant des signes diacritiques ne peut pas être automatiquement coupé par LaTeX, et le crénage (correction de l'espacement entre certaines lettres dans la police) ne peut pas être automatiquement appliqué. L'encodage de ces polices est appelé « OT1 ». Bien qu'il reste l'encodage par défaut pour LaTeX, il n'est pas conseillé d'utiliser « OT1 » pour des langues autres que l'anglais.

La communauté des utilisateurs de TeX a défini un codage de 256 caractères appelé « T1 » qui permet à TeX de composer correctement dans plus de 30 langues basées sur l'alphabet latin. Par conséquent, l'utilisation de l'encodage `T1` est fortement recommandée puisque, de nos jours, presque toutes les familles de polices pouvant être utilisées avec LaTeX sont disponibles dans cet encodage. En fait, certains ne sont *uniquement* disponibles que dans l'encodage `T1`. Spécifier `\usepackage[T1]{fontenc}` après la commande `\documentclass` fait de `T1` l'encodage par défaut dans un document.