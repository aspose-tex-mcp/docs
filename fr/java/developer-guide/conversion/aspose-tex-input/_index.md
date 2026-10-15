---
translation: true
template: /templates/_template-java.md
title: Interface de saisie d'Aspose.TeX | Java
linktitle: Interface de saisie d'Aspose.TeX
weight: 15
url: /java/aspose-tex-input/
description: De conversion de la solution API Aspose.TeX pour Java avec TeX, en tant que format d'entrée, est expliquée ici avec les exemples de code.
lastmod: "2026-04-21"
---

{{<section overview>}}

Veuillez vous référer à **Aspose.TeX for Java** [Référence API](https://reference.aspose.com/tex/java/com.aspose.tex/) pour les définitions formelles de l'implémentation des E/S.

Les exemples de système de fichiers et ZIP composent `hello-world.tex` dans `hello-world.xps`. Définissez `inputDirectory` sur un dossier contenant le fichier TeX et `outputDirectory` sur un dossier de sortie existant. Pour l’entrée ZIP, `inputZip` doit être un `java.nio.file.Path` vers une archive contenant `in/hello-world.tex`. Importez les classes Aspose.TeX utilisées dans l’exemple choisi, `com.aspose.tex.rendering.XpsDevice` et les classes nécessaires de `java.io` et `java.nio.file`. La méthode appelante doit gérer ou déclarer les exceptions. Appliquez une licence conformément au [guide des licences](/tex/{{lang.url-fragment}}java/licensing/) pour éviter les restrictions d’évaluation.

## Le concept du répertoire d'entrée

Étant donné que les primitives d'E/S du langage TeX ne peuvent traiter que les noms de fichiers, **Aspose.TeX pour Java** définit un répertoire comme un mappage entre des noms et des lots de données. Les masses de données sont censées être des fichiers, des flux, des tableaux ou quoi que ce soit d'autre. L'API nous permet de spécifier séparément les répertoires de travail d'entrée et de sortie. Il fournit l'interface générale [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), que l'utilisateur peut implémenter pour ses propres besoins. Il fournit également ses propres implémentations, qui seront discutées ci-dessous. L'interface définit la méthode [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-), qui renvoie le flux de données et détermine le nom complet du fichier, tout en prenant un nom, hypothétiquement différent, comme premier argument, qui, en fait, est la clé de mappage. .

### Obtenir une entrée de fichier à partir du système de fichiers du disque

Voici comment nous procéderions :

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputFileSystemDirectory.java" >}}

Ce cas d'utilisation est assez simple, nous ne nous y attarderons donc pas longtemps.

### Obtenir une entrée de fichier à partir d'une archive ZIP

Nous pouvons également mettre les fichiers d'entrée dans une archive ZIP et la considérer comme un répertoire d'entrée. Dans ce cas, il faut procéder comme suit :

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputZipDirectory.java" >}}

Tout d'abord, nous créons le flux contenant le fichier ZIP. Ensuite, après avoir créé les options de conversion, nous définissons l'option [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--) comme étant une instance de la classe [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/). Le deuxième argument du constructeur est le chemin de base à l'intérieur de l'archive. Si nous voulons que l'archive entière soit un répertoire d'entrée, nous devons transmettre la chaîne vide. L’exemple garde le flux ZIP et le répertoire d’entrée ouverts jusqu’à la fin du travail TeX, puis les ferme. Il s’exécute sans interaction et capture la sortie du terminal en mémoire.

## Le concept du terminal d'entrée

Rappelons maintenant qu'il y a aussi l'entrée du terminal. Quant à celui-ci, **Aspose.TeX for Java** définit l'interface générale [IInputTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/iinputterminal/) comme ayant deux méthodes. L'un d'eux renvoie une instance de [BufferedReader](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedReader.html). Une autre méthode renvoie un [InputStream](https://docs.oracle.com/javase/6/docs/api/java/io/InputStream.html) comme flux sous-jacent. Les implémentations fournies de l’interface sont décrites ci-dessous.

### Obtenir l'entrée du terminal depuis la console

Pour ce faire, nous devons définir l'option [TerminalIn](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalIn--) pour qu'elle soit une instance de la classe [InputConsoleTerminal](https://reference.aspose.com/tex/java/com.aspose.tex/inputconsoleterminal/).

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputConsoleTerminal.java" >}}

`InputConsoleTerminal` est la valeur par défaut de cette option. Cet exemple illustre uniquement la configuration du terminal et n’exécute aucun travail. Un travail demandant une entrée du terminal nécessite une saisie utilisateur ou une implémentation personnalisée du terminal. Les exemples de système de fichiers et ZIP ci-dessus s’exécutent sans interaction avec des fichiers d’entrée complets.

Théoriquement, si nous disposons d'un fichier (ou script) TeX interactif avec un comportement prévisible, nous souhaiterons peut-être implémenter une version du terminal d'entrée qui contiendrait un script complémentaire pour répondre aux requêtes du moteur TeX. Essayez-vous quand vous avez le temps !