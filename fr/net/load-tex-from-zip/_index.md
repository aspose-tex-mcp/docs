---
translation: true
template: /_templates/_load-tex-from-zip-net.md
title: Chargement de TeX depuis ZIP | API .NET
url: /net/load-tex-from-zip/
description: "Solution API .NET pour travailler avec TeX. Apprenez sur l'exemple comment charger un fichier TeX depuis ZIP avec quelques lignes de code C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Charger les fichiers sources TeX depuis ZIP
h2: "Solution API .NET pour charger des fichiers TeX à partir d'une archive ZIP"
---

{{<section overview>}}
---
p1: "TeX est connu comme un langage de composition. Cela signifie que vous ne formatez pas votre texte dans le document, mais entrez le texte brut avec les commandes. En sortie, vous obtiendrez le fichier formaté du format nécessaire (spécifié). Pour mieux comprendre l'entrée et la sortie TeX, découvrez les [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) de la documentation."
p2: "Comme on le sait, le but principal de TeX est d'aider à créer des textes mathématiques ou techniques. Mais avant toute manipulation, le fichier doit d'abord être chargé. Vous trouverez ici des extraits de code expliquant comment charger des fichiers source TeX à partir de ZIP en utilisant des répertoires ZIP pour l'entrée et la sortie, la sortie sur un périphérique PDF, l'écriture de la sortie du terminal sur la console."
p3: "Pour charger les fichiers .tex, nous avons besoin de :"
p4: "Aspose.TeX pour l'API .NET qui est une API de manipulation et de conversion de documents riche en fonctionnalités, puissante et facile à utiliser pour la plate-forme C#."
p5: "Ouvrez le gestionnaire de packages NuGet, recherchez Aspose.TeX et installez-le. Vous pouvez également utiliser la commande suivante à partir de la console du gestionnaire de packages."
---

{{<section feature1>}}
---
title: "Étapes pour charger TeX à partir d'une archive ZIP C# :"
h3: "Code C# pour charger TeX"
item1: "Ouvrez le flux sur l'archive ZIP pour l'utiliser comme répertoire de travail d'entrée."
item2: "Ouvrez le flux sur l'archive ZIP pour l'utiliser comme répertoire de travail de sortie."
item3: "Créez des options de conversion pour le format ObjectTeX par défaut lors de l'extension du moteur ObjectTeX à l'aide de la méthode [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Classe."
item4: "Spécifiez un répertoire de travail d'archive ZIP pour l'entrée ou/et spécifiez un chemin à l'intérieur de l'archive. Utilisez les constructeurs de la classe [*InputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) pour cela."
item5: "Spécifiez un répertoire de travail d'archive ZIP pour la sortie ou/et spécifiez un chemin à l'intérieur de l'archive. Utilisez les constructeurs de la classe [*outputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/) pour cela."
item6: "Spécifiez la console comme terminal de sortie à l'aide de la classe [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item7: "Définissez les options d'enregistrement à l'aide de la classe [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)."
item8: "Exécutez la tâche [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) Méthode pour [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item9: Affiner la sortie.
---