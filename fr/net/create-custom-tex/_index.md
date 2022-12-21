---
translation: true
template: /_templates/_create-custom-tex-net.md
title: Fichiers TeX personnalisés | API .NET
url: /net/create-custom-tex/
description: "API .NET pour travailler avec TeX. Inclut la fonctionnalité pour créer des formats TeX personnalisés. Exemples C# de fonctionnalités pour personnaliser TeX"
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Créer un format TeX personnalisé
h2: "Créer un fichier au format TeX personnalisé via C# .NET"
---

{{<section overview>}}
---
p1: "TeX est connu comme l'un des langages de balisage de données. C'est le noyau principal du système de jeu de publication (composition informatique). Il est discutable de considérer [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) comme un format de fichier, car c'est un langage de programmation. Et d'autre part, c'est un moteur d'interprétation qui comprend ce langage. Quoi qu'il en soit, en bref, son objectif principal est d'aider à la création de textes mathématiques ou techniques. De nombreux paquets différents ont été créés sur la base de ΤeΧ. Ils visent à faciliter le traitement des documents, notamment lorsqu'ils comportent des formules ou des équations mathématiques."
p2: "La solution API Aspose.TeX parmi les différentes autres fonctionnalités permet de créer vos propres fichiers TeX en vedette. Vous trouverez ici des informations qui expliquent comment créer des fichiers d'un tel format personnalisé. Un tel fichier aura les options de moteur personnalisées. Pour cela nous avons besoin de :"
p3: "Aspose.TeX pour l'API .NET qui est une API de manipulation et de conversion de documents riche en fonctionnalités, puissante et facile à utiliser pour la plate-forme C#."
p4: "Ouvrez le gestionnaire de packages NuGet, recherchez Aspose.TeX et installez-le. Vous pouvez également utiliser la commande suivante à partir de la console du gestionnaire de packages."
---

{{<section feature1>}}
---
title: Étapes pour créer un fichier TeX personnalisé C#.
h3: "Code C# pour personnaliser les fichiers TeX"
item1: "Utilisation de la méthode [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) de [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Classe, crée des options de moteur TeX pour aucun format lors de l'extension du moteur ObjectTeX."
item2: "À l'aide de la classe [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/), spécifiez un répertoire de travail du système de fichiers pour l'entrée."
item3: "Utilisez la classe [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) pour spécifier un répertoire de travail du système de fichiers pour la sortie."
item4: "Créez le format à l'aide de la méthode [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)."
item5: Affiner la sortie.
---