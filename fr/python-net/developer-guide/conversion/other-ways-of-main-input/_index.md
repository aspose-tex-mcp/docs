---
translation: true
template: /templates/_template-python-net.md
title: Alternatives pour fournir le fichier d'entrée TeX | Python
linktitle: Autres façons de fournir le fichier d'entrée TeX principal
weight: 14
url: /python-net/other-ways-of-main-input/
description: La solution API Aspose.TeX pour Python inclut un constructeur qui accepte un flux comme premier argument, fournissant une fonctionnalité de conversion.
lastmod: "2024-09-27"
---

{{<section overview>}}

## Fournir le fichier d'entrée principal au moteur TeX à l'aide d'un flux

Jusqu'à présent, nous avons seulement appris comment fournir le [fichier d'entrée principal](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) au moteur TeX sous forme de nom de fichier, que ce soit sous sa forme complète ou sous une forme abrégée, avec ou sans extension. Cependant, il existe un [autre constructeur](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#io.RawIOBase-aspose.tex.presentation.Device-aspose.tex.TeXOptions) disponible dans la classe [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob) qui accepte un flux comme premier argument. Ceci est utile si, pour une raison quelconque, le fichier d'entrée principal ne se présente pas sous la forme d'un fichier sur le système de fichiers du disque. Voici un exemple de la façon dont cela peut être mis en œuvre :

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-InputStream.py" >}}

Notez que tous les fichiers de sortie seront nommés « textut ». En effet, le moteur n’a accès à aucun autre nom. `texput` est le nom de travail par défaut. Vous pouvez trouver des informations plus détaillées sur les noms de tâches [Sortie TeX](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) et [Comment définir le nom de la tâche](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name).

## Saisie du fichier d'entrée TeX principal via le terminal

Il y a [un constructeur supplémentaire](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#aspose.tex.presentation.Device-aspose.tex.TeXOptions) disponible dans la classe [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob) qui ne nous permet pas du tout de spécifier l'entrée. Vous vous demandez peut-être ce que traiterait un tel travail TeX. Dans ce cas, nous aurions besoin d’utiliser un terminal d’entrée. Le moteur TeX nous demandera de saisir le nom du fichier depuis le terminal.

Voici le code :

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

Dès qu'il sera exécuté, le moteur fera une pause et attendra que nous saisissions le nom du fichier (avec ou sans chemin, et avec ou sans extension) :

![Fenêtre du terminal](/tex/images/python-net/.png)

Et voici comment cela apparaîtrait sur le terminal de sortie (console) :

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