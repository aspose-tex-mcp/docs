---
translation: true
template: /templates/_template-net.md
title: Entrée/sortie TeX 
linktitle: E/S TeX
weight: 12
url: /net/tex-io/
description: Principes fondamentaux du travail avec TeX comme format de sortie ou d'entrée dans. Le travail TeX s'exécute sur un fichier spécifié spécifié.
lastmod: 2026-10-20
---

{{<section overview>}}

## Fichier TeX {#tex-file}

Techniquement, n'importe quel fichier peut être un fichier TeX. Il n'est même pas nécessaire d'avoir l'extension *.tex*. Un moteur TeX lit l'entrée octet par octet en essayant de reconnaître les commandes qu'il connaît (c'est-à-dire celles qui sont dans son état interne). Il signale simplement les erreurs concernant les commandes non reconnues et/ou demande des corrections sur le terminal (s'il fonctionne en [mode interactif](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes)). Mais si vous vous attendez à voir quelque chose comme un document joliment composé, l'entrée doit suivre la syntaxe TeX et, idéalement, contenir uniquement les commandes connues du moteur.

## Entrée TeX {#tex-input}

Un travail TeX s'exécute sur un fichier TeX explicitement spécifié. Nous incluons donc ce fichier dans l'entrée d'un certain travail TeX. De plus, TeX dispose de quatre primitives liées à l'entrée auxiliaire :

* `\input<file name>` nécessite un nom de fichier et commence le traitement de ce fichier dès que le traitement du fichier contenant atteint la commande `\input`. Une fois la fin du fichier auxiliaire atteinte, le traitement revient au fichier contenant la commande `\input`.
* `\openin<4-bit-number>=<file name>` nécessite également un nom de fichier, mais il ouvre simplement un fichier et le mappe à un nombre de 0 à 15.
* `\read<numéro> vers <séquence de contrôle>` nécessite le numéro auquel un fichier est mappé et en lit une ligne à la fois afin que `<séquence de contrôle>` corresponde à la liste des jetons lus.
* `\closein<4-bit-number>` ferme le fichier mappé au numéro.

Les fichiers dont les noms sont passés aux commandes `\input` et `\openin` sont également inclus dans l'entrée TeX, et nous les appellerons fichiers *entrée auxiliaire* ou *dépendances*, tandis que le fichier spécifié pour le travail que nous appellerons le fichier *entrée principale*.

Les quatre commandes peuvent apparaître soit dans le fichier d'entrée principal, soit dans un fichier d'entrée auxiliaire. Mais méfiez-vous des dépendances circulaires.

Lors de l'exécution en [mode interactif](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), en cas d'erreur, le moteur TeX demande une correction sur le terminal. À ce stade, vous souhaiterez peut-être remplacer la commande erronée par une nouvelle. Et ce sera une autre et dernière façon de fournir une entrée à TeX que nous appellerons l'*entrée terminal*.

## Sortie TeX {#tex-output}

