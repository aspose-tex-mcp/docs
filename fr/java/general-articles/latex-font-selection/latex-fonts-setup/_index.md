---
translation: true
template: /templates/_template-java.md
title: Comment configurer de nouvelles polices
linktitle: 6. Comment configurer de nouvelles polices
weight: 60
url: /java/latex-fonts-setup/
keywords: latex, polices latex, substitution de polices latex, configuration des polices latex
description: Cet article couvre la configuration de nouvelles polices à utiliser avec LaTeX et comprend également un exemple de définition de police.
lastmod: "2024-09-27"
---

{{<section overview>}}

Pour configurer de nouvelles polices à utiliser avec LaTeX, vous devez essentiellement remplir les tables de sélection de polices internes avec les informations nécessaires pour associer ultérieurement une demande de police dans un document au fichier externe `.tfm` contenant les informations sur les caractères utilisés par LaTeX. Par conséquent, les tables se chargent d'associer le fichier externe `cmdunh10.tfm` à la requête suivante :

```tex
\fontencoding{OT1}\fontfamily{cmdh}\fontseries{m}\fontshape{n}%
\fontsize{10}{12pt}\selectfont
```

Pour ajouter de nouvelles polices, vous devez inverser le processus. Pour chaque nouvelle police externe, vous devez répondre à cinq questions :

1. Quel est le codage de la police, c'est-à-dire quels caractères se trouvent à quelles positions ?
2. Quel est son nom de famille ?
3. Quelle est sa série (poids et largeur) ?
4. Quelle est sa forme ?
5. Quelle est sa taille ?


Les réponses à ces questions fourniront les informations nécessaires pour classer vos polices externes selon les conventions LaTeX. Dans les prochaines sections, nous verrons comment saisir de nouvelles polices dans les tableaux NFSS afin qu'elles puissent être utilisées dans le texte principal. Vous avez normalement besoin de ces informations si vous souhaitez utiliser de nouvelles polices, par exemple pour créer un fichier de package court pour accéder à une nouvelle famille de polices. Dans les sections suivantes, nous aborderons des concepts plus complexes qui sont importants si vous souhaitez utiliser, par exemple, des polices spéciales pour les mathématiques au lieu des polices standard.

## 6.1. La convention de dénomination des polices externes

Un schéma de dénomination de police standard de facto dans le monde TeX classe tous les noms de fichiers de polices en utilisant huit caractères alphanumériques, la casse n'étant pas significative. Cette limite de huit caractères garantit que les mêmes noms de fichiers peuvent être utilisés sur toutes les plates-formes informatiques. Le principe du schéma est décrit dans le tableau ci-dessous, où les parties entre parenthèses peuvent être omises si elles correspondent à un défaut. Par exemple, une taille de dessin n’est donnée que si la police n’est pas mise à l’échelle linéairement.

![La convention de dénomination des polices externes](/tex/images/java/tutorial/latex-font-selection-6-1.png)

Vous trouverez ci-dessous la classification des 35 polices PostScript « de base » selon l'interface des polices de LaTeX. Pour chaque police, le nom Adobe complet et le nom court du fichier correspondant (dans la classification en cours de discussion) sont indiqués. Pour « OT1 », « T1 » ou « TS1 », il faudrait ajouter respectivement « 7t », « 8t » ou « 8c » pour obtenir le nom complet du fichier. Par exemple, `putr8t` pour Utopia Regular en encodage `T1`.  Cela sera utile dans une discussion ultérieure.

![Classification des polices PostScript](/tex/images/java/tutorial/latex-font-selection-6-2.png)

