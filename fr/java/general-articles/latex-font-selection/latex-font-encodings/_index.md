---
translation: true
template: /templates/_template-java.md
linktitle: 1. Entrée et sortie
title: Encodages d'entrée et de sortie
weight: 10
url: /java/latex-font-encodings/
keywords: latex, polices latex, encodages de polices latex, nfss
description: Cet article explique brièvement les concepts d'encodages d'entrée et de sortie dans LaTeX et le nouveau système de sélection de polices (NFSS).
lastmod: "2024-09-27"
---

{{<section overview>}}

Si nous appuyons sur une touche d'un clavier, un code numérique sera généré représentant un certain caractère. Un codage d'entrée mappe un caractère à son code correspondant. Par exemple, sur un clavier allemand, les caractères accentués (tels que le caractère « tréma ») peuvent être mappés à différents codes sous différents systèmes d'exploitation.

Un document stocké dans un fichier informatique ne contient que des codes de caractères, mais les informations sur le codage d'entrée ne sont pas explicitement incluses. Par conséquent, si vous transférez un fichier vers un environnement différent, par exemple des États-Unis vers le Royaume-Uni, vous constaterez peut-être que les signes dollar dans votre document sont soudainement interprétés comme des symboles dièse lorsque vous affichez votre fichier avec un programme qui fait la mauvaise hypothèse sur le codage d’entrée.

Le package `inputenc`, développé par l'équipe du projet LaTeX, était destiné à résoudre les problèmes de codage d'entrée. Il permet aux utilisateurs de spécifier explicitement le codage d'entrée utilisé pour les documents ou parties de documents. Ce mécanisme permet de transférer en toute sécurité des documents d'une installation LaTeX à une autre, obtenant ainsi des résultats d'impression identiques.

Le package `inputenc` interprète les codes de caractères dans le fichier et les mappe à une *représentation LaTeX interne*, qui couvre de manière unique tous les caractères représentables dans LaTeX. Lors d'un traitement ultérieur, comme l'écriture dans un fichier auxiliaire, LaTeX utilise cette représentation interne, évitant ainsi toute mauvaise interprétation.

Cependant, tôt ou tard, LaTeX doit associer ces représentations de caractères internes à des *glyphes* (formes de caractères dans certaines polices), un autre mappage est donc nécessaire. Il y a au plus 256 glyphes dans n'importe quelle police TeX. Ces glyphes ne sont pas adressés par leur nom, mais par des nombres de 8 bits représentant les positions des glyphes dans la police. Cela signifie que nous devons cartographier un grand espace de dénomination unique en plusieurs petits espaces, et ces positions de glyphes peuvent varier considérablement, ce qui n'est pas surprenant.

Ainsi, même si nous avons conservé la signification du signe dollar du fichier externe vers les composants internes de LaTeX, nous pourrions toujours trouver des formes erronées sur le papier si nous sélectionnions une police à imprimer comportant un glyphe inattendu à la position que nous supposions réservée à un dollar. signe. L'une des tâches de **NFSS** (**New Font Selection Scheme** de LaTeX) est de s'assurer soit que toute représentation de caractères interne de LaTeX est correctement rendue, soit, si cela est impossible pour une raison quelconque, que l'utilisateur reçoive un message d'erreur approprié.

Si une police contient des caractères accentués sous forme de glyphes individuels, plutôt que uniquement des caractères de base plus des accents (à partir desquels TeX construit des caractères accentués en interne), alors l'utilisation de ces glyphes est préférable car ils ont généralement une meilleure apparence. Une autre raison (technique) d'utiliser ces glyphes composites est que la primitive `\accent` supprimera la césure.

Pour s'adapter à différents cas, une commande comme `\'e` (la représentation interne de LaTeX pour le caractère 'e-acute') doit parfois lancer des actions compliquées impliquant la primitive `\accent`, et parfois elle informe simplement le générateur de paragraphe qu'elle a besoin du glyphe d'un certain *emplacement* (position) dans la police actuelle.

Tout cela est réalisé grâce au concept d'*encodages de sortie*, qui sont des mappages des représentations de caractères internes de LaTeX vers des positions de glyphes appropriées ou vers des actions de création de glyphes, en fonction des glyphes réellement disponibles dans la police utilisée pour la composition.

Les articles suivants traitent de la version 2 de NFSS, qui est devenue partie intégrante du standard LaTeX en 1994.