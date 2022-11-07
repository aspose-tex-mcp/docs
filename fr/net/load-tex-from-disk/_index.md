---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: Charger TeX depuis un disque | API .NET
url: /net/load-tex-from-disk/
description: "Solution API .NET pour travailler avec TeX. Apprenez sur l'exemple comment charger un fichier TeX à partir du disque avec quelques lignes de code C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Charger les fichiers source TeX à partir du disque
h2: "Solution API .NET pour charger des fichiers TeX/LaTeX à partir du disque"
---

{{<section overview>}}
---
p1: "TeX est connu comme un langage de composition. Cela signifie que vous ne formatez pas votre texte dans le document, mais entrez le texte brut avec les commandes. En sortie, vous obtiendrez le fichier formaté du format nécessaire (spécifié). [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) est le noyau central du système d'ensemble de publication (composition informatique). Un travail TeX s'exécute sur un fichier TeX explicitement spécifié. Pour mieux comprendre l'entrée et la sortie TeX, découvrez les [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) de la documentation."
p2: "Comme on le sait, le but principal de TeX est d'aider à créer des textes mathématiques ou techniques. Mais avant toute manipulation, le fichier doit d'abord être chargé. Vous trouverez ici des extraits de code expliquant comment charger les fichiers source TeX à partir du disque en utilisant les répertoires du système de fichiers pour l'entrée et la sortie, la sortie vers le périphérique XPS, l'écriture de la sortie du terminal vers la console."
p3: "Pour exécuter les exemples, nous avons besoin de :"
p4: "Aspose.TeX pour l'API .NET qui est une API de manipulation et de conversion de documents riche en fonctionnalités, puissante et facile à utiliser pour la plate-forme C#."
p5: "Ouvrez le gestionnaire de packages NuGet, recherchez Aspose.TeX et installez-le. Vous pouvez également utiliser la commande suivante à partir de la console du gestionnaire de packages."
---

{{<section feature1>}}
---
title: Étapes pour charger TeX à partir d'un disque C#.
h3: "Code C# pour charger TeX"
item1: "Créez des options de conversion pour un format personnalisé sur l'extension du moteur ObjectTeX à l'aide de la méthode [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Classe."
item2: "Spécifiez un répertoire de travail du système de fichiers pour l'entrée. Utilisez la classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) pour cela."
item3: "Spécifiez un répertoire de travail du système de fichiers pour la sortie à l'aide de la classe [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item4: "Spécifiez la console comme terminal de sortie à l'aide de la classe [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item5: "Spécifiez un terminal de mémoire comme terminal de sortie si nécessaire. Pour cela, utilisez la classe [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/)."
item6: "Exécutez la tâche [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Méthode pour [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item7: Affiner la sortie.
---