---
translation: true
template: /templates/_template-java.md
title: Autres moyens de fournir le fichier d'entrée TeX | Java
linktitle: Autres façons de fournir le fichier d'entrée TeX principal
weight: 14
url: /java/other-ways-of-main-input/
description: De conversion de la solution API Aspose.TeX pour Java a un constructeur qui accepte un flux comme premier argument.
lastmod: "2026-04-21"
---

{{<section overview>}}

## Fournir le fichier d'entrée principal au moteur TeX sous forme de flux

Jusqu'à présent, nous savions seulement comment transmettre le [fichier d'entrée principal](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) au moteur TeX sous forme de nom de fichier, qu'il soit entièrement spécifié ou sous forme abrégée, avec ou sans extension. Mais il existe un autre [constructeur](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-java.io.InputStream-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-) de la classe `TeXJob`, qui accepte un flux comme premier argument. Ceci est pratique si, pour une raison quelconque, nous avons le fichier d'entrée principal sous une forme autre qu'un fichier sur le système de fichiers du disque. Voici comment nous pouvons y faire face :

Définissez `outputDirectory` sur un dossier de sortie existant. Importez les classes Aspose.TeX utilisées dans les exemples, `com.aspose.tex.rendering.XpsDevice`, `com.aspose.tex.rendering.XpsSaveOptions` et, pour l’entrée par flux, `java.io.ByteArrayInputStream` et `java.nio.charset.StandardCharsets`. La méthode appelante doit gérer ou déclarer les exceptions. Appliquez une licence conformément au [guide des licences](/tex/{{lang.url-fragment}}java/licensing/) pour éviter les restrictions d’évaluation. L’exemple de flux contient un document LaTeX complet et ne nécessite donc aucun répertoire de travail d’entrée. Les flux et périphériques restent ouverts jusqu’à la fin du travail, puis sont fermés ou libérés.

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-StreamInput-LaTeX.java" >}}

Lorsqu’aucun nom de travail n’est explicitement attribué à l’entrée par flux, le moteur utilise le nom par défaut *texput*. Cet exemple crée `texput.xps` et `texput.log`. Utilisez `options.setJobName(...)` pour choisir un autre nom de travail. Consultez [ici](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) et [ici](/tex/{{lang.url-fragment}}java/other-options/#how-to-set-the-job-name) pour plus de détails sur les noms de travail.

## Saisie du fichier d'entrée principal TeX depuis le terminal

Il existe encore un autre [constructeur](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#TeXJob-com.aspose.tex.rendering.Device-com.aspose.tex.TeXOptions-)  de la classe `TeXJob`, qui ne nous permet pas du tout de spécifier l'entrée. Alors, que va traiter un tel travail TeX, vous vous demandez peut-être ? Cette fois, nous aurons besoin d’un terminal d’entrée. Le moteur TeX nous demandera de saisir le nom du fichier depuis le terminal.

Définissez `inputDirectory` sur un dossier contenant un document LaTeX complet nommé `hello-world.ltx`, et `outputDirectory` sur un dossier de sortie existant. Exécutez l’exemple dans une console, saisissez `hello-world.ltx` à l’invite `**` et appuyez sur Entrée. Il crée `hello-world.xps` et écrit la sortie du terminal dans la console. Les deux exemples utilisent `NonstopMode` pour le traitement, mais le constructeur du terminal nécessite toujours le nom de fichier initial. Pour une exécution sans intervention, fournissez une implémentation de `IInputTerminal` ou utilisez une entrée par fichier ou flux.

Voici le code :

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-MainInputTerminal.java" >}}

Dès qu'il est lancé, le moteur bloque, attendant que nous saisissions le nom du fichier (avec ou sans chemin, avec ou sans extension) :


![Fenêtre du terminal](/tex/images/java/Conversion-MainInputTerminal.png)

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