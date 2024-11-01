---
translation: true
template: /templates/_template-java.md
title: Interface de sortie d'Aspose.TeX | Java
linktitle: Interface de sortie d'Aspose.TeX
weight: 16
url: /java/aspose-tex-output/
description: De conversion de la solution API Aspose.TeX pour Java avec TeX, en tant que format de sortie, est expliquée ici avec les exemples de code.
lastmod: "2024-09-27"
---

{{<section overview>}}

Veuillez vous référer à **Aspose.TeX for Java** [Référence API](https://reference.aspose.com/tex/java/com.aspose.tex/package-frame) pour les définitions formelles de l'implémentation des E/S.

## Le concept du répertoire de sortie

Étant donné que les primitives d'E/S du langage TeX ne peuvent traiter que les noms de fichiers, Aspose.TeX définit un répertoire comme un mappage entre les noms et les lots de données. Les masses de données sont censées être des fichiers, des flux, des tableaux ou quoi que ce soit d'autre. L'API nous permet de spécifier séparément les répertoires de travail d'entrée et de sortie. Il fournit l'interface générale [IOutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputWorkingDirectory) pour la sortie, que l'utilisateur peut implémenter à ses propres fins. Il fournit également ses propres implémentations, qui seront discutées ci-dessous. L'interface étend [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory), puisque le moteur peut d'abord créer et écrire un fichier, puis le relire. La propre méthode de l'interface [getOuputFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputWorkingDirectory#getOutputFile-java.lang.String-java.lang.String:A-) renvoie le flux dans lequel écrire, par opposition au flux à lire renvoyé par [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-).

### Écriture de la sortie du fichier sur le système de fichiers du disque

Comme nous l'avons mentionné [ci-dessus](/tex/{{lang.url-fragment}}java/latex-to-png/), la valeur la plus courante pour [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) serait probablement une instance de la classe [OutputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputFileSystemDirectory).

Voici comment nous le définirions :

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.java" >}}

Ce cas d'utilisation est assez simple, nous ne nous y attarderons donc pas longtemps.

### Écriture de la sortie du fichier dans une archive ZIP

Nous pouvons également créer un fichier (ou un flux) et laisser le moteur TeX l'utiliser comme archive ZIP pour stocker les fichiers de sortie. C'est ici:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-OutputZipDirectory.java" >}}

Tout d'abord, nous créons un flux de sortie pour le fichier ZIP. Ensuite, après avoir créé les options de conversion, nous définissons l'option [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getOutputWorkingDirectory--) comme étant une instance de la classe [OutputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/OutputZipDirectory).

## Le concept du terminal de sortie

Il y a une autre partie importante de la sortie : la sortie du terminal. Quant à celui-ci, **Aspose.TeX for Java** définit l'interface générale [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal) comme ayant deux méthodes. L'un d'eux renvoie une instance de [BufferedWriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html). Un autre renvoie une instance [OutputStream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html) comme flux sous-jacent. Les implémentations fournies de l’interface sont décrites ci-dessous.

### Écriture de la sortie du terminal sur la console

Pour ce faire, nous devons définir l'option [TerminalOut](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getTerminalOut--) pour qu'elle soit une instance de la classe [OutputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/OutputConsoleTerminal).

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.java" >}}

Encore une fois, il s’agit de la valeur par défaut de l’option, il n’est donc pas vraiment nécessaire de la spécifier. Pour cette raison, cette section sert uniquement à des fins de démonstration.

### Écrire la sortie du terminal dans un fichier

Contrairement au terminal d'entrée, **Aspose.TeX pour Java** fournit une implémentation de [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal), qui nous permet d'écrire la sortie du terminal dans un fichier dans un répertoire de sortie.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-OutputFileTerminal.java" >}} 

Ici, nous demandons au moteur TeX d'écrire la sortie du terminal dans le fichier portant le nom [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output).trm, qui sera stocké dans le même répertoire de sortie que celui que nous avons spécifié pour le reste de la sortie. Mais ce n'est pas nécessaire. Nous pourrions aussi bien transmettre toute autre instance de toute implémentation de [IOutputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/IOutputTerminal) au constructeur.