---
translation: true
template: /templates/_template-net.md
title: Autres moyens de fournir le fichier d'entrée TeX | .NET
linktitle: Autres façons de fournir le fichier d'entrée TeX principal
weight: 14
url: /net/other-ways-of-main-input/
description: De conversion de la solution API Aspose.TeX pour .NET a un constructeur qui accepte un flux comme premier argument.
lastmod: "2026-04-22"
---

{{<section overview>}}

## Fournir le fichier d'entrée principal au moteur TeX sous forme de flux

Jusqu'à présent, nous savions seulement comment transmettre le [fichier d'entrée principal](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) au moteur TeX sous forme de nom de fichier, qu'il soit entièrement spécifié ou sous forme abrégée, avec ou sans extension. Mais il existe un autre [constructeur](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) de la classe `TeXJob`, qui prend un flux comme premier argument. Ceci est pratique si, pour une raison quelconque, nous avons le fichier d'entrée principal sous une forme autre qu'un fichier sur le système de fichiers du disque. Voici comment cela peut être mis en œuvre :

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-StreamInput-LaTeX.cs" >}}

Notez que tous les fichiers de sortie porteront le nom *texput*. C'est parce que le moteur ne peut trouver aucun autre nom nulle part. *texput* est le nom du travail par défaut. [Ici](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) et [ici](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name) sont des détails sur les noms de tâches.

## Saisie du fichier d'entrée principal TeX depuis le terminal

Il existe encore un autre [constructeur](https://reference.aspose.com/tex/net/aspose.tex/texjob/texjob/) de la classe `TeXJob`, qui ne nous permet pas du tout de spécifier l'entrée. Alors, que va traiter un tel travail TeX, vous vous demandez peut-être ? Cette fois, nous aurons besoin d’un terminal d’entrée. Le moteur TeX nous demandera de saisir le nom du fichier depuis le terminal.

Voici le code :

{{< gist "aspose-com-gists" "0fbd18cd8c28d5ed12e19cd52634ebd4" "Example-MainInputTerminal.cs" >}}

Dès qu'il est lancé, le moteur bloque, attendant que nous saisissions le nom du fichier (avec ou sans chemin, avec ou sans extension) :


![Fenêtre du terminal](/tex/images/net/Conversion-MainInputTerminal.png)

Et voici à quoi cela ressemblerait sur le terminal de sortie qui est la console :

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode
**<path_to_the_file>/hello-world.ltx
(<path_to_the_file>/hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.xps (1 page).
Transcript written on hello-world.log.
```
