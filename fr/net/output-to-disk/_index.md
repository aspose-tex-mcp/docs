---
translation: true
template: /_templates/_output-to-disk-net.md
title: Écrire la sortie TeX sur le disque | API .NET
url: /net/output-to-disk/
description: "API .NET pour travailler avec TeX. Apprenez sur l'exemple comment créer une sortie personnalisée pour le fichier TeX avec quelques lignes de code C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Écrire la sortie TeX sur le disque
h2: "Enregistrez le résultat de la conversion du fichier TeX sur le disque via C# .NET"
---

{{<section overview>}}
---
p1: "TeX est connu comme un langage de composition, ce qui signifie que vous ne formatez pas votre texte dans le document, mais entrez le texte brut avec les commandes. Comme il est connu de l'article [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) de la documentation, le travail TeX s'exécute sur un fichier TeX explicitement spécifié. Vous pouvez également y trouver des informations sur les modes d'interaction TeX et les primitives liées à l'entrée et à la sortie TeX."
p2: "L'utilisation principale de TeX est d'aider à la création de textes mathématiques ou techniques. Mais lorsque le fichier est déjà créé et que vous ne souhaitez plus le modifier, vous pouvez le convertir dans un format différent, plus populaire."
p3: "Sur cette page, vous trouverez un exemple de code expliquant l'utilisation des répertoires du système de fichiers pour l'entrée et la sortie, la sortie vers un périphérique XPS, le remplacement du nom de la tâche, l'écriture de la sortie du terminal sur le disque. En termes simples, il s'agit d'une conversion avec écriture de la sortie sur le disque. Pour exécuter une telle opération, nous avons besoin de :"
p4: "Aspose.TeX pour l'API .NET qui est une API de manipulation et de conversion de documents riche en fonctionnalités, puissante et facile à utiliser pour la plate-forme C#."
p5: "Ouvrez le gestionnaire de packages NuGet, recherchez Aspose.TeX et installez-le. Vous pouvez également utiliser la commande suivante à partir de la console du gestionnaire de packages."
---

{{<section feature1>}}
---
title: "Étapes pour écrire la sortie du terminal sur le disque C# :"
h3: "Code C# pour convertir TeX et écrire la sortie sur le disque"
item1: "Créez des options de conversion sur l'extension du moteur ObjectTeX à l'aide de [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Méthode de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Classe."
item2: "Spécifiez un nom de travail si vous ne voulez pas que le premier argument du constructeur TeXJob soit pris comme nom de travail."
item3: "Spécifiez un répertoire de travail du système de fichiers pour l'entrée. Utilisez la classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) pour cela."
item4: "Spécifiez un répertoire de travail du système de fichiers pour la sortie à l'aide des entités de la classe [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item5: "Spécifiez que la sortie du terminal doit être écrite dans un fichier du répertoire de travail de sortie."
item6: "Exécutez la tâche [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Méthode pour [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
---