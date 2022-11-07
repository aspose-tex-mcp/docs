---
translation: true
template: /_templates/_customize-output-net.md
title: Créer une sortie personnalisée TeX | API .NET
url: /net/customize-output/
description: "Solution API .NET pour travailler avec TeX. Lisez l'exemple comment créer une sortie personnalisée pour le fichier TeX avec quelques lignes de code C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Personnaliser la sortie
h2: "Solution API .NET pour personnaliser la sortie des fichiers TeX"
---

{{<section overview>}}
---
p1: "TeX est connu comme un langage de composition. Cela signifie que vous ne formatez pas votre texte dans le document, mais entrez le texte brut avec les commandes."
p2: "L'article [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) de la Documentation nous apprend qu'un fichier TeX ne peut contenir aucune donnée à composer mais uniquement des séquences de contrôle . Pourtant, il contient généralement de telles données et un fichier au format cible contient le texte composé. Le fichier aura également le même nom que le fichier spécifié comme entrée et est le fichier de sortie principal. Pour le TeX original, il s'agit d'un fichier au format DVI. Nous appellerons le nom des fichiers d'entrée et de sortie sans étendre le nom du travail."
p3: "Sur cette page, vous trouverez un exemple de code expliquant la création d'un fichier au format TeX personnalisé où vous pourrez voir comment personnaliser la sortie des fichiers TeX. Pour personnaliser la sortie des fichiers .tex, nous avons besoin :"
p4: "Aspose.TeX pour l'API .NET qui est une API de manipulation et de conversion de documents riche en fonctionnalités, puissante et facile à utiliser pour la plate-forme C#."
p5: "Ouvrez le gestionnaire de packages NuGet, recherchez Aspose.TeX et installez-le. Vous pouvez également utiliser la commande suivante à partir de la console du gestionnaire de packages."
---

{{<section feature1>}}
---
title: "Étapes pour personnaliser la sortie TeX C# :"
h3: "Code C# pour la personnalisation de la sortie TeX"
item1: "Avec l'aide de la méthode [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Classe, crée des options de moteur TeX pour aucun format lors de l'extension du moteur ObjectTeX."
item2: "Utilisez la classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) pour spécifier un répertoire de travail du système de fichiers pour l'entrée."
item3: "Utilisez la classe [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) pour spécifier un répertoire de travail du système de fichiers pour la sortie."
item4: "Pour créer le nouveau format, utilisez la méthode [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)."
item5: Affiner la sortie.
---