La convention de dénomination couvre les noms TeX internes des polices (c'est-à-dire ceux utilisés dans les déclarations `\DeclareFontShape` comme décrit dans la section suivante), les noms des polices virtuelles et de leurs composants (par exemple, les réencodages particuliers des polices physiques) et les noms des polices physiques. polices. Dans le cas des polices PostScript, les noms de polices physiques sont souvent différents de ceux utilisés en interne par TeX.
Dans ce dernier cas, les noms de polices internes doivent être mappés aux polices externes correspondantes lorsque le résultat d'une exécution LaTeX est affiché ou imprimé. Par exemple, le pilote PostScript « dvips » utilise des fichiers de mappage (extension par défaut « .map ») qui contiennent des lignes telles que

```
putr8r Utopia-Regular "TeXBase1Encoding ReEncodeFont " <8r.enc <putr8a.pfb
```

lui indiquant que la police `putr8r` peut être obtenue à partir de la police externe `putr8a.pfb` en la réencodant via un vecteur d'encodage spécial (`8r.enc`). Cependant, vous ne trouverez aucune référence à ce `putr8r` dans le fichier `t1put.fd`, qui contient les déclarations `\DeclareFontShape` pour la famille Utopia dans l'encodage `T1`. La raison en est que « putr8t » est une police virtuelle (construite avec l'aide de l'utilitaire « fontinst ») qui fait référence à « putr8r ». Ce dernier lien ne se trouve que dans les sources des polices virtuelles.

## 6.2. Comment déclarer de nouvelles familles de polices et groupes de formes de police

Chaque combinaison famille/encodage doit être introduite dans LaTeX à l'aide de la commande `\DeclareFontFamily`, qui prend trois arguments. Les deux premiers sont le schéma de codage et le nom de famille. Le troisième est généralement vide, mais il peut contenir des options spéciales pour le chargement des polices et est expliqué plus en détail dans cet article. Donc, si vous souhaitez déclarer une nouvelle famille - par exemple, Computer Modern Dunhill avec l'ancien encodage TeX - vous écririez

```tex
\DeclareFontFamily{OT1}{cmdh}{}
```

Normalement, une famille de polices comporte de nombreuses polices individuelles. Pour réduire le nombre de déclarations, vous devez combiner des polices qui diffèrent uniquement par leur taille et les déclarer en groupe au lieu d'annoncer chaque membre de la famille individuellement.

Un tel groupe est entré dans les tables internes de LaTeX avec la commande `\DeclareFontShape`, qui prend six arguments. Les quatre premiers arguments sont le schéma de codage, le nom de famille, le nom de série et le nom de forme sous lequel vous souhaitez accéder à ces polices. Le cinquième argument est une liste de tailles et de noms de polices externes, donnés dans un format spécial abordé ci-dessous. Le sixième argument est généralement vide et son utilisation est expliquée plus loin dans cet article.

Par exemple, une entrée de table NFSS pour le support vertical Computer Modern Dunhill dans l'ancien schéma de codage TeX pourrait être saisie comme suit :

```tex
\DeclareFontShape{OT1}{cmdh}{m}{n}{ <10> cmdunh10 }{}
```

en supposant qu'une seule police externe de taille 10 pt est disponible. Si vous disposez également de cette police disponible en 12 pt (à partir de 10 pt), la déclaration serait

```tex
\DeclareFontShape{OT1}{cmdh}{m}{n}{ <10> <12>cmdunh10 }{}
```

Si le fichier externe est disponible dans toutes les tailles possibles, la déclaration devient très simple. C'est le cas des polices PostScript (contour) de type 1, ou lorsque le programme pilote est capable de générer des polices à la demande en appelant METAFONT.

Par exemple, le format Times Roman gras dans le schéma de codage LaTeX `T1` pourrait être introduit comme suit

```tex
\DeclareFontShape{T1}{ptm}{b}{n}{ <-> ptm8t }{}
```

Cet exemple déclare une plage de tailles avec deux extrémités ouvertes. En conséquence, le même fichier externe « ptmb8t.tfm » est utilisé pour toutes les tailles et est mis à l'échelle à la taille souhaitée. Si vous disposez de plusieurs fichiers `.tfm` pour une police - par exemple, `emtt10` pour les tailles de texte et `emtt12` pour les tailles d'affichage (European Modern Typewriter) - la déclaration peut être

```tex
\DeclareFontShape{T1}{emtt}{m}{n}{<-12> emtt10 <12-> emtt12}{}
```

Dans ce cas, le fichier « emtt10.tfm » serait utilisé pour les tailles inférieures à 12 pts, et « emtt12.tfm » pour toutes les tailles supérieures ou égales à 12 pts.

Les exemples ci-dessus démontrent que le cinquième argument de la commande `\DeclareFontShape` consiste en des spécifications de taille entourées de crochets angulaires entremêlées d'informations de chargement pour les tailles individuelles (par exemple, les noms de police). La partie à l'intérieur des crochets angulaires est appelée *informations sur la taille*, et la partie qui suit le crochet angulaire de fermeture est appelée *informations sur la police*.  Les informations sur la police sont en outre structurées en une *fonction de taille* (souvent vide) et ses arguments. Dans les arguments de `\DeclareFontShape`, les espaces sont ignorés pour rendre les entrées plus lisibles. Dans des circonstances inhabituelles, lorsqu'un espace réel doit être saisi, vous pouvez utiliser la commande `\space`.

### Tailles simples et gammes de tailles

Les informations sur les tailles peuvent être divisées en *tailles simples* et *gammes de tailles*. Une taille simple est donnée par un nombre unique (décimal), comme « <10> » ou « <17.28> », et peut avoir n'importe quelle valeur positive. Cependant, vous ne trouverez probablement pas de valeurs inférieures à 4 ou supérieures à 120 car le nombre représente une taille de police mesurée en points. Une plage de tailles est donnée par deux tailles simples séparées par un trait d'union, pour indiquer une plage de tailles de police partageant les mêmes informations de police. La limite inférieure est incluse dans la plage, tandis que la limite supérieure est exclue. Par exemple, « <5-10> » représente des tailles supérieures ou égales à 5 pts et inférieures à 10 pts. Il est possible d'omettre le numéro sur l'une ou l'autre taille du trait d'union dans une plage de tailles : `<->` représente toutes les tailles possibles, `<-10>` représente toutes les tailles inférieures à 10 pt et `<12->` représente toutes les tailles supérieures ou égales à 12pt.
Plusieurs tailles simples ont souvent les mêmes informations de police. Dans ce cas, un raccourci pratique consiste à omettre toutes les informations sauf la dernière :

```tex
\DeclareFontShape{OT1}{panr}{m}{n}{ <5> <6> <7> <8> <9> <10>
    <10.95> <12> <14.4> <17.28> <20.74> <24.88> pan10 }{}
```

Cela déclare la police Pandora medium Roman comme étant disponible en plusieurs tailles, toutes produites par mise à l'échelle à partir de la même taille de dessin.

### Fonctions de taille

Comme mentionné ci-dessus, les informations sur la police sont en outre structurées en une fonction de taille et son argument. Si un « * » apparaît dans la chaîne d'informations sur la police, tout ce qui se trouve à gauche forme le nom de la fonction et tout ce qui se trouve à droite est l'argument. S'il n'y a pas d'astérisque, comme dans tous les exemples jusqu'à présent, la chaîne entière est considérée comme l'argument et le nom de la fonction est *vide*.

Les fonctions de taille produisent la spécification nécessaire à LaTeX pour trouver la police externe et la charger à la taille souhaitée. Ce processus est basé sur la taille demandée par l'utilisateur et les informations contenues dans la commande `\DeclareFontShape`. Les fonctions de taille sont également chargées d'informer l'utilisateur des événements spéciaux. Par exemple, certaines fonctions diffèrent uniquement par le fait qu'elles émettent des avertissements. Cette capacité permet au responsable du système de configurer LaTeX de la manière la mieux adaptée à un site particulier.

Le nom d’une fonction de taille se compose de zéro ou plusieurs lettres. Certaines fonctions de taille peuvent prendre deux arguments : un facultatif et un obligatoire. Un paramètre facultatif doit être placé entre crochets. Par exemple, la spécification suivante sélectionnerait, pour toutes les tailles possibles, la fonction de taille `s` avec l'argument facultatif `0.9` et l'argument obligatoire `cmfbi10` :

```tex
<-> s * [0.9] cmfib8
```

Les spécifications de taille dans `\DeclareFontShape` sont inspectées dans l'ordre dans lequel elles sont données. Lorsqu'une information de taille correspond à la taille demandée, la fonction de taille correspondante est exécutée. Si ce processus génère une police valide, aucune autre entrée n'est inspectée. Sinon, la recherche continue avec l'entrée suivante. Les fonctions de taille standard sont répertoriées ci-dessous.

**La fonction "vide"** La fonction vide charge les informations de police exactement à la taille demandée s'il s'agit d'une taille simple. S'il existe une plage de tailles et que la taille demandée par l'utilisateur se situe dans cette plage, la police est chargée exactement à la taille de l'utilisateur.
Par exemple, si l'utilisateur a demandé « 14.4 », alors la spécification

```tex
<-> panr10
```

chargerait le fichier `panr10.tfm` à 14,4 pt. Toutes les valeurs du fichier `.tfm` sont mises à l'échelle de 1,44 car cette police a été conçue pour 10 pt.

Vous souhaiterez parfois charger une police d'une taille légèrement différente de celle demandée par l'utilisateur. Un tel ajustement peut être nécessaire lorsque les polices d'une famille semblent trop grandes par rapport aux polices d'autres familles utilisées dans le même document. À cette fin, la fonction de taille vide permet à un argument facultatif de spécifier un facteur d'échelle qui est multiplié par la taille demandée pour obtenir la taille réelle à charger.

Ainsi, 

```tex
<-> [0.95] phvr8t
```

chargerait toujours le fichier `phvr8t.tfm` (Helvetica dans l'encodage `T1`) à 95 % de la taille demandée. Si l'argument facultatif est utilisé, la fonction de taille vide émettra un avertissement pour informer l'utilisateur que la police n'est pas chargée à la taille prévue.

**La fonction "s"** La fonction `s` fait la même chose que la fonction vide, sauf qu'aucun message ne sera généré sur le terminal. Les messages seront toujours écrits dans le fichier de transcription, afin que vous puissiez savoir quelles polices ont été utilisées en cas de problème.

**La fonction "gen"** Les noms de polices externes sont souvent construits en ajoutant la taille de la police à une chaîne qui représente la police de caractères. Par exemple, « cmtt8 », « cmtt9 » et « cmtt10 » sont les noms externes des polices Computer Modern Typewriter à 8, 9 et 10 pts, respectivement. Avec les noms de polices organisés selon un tel schéma, vous pouvez utiliser la fonction « gen » pour raccourcir l'entrée. Cette fonction combine les informations sur la police et la taille demandée pour générer les noms de police externes. Ainsi, si vous écrivez

```tex
<8> <9> <10> gen * cmtt
```

ce serait un raccourci pour
```tex
<8> cmtt8 <9> cmtt9 <10> cmtt10
```

qui enregistre huit caractères dans les tables NFSS internes. Cette fonction combine littéralement les deux parties, vous ne devez donc pas l'utiliser avec des tailles décimales comme « 14,4 ». Vous devez également vous assurer que les chiffres du nom de la police externe représentent réellement la taille du design (par exemple, « cmr17 » est en fait Computer Modern Roman à 17,28 pt).

À tous autres égards, la fonction « gen » se comporte comme la fonction vide. Autrement dit, l'argument facultatif, s'il est spécifié, représente un facteur d'échelle et, s'il est utilisé, génère un message d'information.

**La fonction "sgen"** La fonction `sgen` est la version silencieuse de la fonction gen. Il écrit n'importe quel message uniquement dans le fichier de transcription.

**La fonction "genb"** Cette fonction de taille est similaire à gen, mais est destinée aux polices dans lesquelles la taille est codée dans le nom de police en centipoints, comme les polices EC. En conséquence, une ligne telle que 

```tex
<9> <10> <10.95> <12> genb * ecrm
```

agit comme un raccourci

```tex
<9> ecrm0900 <10> ecrm1000 <10.95> ecrm1095 <12> ecrm1200
```

Un argument facultatif, s’il est présent, aura le même effet qu’avec la fonction vide.

**La fonction "sgenb"** La fonction `sgenb` est la version silencieuse de la fonction `genb`. Il écrit n'importe quel message uniquement dans le fichier de transcription.

**La fonction "sub"** La fonction `sub` est utilisée pour remplacer un groupe de formes de police différent si aucune police externe n'existe pour le groupe de formes de police actuel. Dans ce cas, l’argument n’est pas un nom de police externe mais plutôt une combinaison différente de famille, de série et de forme séparées par des barres obliques. Par exemple, le Computer Modern Sans n'a pas de forme italique, seulement une forme inclinée. Par conséquent, il est raisonnable de déclarer la forme inclinée comme substitut à la forme italique :

```tex
\DeclareFontShape{OT1}{cmss}{m}{it}{ <-> sub * cmss/m/sl }{}
```

Sans cette déclaration, le mécanisme de substitution automatique de LaTeX remplacerait la forme par défaut, Computer Modern Sans vertical.

Il existe d'autres bonnes utilisations de la fonction `sub`. Regardez le code suivant :

```tex
\DeclareFontShape{OT1}{cmss}{m}{sl}{ <-8> sub * cmss/m/n
   <8> cmssi8 <9> cmssi9 <10><10.95> cmssi10 <12><14.4> cmssi12
   <17.28><20.74><24.88> cmssi17 }{}
```

Cette déclaration indique que pour les tailles inférieures à 8 pt, LaTeX doit rechercher dans la déclaration de forme de police « OT1/cmss/m/n ». De telles substitutions peuvent être enchaînées. Par exemple, il n’existe pas de police Computer Modern Sans inférieure à 8 pts, donc le groupe de formes de police substitué contiendra probablement une autre entrée de substitution. Cependant, l'utilisation de cette méthode présente l'avantage que lorsque vous obtenez une police supplémentaire, vous ne devez modifier qu'une seule déclaration de groupe de formes de police - les autres déclarations qui utilisent cette police en bénéficieront automatiquement.

**La fonction "ssub"** La fonction `ssub` a la même fonctionnalité que la fonction sub mais ne produit pas d'avertissements à l'écran (le premier 's' signifie "silencieux").

**La fonction "subf"** La fonction `subf` charge les polices de la même manière que la fonction vide mais produit un avertissement indiquant que cette opération a été effectuée en substitution car la forme de police demandée n'est pas disponible. Cette fonction peut être utilisée pour remplacer certaines polices externes sans qu'il soit nécessaire de déclarer un groupe de formes de police distinct pour elles, comme dans le cas de la fonction `sub`. Par exemple, 

```tex
\DeclareFontShape{OT1}{ptm}{bx}{n}{ <-> subf * ptmb7t }{}
```

avertirait l'utilisateur que la combinaison demandée n'est pas disponible et, par conséquent, que la police `ptmb7t` a été chargée à la place. Comme cela est moins informatif que l'utilisation de la fonction « sub », cette dernière doit être préférée.

**La fonction "ssubf"** La version silencieuse de `subf`, cette fonction écrit ses messages uniquement dans le fichier de transcription.

**La fonction "fixe"** Cette fonction ignore la taille demandée et charge à la place la police externe donnée en argument. S'il est présent, l'argument facultatif indique la taille (en points) à laquelle la police sera chargée. Ainsi, cette fonction vous permet de spécifier des plages de tailles pour lesquelles une police d'une taille fixe sera chargée.

**La fonction "sfixed"** Version silencieuse de `fixed`, cette fonction permet par exemple de charger la police contenant les grands symboles mathématiques, qui n'est souvent disponible qu'en une seule taille.

### Options de chargement des polices

Comme mentionné ci-dessus, chaque famille de polices doit être déclarée à l'aide de la commande `\DeclareFontFamily`. L'argument de cette commande, ainsi que le sixième argument de `\DeclareFontShape`, peuvent être utilisés pour spécifier des opérations spéciales qui sont effectuées lorsqu'une police est chargée. De cette façon, vous pouvez modifier les paramètres associés à une police dans son ensemble.

Outre les informations sur chaque caractère, TeX conserve pour chaque police externe un ensemble de dimensions globales et d'autres valeurs associées à la police. Par exemple, chaque police possède son propre « caractère de trait d'union », le caractère qui est inséré lorsque TeX coupe un mot. Un autre exemple est la largeur normale et l'extensibilité de l'espace vide entre les mots ; une valeur est conservée pour chaque police et modifiée à chaque fois que TeX passe à une nouvelle police. En modifiant ces valeurs au moment du chargement de la police, des effets spéciaux peuvent être obtenus.

Normalement, les changements s’appliquent à toute une famille ; par exemple, vous souhaiterez peut-être interdire la césure pour tous les mots composés dans la famille des machines à écrire. Dans ce cas, le troisième argument de `\DeclareFontFamily` doit être utilisé. Si les modifications doivent s'appliquer uniquement à un groupe de formes de police spécifique, vous devez utiliser le sixième argument de `\DeclareFontShape`. En d'autres termes, lorsqu'une police est chargée, NFSS applique d'abord l'argument de `\DeclareFontFamily` puis le sixième argument de `\DeclareFontShape`, afin de pouvoir remplacer les options de chargement spécifiées pour toute la famille si nécessaire.

Avec `\hyphenchar\font=<number>`, TeX spécifie le caractère utilisé pour la césure. Le `<numéro>` représente la position de ce caractère dans le schéma de codage. La valeur par défaut est la valeur de `\defaulthyphenchar`, qui est `45`, représentant la position du caractère '-' dans la plupart des schémas de codage. Si vous définissez ce nombre sur « -1 », la césure est supprimée. Ainsi, en déclarant

```tex
\DeclareFontFamily{0T1}{cmtt}{\hyphenchar\font=-1}
```

vous pouvez supprimer la césure pour toutes les polices de la famille `cmtt` avec le schéma de codage `OT1`. Les polices avec le codage « T1 » ont un trait d'union alternatif en position 127, afin que vous puissiez définir, par exemple,

```tex
\DeclareFontFamily{T1}{cmr}{\hyphenchar\font=127}
```

ce qui rend le trait d'union différent du tiret de mot composé saisi dans des mots comme « soi-disant ». TeX ne coupe pas les mots qui contiennent déjà des traits d'union explicites (sauf juste après le trait d'union), ce qui peut poser problème dans les langues dans lesquelles la longueur moyenne des mots est beaucoup plus grande qu'en anglais. Avec les paramètres ci-dessus, ce problème peut être résolu.

Chaque police TeX est associée à un ensemble de dimensions, qui sont modifiées par des affectations de la forme `\fontdimen<number>\font=<dimen>`, où `<number>` est le numéro de référence de la dimension et `<dimen> ` est la valeur à attribuer. Les valeurs par défaut sont récupérées du fichier `.tfm` lorsque la police est chargée. Chaque police a au moins sept dimensions de ce type :* `\fontdimen1` Spécifie l'inclinaison par point des caractères. Si la valeur est zéro, la police est droite.

* `\fontdimen2` Spécifie la largeur normale d'un espace utilisé entre les mots (espace inter-mots).

* `\fontdimen3` Spécifie l'extensibilité supplémentaire de l'espace inter-mots, qui est la quantité supplémentaire d'espace blanc que TeX est autorisé à ajouter à l'espace entre les mots pour produire des lignes justifiées dans un paragraphe. En cas d'urgence, TeX peut ajouter plus d'espace que cette valeur autorisée ; dans ce cas, une *case sous-pleine* sera signalée.

* `\fontdimen4` Spécifie la réduction autorisée de l'espace inter-mots, qui est la quantité d'espace que TeX est autorisé à soustraire de l'espace inter-mots normal (\fontdimen2) pour produire des lignes justifiées dans un paragraphe. TeX ne réduira jamais l'espace inter-mots à moins de ce minimum.

* `\fontdimen5` Spécifie la *hauteur x*. Il définit la dimension orientée police `1ex`.

* `\fontdimen6` Spécifié la largeur *quad*. Il définit la dimension orientée police `1em`.

* `\fontdimen7` Spécifie la quantité d'espace supplémentaire à ajouter après certains caractères de ponctuation de fin de phrase lorsque `\nonfrenchspacing` est en vigueur. Elle est toujours ignorée ou plutôt remplacée par la valeur `\xspaceskip` lorsque cette valeur est différente de zéro.

Lorsque vous modifiez l'espacement entre les mots associé à une police, vous ne pouvez pas utiliser de valeur absolue, car une telle valeur doit être utilisable pour toutes les tailles d'un même groupe de formes. Par conséquent, vous devez définir la valeur en utilisant un autre paramètre qui dépend de la police. On pourrait dire, par exemple,

```tex
\DeclareFontShape{0T1}{cmr}{m}{n}{...}
   {\fontdimen2\font=.7\fontdimen2\font}
```

Cette déclaration réduit l'espace inter-mots normal à 70 % de sa valeur d'origine. De même, l'extensibilité et la rétraction pourraient être modifiées.

Certaines polices des formules nécessitent plus de sept dimensions de police. À savoir, les polices de symboles appelées « symboles » et « largesymbols ». TeX ne pourra pas composer une formule si ces polices ont respectivement moins de 22 et 13 paramètres `\fontdimen`. Les valeurs de ces paramètres sont utilisées pour positionner les caractères dans une formule mathématique.

Il y a une optimisation malheureuse dans le système TeX : TeX ne charge chaque fichier `.tfm` qu'une seule fois pour une taille donnée. Par conséquent, il est impossible de définir un groupe de formes de police (avec la commande `\DeclareFontShape`) pour charger une police externe - par exemple, `cmtt10` - et d'utiliser une autre commande `\DeclareFontShape` pour charger la même police externe, cette fois modifier certains des paramètres `\fontdimen` ou un autre paramètre associé à la police. Une tentative en ce sens modifie les valeurs des deux groupes de formes de police.

Par exemple, supposons que vous essayiez de définir une forme de police avec un espacement serré en réduisant l'espace entre les mots :

```tex
\DeclareFontShape{T1}{ptm}{m}{n}{ <-> ptmr8t }{}
\DeclareFontShape{T1}{ptm}{c}{n}{ <-> ptmr8t }
                     {\fontdimen2\font=.7\fontdimen2\font}
```

Cette déclaration ne fonctionnera pas. L'espacement entre les mots pour la forme moyenne changera lorsque la forme serrée sera chargée selon les valeurs qui y sont spécifiées, et ce n'est pas ce à quoi on s'attend. La meilleure façon de gérer cette situation est de définir une police virtuelle contenant les mêmes caractères que la police d'origine mais qui diffère dans les paramètres des dimensions de la police. Une autre solution possible consiste à charger la police dans une taille légèrement différente, comme dans la déclaration suivante :

```tex
\DeclareFontShape{T1}{ptm}{c}{n}{ <-> [0.9999] ptmr8t }
                 {\fontdimen2\font=.7\fontdimen2\font}
```

Cette méthode en fait des polices différentes pour TeX avec des paramètres `\fontdimen` séparés. Alternativement, dans ce cas particulier, vous pouvez contrôler l'espace entre les mots en définissant `\spaceskip`, remplaçant ainsi les valeurs de police.

## 6.3. Comment modifier les familles de polices et les groupes de formes de police

Si une déclaration de forme de police non standard est nécessaire pour un document particulier, cette déclaration privée doit être placée dans un package ou dans le préambule du document. Cela écrasera toute déclaration existante pour la combinaison de formes de police. Cependant, il est important que l'utilisation de `\DeclareFontFamily` empêche un chargement ultérieur du fichier `.fd` correspondant (discuté plus loin dans cet article). De plus, cette nouvelle déclaration n'a aucun effet sur les polices déjà chargées.

## 6.4. Comment déclarer un nouveau schéma de codage de police

Les modifications de police qui impliquent des modifications du schéma de codage nécessitent certaines précautions. Dans l'encodage `T1`, par exemple, la plupart des lettres accentuées ont leurs propres glyphes, alors que dans l'encodage de texte TeX traditionnel (`OT1`), les lettres accentuées doivent être générées à partir de lettres et d'accents en utilisant la primitive `\accent`. Si les deux approches doivent être mélangées, peut-être parce qu'une police n'est disponible que dans l'un des encodages, la définition d'une commande telle que `\"` doit se comporter différemment selon l'encodage de police actuel.

C'est pourquoi chaque encodage de police doit être formellement introduit dans LaTeX avec une commande `\DeclareFontEcnoding`, qui prend trois arguments. Le premier argument est le nom de l'encodage, qui sera utilisé ultérieurement pour accéder à l'encodage avec la commande `\fontencoding`. La liste des [schémas de codage standard](/tex/{{lang.url-fragment}}java/latex-fonts-low-level/#choosing-the-encoding) et leurs noms internes sont fournis dans le tableau de la section 5.1.

Le deuxième argument contient tout code (tel que des définitions) à exécuter chaque fois que LaTeX passe d'un encodage à un autre à l'aide de la commande `\fontencoding`. Le dernier argument contient le code à utiliser à chaque accès à la police sous forme d'alphabet mathématique. Ainsi, ces trois arguments peuvent être utilisés pour redéfinir des commandes qui dépendent de la position des caractères dans l'encodage.

Le projet LaTeX3e se réserve l'utilisation d'encodages commençant par les lettres suivantes :

* `T` - encodages de texte standard avec 256 caractères.
* `TS` - symboles conçus pour étendre le codage `T` correspondant.
* `X` - encodages de texte qui ne sont pas conformes aux exigences strictes des encodages `T`.
* `M` - encodages mathématiques standard avec 256 caractères.
* `S` - autres codages de symboles.
* `A` - autres applications spéciales.
* `OT` - encodages de texte standard avec 128 caractères.
* `OM` - encodages mathématiques standard avec 128 caractères.

La lettre « O » souligne que les codages de 128 caractères sont anciens et *obsolètes*. Idéalement, ces encodages seront remplacés par des standards définis par le groupe d'utilisateurs TeX afin qu'à l'avenir un changement d'encodage ne soit nécessaire que si l'on passe d'une langue à une autre.

Lorsque vous déclarez vos propres encodages privés, vous devez choisir des noms commençant par « L » pour « local » ou « E » pour « expérimental ». Les encodages commençant par « U » sont destinés aux encodages « Inconnu » ou « Non classé », c'est-à-dire aux polices qui ne correspondent pas à un modèle d'encodage commun. La convention de dénomination introduite garantit que les fichiers utilisant des encodages officiels sont portables.

La commande `\DeclareFontEncoding` stocke le nom du codage nouvellement déclaré dans la commande `\LastDeclaredEncoding`. Ceci est parfois utile lorsque vous déclarez d'autres informations d'encodage associées et est, par exemple, utilisé dans les fichiers de déclaration d'encodage pour les langues cyrilliques.

De plus, comme nous l'avons mentionné dans la discussion sur la substitution de polices dans l'article précédent, les valeurs par défaut de la famille, de la série et de la forme peuvent devoir être différentes pour différents encodages. Pour un tel cas, NFSS fournit la commande `\DeclareFontSubstitution`, qui prend l'encodage comme premier argument. Les trois arguments suivants sont les valeurs par défaut (associées à cet encodage) pour la famille, la série et la forme à utiliser dans le processus de substitution automatique. Il est important que ces trois arguments forment une forme de police valide. En d'autres termes, une déclaration `\DeclareFontShape` existe pour eux. Sinon, un message d'erreur sera émis lorsque NFSS vérifiera ses tables internes dans `\begin{document}`.

## 6.5. Organisation des fichiers internes

Les familles de polices peuvent être déclarées lorsqu'un fichier de format est généré, déclarées dans le préambule du document ou chargées à la demande lorsqu'une commande de changement de police dans le document demande une combinaison qui n'a pas encore été utilisée. La première méthode conduit à consommer de la mémoire interne à chaque exécution de LaTeX, même si la police n'est pas utilisée. Les deux dernières options prennent un peu plus de temps lors du formatage du document car les définitions de police doivent être lues au moment de l'exécution. Néanmoins, ces dernières solutions sont préférables pour la plupart des groupes de formes car elles permettent de composer une grande variété de documents avec un seul format LaTeX.

Lors de la génération du fichier de format, LaTeX lit un fichier nommé « fonttext.ltx », qui contient l'ensemble standard de définitions de familles de polices et quelques autres déclarations liées aux polices de texte.

Toutes les autres définitions de familles de polices doivent être déclarées dans des fichiers externes chargés à la demande : soit des fichiers de package, soit des fichiers de définition de police (`.fd`).  Si les définitions de famille de polices sont placées dans un fichier de package, vous devez explicitement charger ce package après la commande `\documentclass`. Cependant, il existe une troisième possibilité : chaque fois que NFSS reçoit une demande pour une famille de polices « foo » dans un schéma d'encodage « BAR », et qu'il ne sait rien de cette combinaison, il essaiera de charger un fichier appelé « barfoo.fd ». Si ce fichier existe, il est censé contenir des définitions de groupes de formes de police pour la famille `foo` dans le schéma de codage `BAR` - c'est-à-dire des déclarations de la forme

```tex
\DeclareFontFamily{BAR}{foo}{...}
\DeclareFontShape{BAR}{foo}{...}{...}{...}{...}
...
\endinput
```

C'est ainsi qu'il devient possible de déclarer un grand nombre de familles de polices pour LaTeX sans remplir une mémoire précieuse avec des informations qui ne sont probablement presque jamais utilisées.

Chaque fichier `.fd` doit contenir toutes les définitions de polices pour une famille de polices dans un seul schéma de codage. Dans le fichier, il doit y avoir une ou plusieurs déclarations `\DeclareFontShape` et exactement une déclaration `\DeclareFontFamily`. Aucune autre définition ne doit apparaître dans le fichier, à l'exception peut-être d'une déclaration `\ProvidesFile` ou de certaines instructions `\typeout` informant l'utilisateur du chargement de la police. Au lieu de la commande `\typeout`, vous pouvez utiliser la commande TeX simple `\wlog`, qui écrit son argument uniquement dans le fichier de transcription. Les informations détaillées dans le fichier de transcription doivent être générées par tous les fichiers « .fd » utilisés en production, car l'examen de cette transcription aidera à repérer les erreurs en fournissant des informations sur les fichiers et leurs versions utilisées dans une tâche particulière. Si les commandes `\typeout` ou `\wlog` sont utilisées, il est important de se rappeler que les espaces et les lignes vides dans un fichier `.fd` sont ignorés. Par conséquent, il est nécessaire d'utiliser la commande `\space` dans l'argument de `\typeout` ou `\wlog` pour obtenir un espace vide sur l'écran et le fichier de transcription.

De nouveaux schémas de codage ne peuvent pas être introduits via le mécanisme `.fd`. NFSS rejettera toute demande de passage à un schéma de codage qui n'a pas été explicitement déclaré dans le format LaTeX (c'est-à-dire « fonttext.ltx »), dans un fichier de package ou dans le préambule du document.

## 6.6. Comment déclarer de nouvelles polices à utiliser en mathématiques

### Comment spécifier les tailles de police

Pour chaque taille de texte, NFSS maintient [trois tailles utilisées pour composer les formules mathématiques](/tex/{{lang.url-fragment}}java/latex-math-fractions-binomial-styles/) : la taille dans laquelle composer la plupart des symboles (sélectionnée par `\textstyle` ou `\displaystyle`) ; la taille des indices et exposants de premier ordre (`\scriptstyle`) ; et la taille des indices et exposants d'ordre supérieur (`\scriptscriptstyle`). Si vous passez à une nouvelle taille de texte pour laquelle les tailles mathématiques correspondantes ne sont pas encore connues, NFSS essaie de les calculer sous forme de fractions de la taille du texte. Si vous ne souhaitez pas que NFSS calcule ces tailles, vous pouvez spécifier vous-même les valeurs correctes via `\DeclareMathSizes`. Cette déclaration prend quatre arguments : la taille externe du texte et les trois tailles mathématiques pour cette taille de texte. Par exemple, la déclaration suivante définit les tailles mathématiques pour la taille 14 pt (titre) comme étant respectivement 14 pt, 10 pt et 7 pt :

```tex
\DeclareMathSizes{14}{14}{10}{7}
```

Une autre déclaration ci-dessous (pour les titres d'un niveau supérieur) informe le NFSS qu'aucune taille mathématique n'est nécessaire pour une taille de texte de 36 points. Cela peut aider à éviter le chargement inutile de nombreuses polices.

```tex
\DeclareMathSizes{36}{}{}{}
```

### Comment ajouter de nouveaux symboles

Nous avons déjà expliqué comment utiliser les [commandes de l'alphabet mathématique](/tex/{{lang.url-fragment}}java/latex-math-fonts/#81-math-alphabet-identifiers) pour produire des lettres avec des formes spéciales dans une formule. Ici, nous allons montrer comment ajouter des polices contenant des symboles spéciaux, appelés *polices de symboles*, et comment rendre ces symboles accessibles dans les formules.

L'ajout de nouvelles polices de symboles est similaire à la déclaration d'un nouvel identifiant d'alphabet mathématique : `\DeclareSymbolFont` définit les valeurs par défaut pour toutes les versions mathématiques, `\SetSymbolFont` remplace les valeurs par défaut pour une version particulière.

Les polices de symboles mathématiques sont accessibles via un nom symbolique. Par exemple, si vous souhaitez installer la police AMS `msbm10` (voir le tableau des glyphes ci-dessous), vous devez d'abord faire connaître la police à NFSS à l'aide des déclarations décrites dans les sections précédentes.

![graphique de glyphes msbm10](/tex/images/java/tutorial/latex-font-selection-6-3.png)

Ces instructions ressembleraient à

```tex
\DeclareFontFamily{U}{msb}{}
\DeclareFontShape{U}{msb}{m}{n}{ <5> <6> <7> <8> <9> gen * msbm
        <10> <10.95> <12> <14.4> <17.28> <20.74> <24.88> msbm10}{}
```

et sont généralement placés dans un fichier `.fd`. Ensuite, vous devez déclarer cette police de symbole pour toutes les versions mathématiques par la commande suivante :

```tex
\DeclareSymbolFont{AMSb}{U}{msb}{m}{n}
```

Il rend le groupe de formes de police « U/msb/m/n » disponible en tant que police de symboles sous le nom « AMSb ». S'il y avait une série en gras dans cette famille de polices (en fait, il n'y en a pas), vous pourriez par la suite modifier la configuration de la version mathématique en gras en disant

```tex
\SetSymbolFont{AMSb}{bold}{U}{msb}{b}{n}
```

Après avoir pris soin des déclarations de police, vous pouvez utiliser cette police de symboles en mode mathématique. Mais comment dire à NFSS que, par exemple, la commande `\lessdot` en mode mathématique doit produire le symbole correspondant dans la sortie ? Pour ce faire, vous devez introduire vos propres noms de symboles dans NFSS en utilisant `\DeclareMathSymbol` :

```tex
\DeclareMathSymbol{cmd}{type}{symbol-font}{slot}
```

Le premier argument est le nom de la commande que vous choisissez. Le deuxième argument est l'une des commandes présentées dans le tableau ci-dessous et détermine la nature du symbole, qui, à son tour, détermine la quantité d'espace que LaTeX met autour du symbole lorsqu'il apparaît dans une formule.

![Types d'objets mathématiques](/tex/images/java/tutorial/latex-font-selection-6-4.png)

D'ailleurs, à l'exception de `\mathalpha`, ces commandes peuvent être utilisées dans des formules mathématiques comme des fonctions avec un seul argument, auquel cas elles espacent leur argument (éventuellement complexe) comme s'il était du type correspondant.

Le troisième argument identifie la police du symbole à partir de laquelle le symbole doit être récupéré, c'est-à-dire le nom symbolique défini par la commande `\DeclareSymbolFont`. Le quatrième argument donne la position du symbole dans l'encodage de la police, sous forme décimale, octale ou hexadécimale. Vous pouvez facilement connaître les positions de tous les glyphes dans cette police à partir du tableau des glyphes ci-dessus. Par exemple, `\lessdot` peut être déclaré comme

```tex
\DeclareMathSymbol{\lessdot}{\mathbin}{AMSb}{"6c}
```

Au lieu d'un nom de commande, vous pouvez utiliser un seul caractère comme premier argument. Par exemple, le package `eulervm` contient plusieurs déclarations de la forme pour spécifier où récupérer les chiffres.

```tex
\DeclareMathSymbol{0}{\mathalpha}{letters}{"30}
```

La commande `\DeclareMathSymbol` spécifie une position dans une police de symbole. Par conséquent, il est important que toutes les polices externes associées à cette police de symboles via les commandes `\DeclareSymbolFont` et `\SetSymbolFont` aient le même caractère à cette position. Le moyen le plus simple de s'en assurer est d'utiliser uniquement des polices avec le même encodage (sauf s'il s'agit de l'encodage « U », ou inconnu, car deux polices dans cet encodage ne sont pas tenues de contenir les mêmes caractères).

Dans le tableau de glyphes ci-dessus, vous pouvez également trouver des lettres « tableau gras » (ABC... à partir de la position « 101 »). Si vous souhaitez utiliser ces lettres comme alphabet mathématique, vous pouvez les définir en utilisant `\DeclareMathAlphabet`. Cependant, si cette police de symboles est déjà chargée, il est préférable d'utiliser un raccourci pour accéder aux symboles individuels :

```tex
\DeclareSymbolFontAlphabet{\mathbb}{AMSb}
```

Autrement dit, vous fournissez le nom de votre identifiant d'alphabet mathématique et le nom symbolique de la police de symbole précédemment déclarée.
Une raison importante pour ne pas charger inutilement les polices deux fois est qu'il existe une limite supérieure de 16 polices mathématiques pouvant être actives à tout moment dans TeX. Dans le calcul de cette limite, chaque police de symbole compte ; les alphabets mathématiques ne comptent que s'ils sont réellement utilisés dans le document, et ils comptent localement dans chaque version mathématique. Par conséquent, si huit polices de symboles sont déclarées, vous pouvez utiliser au maximum huit identifiants d’alphabet mathématique (éventuellement différents) dans chaque version.

En bref : pour introduire de nouvelles polices de symboles, vous devez émettre un petit nombre de déclarations `\DeclareSymbolFont` et `\SetSymbolFont` et un nombre potentiellement grand de déclarations `\DeclareMathSymbol`. Par conséquent, il est préférable d’ajouter de telles polices dans un fichier de package.

### Comment introduire de nouvelles versions mathématiques

Nous avons déjà [mentionné](/tex/{{lang.url-fragment}}java/latex-math-fonts/#83-math-formula-versions) que la configuration standard déclare automatiquement deux versions mathématiques : normale et grasse. Pour introduire des versions supplémentaires, vous pouvez utiliser la déclaration `\DeclareMathVersion`, qui prend un argument : le nom de la nouvelle version mathématique. Toutes les polices de symboles et tous les alphabets mathématiques déclarés précédemment sont automatiquement disponibles dans cette version mathématique ; les polices par défaut leur sont attribuées - c'est-à-dire les polices que vous avez spécifiées avec `\DeclareMathAlphabet` ou `\DeclareSymbolFont`.

Vous pouvez ensuite modifier la configuration de votre nouvelle version en émettant les commandes `\SetMathAlphabet` et `\SetSymbolFont` appropriées pour la version mathématique en gras, comme indiqué plus haut dans cette section et dans l'article sur les [polices en mathématiques](/tex/{{lang.url-fragment}}java/latex-math-fonts/) . Encore une fois, l'introduction d'une nouvelle version mathématique se fait normalement dans un fichier de package.


### Comment modifier la configuration de la police des symboles

Nous avons vu comment ajouter de nouvelles polices de symboles pour accéder à davantage de symboles. Les mêmes commandes peuvent être utilisées pour modifier une configuration existante. Cette fonctionnalité peut être intéressante si vous décidez d'utiliser des polices spéciales dans certaines ou toutes les versions mathématiques.

Vous trouverez ci-dessous les paramètres LaTeX par défaut :

```tex
\DeclareMathVersion{normal} \DeclareMathVersion{bold}
\DeclareSymbolFont{operators} {OT1}{cmr}{m} {n}
\DeclareSymbolFont{letters} {OML}{cmm}{m}{it}
\DeclareSymbolFont{symbols} {OMS}{cmsy}{m}{n}
\DeclareSymbolFont{largesymbols} {OMX}{cmex}{m}{n}

% Special bold fonts only for these:
\SetSymbolFont {operators}{bold}{OT1}{cmr}{bx}{n}
\SetSymbolFont {letters} {bold}{OML}{cmm}{b}{it}
```

Dans la configuration standard, les chiffres et le texte produits par des opérateurs tels que `\log` et `\max` sont extraits de la police de symboles appelée `operators`. Pour modifier cela afin que ces éléments se fondent bien avec la police de texte principale - par exemple, Computer Modern Sans plutôt que Computer Modern Roman - vous pouvez exécuter les commandes suivantes :

```tex
\SetSymbolFont{operators}{normal}{0T1}{cmss}{m} {n}
\SetSymbolFont{operators}{bold} {0T1}{cmss}{bx}{n}
```

Les polices de symboles portant les noms « symboles » et « largesymbols » jouent un rôle unique dans TeX. C'est pourquoi ils nécessitent un nombre spécial de paramètres `\fontdimen` qui leur sont associés. Par conséquent, seules des polices spécialement préparées peuvent être utilisées comme ces deux polices de symboles. En principe, on peut ajouter de tels paramètres à n'importe quelle police au moment du chargement en utilisant le troisième paramètre de `\DeclareFontFamily` ou le sixième paramètre de `\DeclareFontShape`.

## 6.7. Comment définir votre propre fichier `.fd` (exemple)

Si vous souhaitez configurer des polices (PostScript) et créer le fichier « .fd » requis, vous devez suivre la procédure décrite plus haut dans cet article. Si « fontinst » est utilisé pour générer les fichiers de métriques de police requis, alors les fichiers « .fd » correspondants sont également automatiquement générés. Cependant, il est facile d'écrire manuellement un fichier « .fd » pour une seule famille de polices, à condition que vous sachiez quel encodage de police est utilisé. A titre d'exemple, étudions le fichier de déclaration `t1bch.fd` pour *Bitstream Charter* dans l'encodage `T1` :

```tex
\ProvidesFile{t1bch.fd}[2001/06/04 font definitions for T1/bch.]
% Primary declarations
\DeclareFontFamily{T1}{bch}{}
\DeclareFontShape{T1}{bch}{m}{n}{<-> bchr8t}{}
\DeclareFontShape{T1}{bch}{m}{sc}{<-> bchrc8t}{}
\DeclareFontShape{T1}{bch}{m}{sl}{<-> bchro8t}{}
\DeclareFontShape{T1}{bch}{m}{it}{<-> bchri8t}{}
\DeclareFontShape{T1}{bch}{b}{n}{<-> bchb8t}{}
\DeclareFontShape{T1}{bch}{b}{sc}{<-> bchbc8t}{}
\DeclareFontShape{T1}{bch}{b}{sl}{<-> bchbo8t}{}
\DeclareFontShape{T1}{bch}{b}{it}{<-> bchbi8t}{}
% Substitutions
\DeclareFontShape{T1}{bch}{bx}{n}{<->ssub * bch/b/n}{}
\DeclareFontShape{T1}{bch}{bx}{sc}{<->ssub * bch/b/sc}{}
\DeclareFontShape{T1}{bch}{bx}{sl}{<->ssub * bch/b/sl}{}
\DeclareFontShape{T1}{bch}{bx}{it}{<->ssub * bch/b/it}{}
\endinput
```

La première ligne est une *ligne d'identification*. Suit ensuite la déclaration de la famille de polices et de l'encodage (`bch` et `T1`) à l'aide de `\DeclareFontFamily`. L'argument de cette commande doit correspondre au nom du fichier `.fd`, sauf que l'encodage du nom du fichier est en minuscules. Ensuite, chaque combinaison de série et de forme est mappée au nom d'un fichier « .tfm ». Ces polices seront mises à l'échelle à n'importe quelle taille souhaitée (notez `<->`). La deuxième partie du fichier établit des substitutions pour les combinaisons pour lesquelles aucune police n'est disponible (c'est-à-dire en remplaçant la série étendue en gras par la série en gras).
En supposant que vous disposez des polices *Charter* supplémentaires (Black et BlackItalic), vous souhaiterez peut-être alors ajouter les définitions correspondantes au fichier `.fd`. Vous devrez bien entendu d’abord fournir les polices virtuelles appropriées pour émuler le jeu de caractères « T1 ». Heureusement, de nombreuses polices peuvent être téléchargées depuis Internet.

Une autre raison possible de créer vos propres fichiers « .fd » pourrait provenir de la nécessité de combiner des polices de différentes familles et de les introduire dans LaTeX en tant que nouvelle famille de polices unique. Par exemple, il existe la famille de polices *Aldus* conçue pour accompagner la police *Palatino* (qui a été conçue à l'origine comme police d'affichage). Comme Aldus n’a pas de série audacieuse, Palatino est un choix naturel à utiliser comme substitut audacieux. Dans l'exemple ci-dessous, nous combinons Aldus dans sa série moyenne avec Palatino bold, appelant la famille de polices composites « zasj ». Seul un fragment d'un fichier `.fd` complet est présenté, ce qui suffit à illustrer l'idée.

```tex
\ProvidesFile{t1zasj.fd}
   [2003/10/12 font definitions for T1 Aldus/Palatino mix.]
\DeclareFontFamily{T1}{zasj}{}
% Medium series
\DeclareFontShape{T1}{zasj}{m}{n} {<->pasr9d}{}
\DeclareFontShape{T1}{zasj}{m}{sc}{<->pasrc9d}{}
\DeclareFontShape{T1}{zasj}{m}{it}{<->pasri9d}{}
\DeclareFontShape{T1}{zasj}{m}{sl}{<->ssub * pasj/m/it}{}
% Bold series
\DeclareFontShape{T1}{zasj}{b}{n}{<-> pplb8t}{}
\DeclareFontShape{T1}{zasj}{b}{sc}{<->pplbc8t}{}
\DeclareFontShape{T1}{zasj}{b}{sl}{<->pplbo8t}{}
\DeclareFontShape{T1}{zasj}{b}{it}{<->pplbi8t}{}
```

Pour accéder à cette "pseudo-famille", il faut sélectionner `zasj` dans l'encodage `T1`. Nous devons également nous assurer que `\textbf` passe en gras, et non en gras étendu, puisque notre fichier `.fd` ne fournit aucune substitution. Tout cela peut être automatiquement fourni par un petit package comme celui-ci :

```tex
\ProvidesPackage{fontmix}[2003/10/12 T1 Aldus/Palatino mix.]
\RequirePackage[T1]{fontenc}
\renewcommand\rmdefault{zasj} \renewcommand\bfdefault{b}
```

Ainsi, en chargeant le package `fontmix`, nous obtenons Aldus et Palatino Bold pour les titres. Un tel mélange de polices n'améliore pas souvent votre texte, c'est pourquoi cet exemple ne suggère pas de créer des combinaisons aléatoires.

## 6.8. L'ordre des déclarations

Le NFSS vous demande de fournir toutes les déclarations dans un ordre précis, afin de pouvoir vérifier si vous avez renseigné toutes les informations nécessaires. Si vous déclarez des objets dans le mauvais ordre, il se plaindra. Voici les dépendances que vous devez honorer :

* `\DeclareFontFamily` vérifie que le schéma de codage a été précédemment déclaré avec `\DeclareFontEncoding`.
* `\DeclareFontShape` vérifie que la famille de polices a été déclarée disponible dans l'encodage demandé (`\DeclareFontFamily`).
* `\DeclareSymbolFont` garantit que le schéma de codage est valide.
* `\SetSymbolFont` garantit en outre que la version mathématique demandée a été déclarée (`\DeclareMathVersion`) et que la police de symboles demandée a été déclarée (`\DeclareSymbolFont`).
* `\DeclareSymbolFontAlphabet` vérifie que le nom de commande pour l'identifiant de l'alphabet peut être utilisé et que la police du symbole a été déclarée.
* `\DeclareMathAlphabet` vérifie que le nom de commande choisi peut être utilisé et que le schéma d'encodage a été déclaré.
* `\SetMathAlphabet` vérifie que l'identifiant de l'alphabet a été précédemment déclaré avec `\DeclareMathAlphabet` ou `\DeclareSymbolFontAlphabet` et que la version mathématique et le schéma d'encodage sont connus.
* `\DeclareMathSymbol` garantit que le nom de la commande peut être utilisé (c'est-à-dire qu'il n'est pas défini ou a été précédemment déclaré comme étant un symbole mathématique) et que la police du symbole a été précédemment déclarée.
* Lorsque la commande `\begin{document}` est atteinte, NFSS effectue des vérifications supplémentaires. Par exemple, il vérifie que les valeurs de substitution par défaut pour chaque schéma de codage pointent vers des déclarations de groupe de formes de police connues.

