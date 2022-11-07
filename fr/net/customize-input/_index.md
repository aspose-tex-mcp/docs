---
translation: true
template: /_templates/_customize-input-net.md
title: Créer une entrée personnalisée TeX | API .NET
url: /net/customize-input/
description: "Solution API .NET pour travailler avec TeX. Apprenez sur l'exemple comment créer une entrée personnalisée pour le fichier TeX avec quelques lignes de code C#."
keywords: entrée personnalisée tex net api, C# api pour personnaliser tex
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Personnaliser la saisie
h2: "Solution API .NET pour personnaliser la saisie des fichiers TeX"
---

{{<section overview>}}
---
p1: "TeX est connu comme un langage de composition. Cela signifie que vous ne formatez pas votre texte dans le document, mais entrez le texte brut avec les commandes. Comme décrit dans l'article [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) de la documentation, le travail TeX s'exécute sur un fichier TeX explicitement spécifié. Donc, nous incluons ce fichier dans l'entrée d'un certain travail TeX."
p2: "Sur cette page, vous trouverez un exemple de code expliquant comment personnaliser l'entrée des fichiers source TeX en tenant compte du fait que l'entrée doit suivre la syntaxe TeX et, idéalement, ne contenir que des commandes connues du moteur."
p3: "Pour personnaliser l'entrée des fichiers .tex, nous avons besoin de :"
p4: "Aspose.TeX pour l'API .NET qui est une API de manipulation et de conversion de documents riche en fonctionnalités, puissante et facile à utiliser pour la plate-forme C#."
p5: "Ouvrez le gestionnaire de packages NuGet, recherchez Aspose.TeX et installez-le. Vous pouvez également utiliser la commande suivante à partir de la console du gestionnaire de packages."
---

{{<section feature1>}}
---
title: "Étapes pour personnaliser l'entrée TeX C# :"
h3: "Code C# pour la personnalisation des entrées TeX"
item1: "Utilisation de la méthode [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Classe, crée des options de moteur TeX pour aucun format lors de l'extension du moteur ObjectTeX."
item2: "À l'aide de la classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/), spécifiez un répertoire de travail du système de fichiers pour l'entrée."
item3: "À l'aide de la méthode [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/), créez le format personnalisé."
---