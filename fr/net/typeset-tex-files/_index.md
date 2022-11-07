---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: Fonctionnalité de composition TeX | API .NET
url: /net/typeset-tex-files/
description: "Solution API .NET pour travailler avec TeX. Apprenez sur l'exemple comment créer des compositions TeX avec quelques lignes de code C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Composer des fichiers TeX
h2: "Composer un fichier TeX à l'aide d'un format TeX personnalisé C# .NET"
---

{{<section overview>}}
---
p1: "TeX est connu comme l'un des langages de balisage de données et/ou un langage de composition en même temps. Cela signifie que vous ne formatez pas votre texte dans le document, mais entrez le texte brut avec les commandes. En sortie, vous obtiendrez le fichier formaté du format nécessaire (spécifié). [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) est le noyau central du système d'ensemble de publication (composition informatique)."
p2: "Pour mieux comprendre la composition de TeX, découvrez les [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) de la documentation. Et sur cette page, vous trouverez des extraits de code expliquant comment composer un fichier TeX en utilisant un format TeX personnalisé."
p3: "Pour exécuter les exemples, nous avons besoin de :"
p4: "Aspose.TeX pour l'API .NET qui est une API de manipulation et de conversion de documents riche en fonctionnalités, puissante et facile à utiliser pour la plate-forme C#."
p5: "Ouvrez le gestionnaire de packages NuGet, recherchez Aspose.TeX et installez-le. Vous pouvez également utiliser la commande suivante à partir de la console du gestionnaire de packages."
---

{{<section feature1>}}
---
title: Étapes pour composer TeX en utilisant C#.
h3: "Code C# pour composer TeX"
item1: "Créez le fournisseur de format à l'aide de la classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item2: "Créez des options de conversion pour un format personnalisé sur l'extension du moteur ObjectTeX à l'aide de la méthode [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Classe."
item3: "Spécifiez le répertoire de travail d'entrée si l'entrée principale n'est pas fournie sous forme de flux. Utilisez la classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) pour cela."
item4: "Spécifiez un répertoire de travail du système de fichiers pour la sortie. Utilisez la classe [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) pour cela."
item5: "Exécutez la tâche [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Méthode pour [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item6: Affiner la sortie.
---