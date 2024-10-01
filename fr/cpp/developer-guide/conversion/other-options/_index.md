---
translation: true
template: /templates/_template-cpp.md
title: Autres options de gestion de TeX | C++
linktitle: Autres options
weight: 17
url: /cpp/other-options/
description: La fonctionnalité de conversion de la solution API Aspose.TeX pour C++ permet de définir le mode d'interaction initial dans lequel le moteur démarre. Voici quelques exemples de code.
lastmod: "2024-09-27"
---

{{<section overview>}}

## Comment définir le mode d'interaction

Comme nous l'avons mentionné [ici](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX for C++** nous permet de définir le mode d'interaction initial dans lequel le moteur démarre. Voici comment nous procédons :

```C++
// Create conversion options instance.
...
// Set the interaction mode.
options->set_Interaction(Interaction::NonstopMode);
```

## Comment définir le nom du travail

Lorsque nous transmettons le fichier d'entrée principal comme nom de fichier, nous obtenons des fichiers de sortie portant le même nom, mais avec d'autres extensions. Le moteur TeX appelle le nom du fichier d'entrée *nom du travail* et l'utilise pour les fichiers de sortie, sauf dans les cas où des fichiers auxiliaires avec d'autres noms explicitement spécifiés sont écrits. Lorsque nous transmettons le fichier d'entrée principal en tant que [stream](/tex/{{lang.url-fragment}}cpp/other-ways-of-main-input/#providing-the-main-input-file-as-a-stream), le moteur TeX utilise le nom de travail par défaut, qui est *texput*.
Dans les deux cas, nous pouvons remplacer le nom du travail en attribuant l'option de conversion appropriée.

```C++
// Create conversion options instance.
...
// Set the job name.
options->set_JobName(u"my-job-name");
```
## Comment répéter le travail

Comme nous l'avons mentionné [ci-dessus](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) concernant les étiquettes et les références, il existe des cas où nous souhaiterions exécuter deux fois le même travail. Voici comment procéder :

```C++
// Create conversion options instance.
...
// Set the job name.
options->set_Repeat(true);
```