Comme nous l'avons mentionné [ci-dessus](/tex/{{lang.url-fragment}}net/tex-io/#tex-input), un travail TeX s'exécute sur un fichier explicitement spécifié. Le fichier ne peut contenir aucune donnée à composer. Il ne peut y avoir que des séquences de contrôle ne produisant aucun caractère à saisir. Mais normalement, il contiendra de telles données, de sorte que nous obtiendrons un fichier au format cible qui devrait contenir notre texte composé (ou tout ce qui est autorisé par le moteur et le format, s'ils sont étendus pour s'adapter aux fonctionnalités supplémentaires d'un certain format cible) . Le fichier aura le même nom que le fichier spécifié en entrée. Nous appellerons ce fichier le fichier *sortie principale*. Comme nous l'avons mentionné [ci-dessus](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex), pour le TeX original, ce sera un fichier au format DVI. Nous appellerons le nom des fichiers d'entrée et de sortie sans extension le *nom du travail*.

De plus, TeX dispose de trois primitives liées à la sortie auxiliaire :

* `\openout<4-bit-number>=<file name>` nécessite un nom de fichier, ouvre un fichier et le mappe à un nombre de 0 à 15.
* `\write<number>{token list}` nécessite le numéro auquel un fichier est mappé et écrit la `token list` dans le fichier.
* `\closeout<4-bit-number>` ferme le fichier mappé au numéro.

Les fichiers dont les noms sont passés aux commandes `\openout` sont également inclus dans la sortie TeX, et nous les appellerons fichiers *sortie auxiliaire*.

Au fur et à mesure que le moteur TeX exécute l'entrée, il peut générer des informations de débogage dans le fichier *log* ou *trascript*. Nous inclurons ce fichier dans la sortie TeX.
Simultanément à l'écriture dans le fichier journal, le moteur TeX peut fournir des informations moins détaillées au terminal. Et c'est la dernière façon dont le moteur TeX écrit la sortie que nous appellerons la *sortie du terminal*.

## Modes d'interaction TeX {#tex-interaction-modes}

Une tâche TeX peut s'exécuter dans l'un des quatre modes d'interaction à tout moment. Ces modes sont commutés par les primitives TeX suivantes :

* `\batchmode`. Le moteur omet tous les arrêts et omet la sortie du terminal, et ne nécessite donc pas le terminal pour l'entrée ou la sortie.
* `\mode nonstop`. Le moteur omet tous les arrêts et ne nécessite donc le terminal que pour la sortie.
* `\mode de défilement`. Le moteur omet les arrêts d’erreur et nécessite le terminal à la fois pour l’entrée et la sortie.
* `\errorstopmode`. Le moteur s'arrête à chaque occasion d'interagir.

Aspose.TeX nous permet de spécifier le mode d'interaction comme option de travail TeX lors de la création de son objet. Ce mode sera défini dans l'état interne du moteur immédiatement après le chargement du format TeX (si un format est censé être chargé), et passera à un autre mode dès que le moteur rencontrera l'une des quatre commandes. La valeur par défaut de cette option conservera le mode d'interaction défini par le format TeX. Lorsqu'aucun format n'est chargé, le mode d'interaction est le même que celui défini par la commande `\errorstopmode`.

## Le rôle de l'abstraction par interfaces (`IInputWorkingDirectory` et `IOutputWorkingDirectory`)

Les moteurs TeX traditionnels sont intrinsèquement étroitement liés au système de fichiers du système d'exploitation local ; ils traitent les fichiers comme des chemins absolus ou relatifs sur le disque. Aspose.TeX s'affranchit de cette contrainte héritée du passé en introduisant une couche d'abstraction robuste, articulée autour de deux interfaces principales : `IInputWorkingDirectory` et `IOutputWorkingDirectory`. Ce découplage vous permet de :

- Traiter des documents entièrement en mémoire, en utilisant un stockage basé sur des flux (streams).
- Gérer directement des archives groupées en lisant des flux ZIP, sans avoir à les extraire préalablement sur le disque.
- Garantir la sécurité des threads (thread safety) dans les applications serveur multi-utilisateurs (multi-tenant), en isolant chaque tâche de composition typographique dans sa propre instance de répertoire de travail virtuel.

### Pourquoi l'abstraction par interfaces est cruciale pour les développeurs

Dans les applications d'entreprise modernes — telles que les microservices dans le cloud ou les files d'attente de tâches en arrière-plan — le recours aux chemins d'accès sur disque physique entraîne des goulots d'étranglement majeurs :

- Plusieurs threads lisant ou écrivant dans le même répertoire physique risquent d'entrer en conflit ou d'écraser mutuellement leurs fichiers temporaires (comme les fichiers `.aux`, `.log` ou les fichiers de sortie).
- Écrire des ressources intermédiaires ou des données dynamiques issues d'une base de données sur le disque, uniquement pour qu'un moteur de composition typographique puisse les lire, nuit aux performances.
- Les environnements cloud (comme les conteneurs Docker ou les fonctions « serverless ») disposent souvent de systèmes de fichiers en lecture seule ou d'un accès au stockage restreint.

En faisant abstraction des entrées et des sorties via des interfaces, Aspose.TeX permet aux développeurs de rediriger les opérations sur les fichiers vers des flux en mémoire, des archives ZIP, des bases de données ou des systèmes de fichiers virtuels personnalisés, sans aucune modification de la logique fondamentale de composition typographique.