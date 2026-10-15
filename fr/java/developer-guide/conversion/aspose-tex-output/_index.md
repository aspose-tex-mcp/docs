---
translation: true
template: /templates/_template-java.md
title: Interface de sortie d'Aspose.TeX | Java
linktitle: Interface de sortie d'Aspose.TeX
weight: 16
url: /java/aspose-tex-output/
description: De conversion de la solution API Aspose.TeX pour Java avec TeX, en tant que format de sortie, est expliquée ici avec les exemples de code.
lastmod: "2026-04-21"
---

{{<section overview>}}

Veuillez vous référer à **Aspose.TeX for Java** [Référence API](https://reference.aspose.com/tex/java/com.aspose.tex/) pour les définitions formelles de l'implémentation des E/S.

Les exemples de système de fichiers, ZIP et terminal composent `hello-world.tex` en XPS. Définissez `inputDirectory` sur un dossier contenant le fichier TeX et `outputDirectory` sur un dossier de sortie existant. Pour la sortie ZIP, `outputZip` doit être un `java.nio.file.Path` dans un dossier existant. Importez les classes Aspose.TeX utilisées dans l’exemple choisi, `com.aspose.tex.rendering.XpsDevice` et les classes nécessaires de `java.io` et `java.nio.file`. La méthode appelante doit gérer ou déclarer les exceptions. Appliquez une licence conformément au [guide des licences](/tex/{{lang.url-fragment}}java/licensing/) pour éviter les restrictions d’évaluation.

## Le concept du répertoire de sortie

Étant donné que les primitives d'E/S du langage TeX ne peuvent traiter que les noms de fichiers, Aspose.TeX définit un répertoire comme un mappage entre les noms et les lots de données. Les masses de données sont censées être des fichiers, des flux, des tableaux ou quoi que ce soit d'autre. L'API nous permet de spécifier séparément les répertoires de travail d'entrée et de sortie. Il fournit l'interface générale [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/) pour la sortie, que l'utilisateur peut implémenter à ses propres fins. Il fournit également ses propres implémentations, qui seront discutées ci-dessous. L'interface étend [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), puisque le moteur peut d'abord créer et écrire un fichier, puis le relire. La propre méthode de l'interface [getOuputFile()](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/#getOutputFile-java.lang.String-java.lang.String:A-) renvoie le flux dans lequel écrire, par opposition au flux à lire renvoyé par [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-).

### Écriture de la sortie du fichier sur le système de fichiers du disque

Comme nous l'avons mentionné [ci-dessus](/tex/{{lang.url-fragment}}/java/conversion/), la valeur la plus courante pour [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) serait probablement une instance de la classe [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/).

Voici comment nous le définirions :

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileSystemDirectory.java" >}}

Ce cas d'utilisation est assez simple, nous ne nous y attarderons donc pas longtemps.

### Écriture de la sortie du fichier dans une archive ZIP

Nous pouvons également créer un fichier (ou un flux) et laisser le moteur TeX l'utiliser comme archive ZIP pour stocker les fichiers de sortie. C'est ici:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputZipDirectory.java" >}}

Tout d'abord, nous créons un flux de sortie pour le fichier ZIP. Ensuite, après avoir créé les options de conversion, nous définissons l'option [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) comme étant une instance de la classe [OutputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputzipdirectory/). L’exemple stocke `hello-world.xps` et `hello-world.log` dans l’archive. Après le travail, appelez `finish()` sur le répertoire de sortie avant de fermer le flux sous-jacent. Les exemples gardent leurs flux et répertoires de travail ouverts jusqu’à la fin du travail, puis les ferment.

## Le concept du terminal de sortie

Il y a une autre partie importante de la sortie : la sortie du terminal. Quant à celui-ci, **Aspose.TeX for Java** définit l'interface générale [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/) comme ayant deux méthodes. L'un d'eux renvoie une instance de [BufferedWriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html). Un autre renvoie une instance [OutputStream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html) comme flux sous-jacent. Les implémentations fournies de l’interface sont décrites ci-dessous.

### Écriture de la sortie du terminal sur la console

Pour ce faire, nous devons définir l'option [TerminalOut](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalOut--) pour qu'elle soit une instance de la classe [OutputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/outputconsoleterminal/).

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputConsoleTerminal.java" >}}

`OutputConsoleTerminal` est la valeur par défaut de cette option. L’exemple le sélectionne explicitement et écrit la sortie du terminal dans la console pendant la conversion. Les quatre exemples s’exécutent sans interaction ; les exemples de système de fichiers et ZIP capturent la sortie du terminal en mémoire.

### Écrire la sortie du terminal dans un fichier

Contrairement au terminal d'entrée, **Aspose.TeX pour Java** fournit une implémentation de [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/), qui nous permet d'écrire la sortie du terminal dans un fichier dans un répertoire de sortie.

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-OutputFileTerminal.java" >}}

Définissez le répertoire de travail de sortie avant de créer `OutputFileTerminal`. Il écrit la sortie du terminal dans [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, ici `hello-world.trm`, dans ce répertoire. Ce fichier du terminal est distinct de la transcription TeX `hello-world.log`. Pour écrire la sortie du terminal ailleurs, transmettez au constructeur une autre implémentation de [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/).