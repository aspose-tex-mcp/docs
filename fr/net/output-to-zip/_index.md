---
translation: true
template: /_templates/_output-to-zip-net.md
title: TeX vers ZIP | Solution d'API .NET
url: /net/output-to-zip/
description: "La Conversion TeX vers ZIP vous permet d'enregistrer votre fichier TeX en tant qu'archive la plus populaire. Exemples C# de cette fonctionnalité."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Écrire la sortie dans ZIP
h2: "Enregistrez le résultat de la conversion du fichier TeX au format ZIP via C# .NET"
---

{{<section overview>}}
---
p1: "TeX est connu comme l'un des langages de balisage de données. C'est le noyau principal du système de jeu de publication (composition informatique). Il est discutable de considérer [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) comme un format de fichier, car c'est un langage de programmation. Et d'autre part, c'est un moteur d'interprétation qui comprend ce langage. Quoi qu'il en soit, en bref, son objectif principal est d'aider à la création de textes mathématiques ou techniques. Mais lorsque le fichier est déjà créé et que vous ne souhaitez plus le modifier, vous pouvez le convertir dans un format différent, plus populaire."
p2: "La solution API Aspose.TeX parmi les différentes autres fonctionnalités permet la conversion de fichiers TeX, puis l'enregistrement du résultat sous forme d'archive ZIP. Vous trouverez ici un extrait de code expliquant comment convertir TeX en PDF et enregistrer la sortie du résultat dans un zip. Le convertisseur d'API transforme TeX en utilisant n'importe quel langage supporté par C#. L'API que vous voyez ici peut également être utilisée pour créer votre propre application multiplateforme ou être intégrée à votre projet .NET. Ces [*convertisseurs multiplateformes*](https://products.aspose.app/tex/conversion/tex) sont également présents dans l'écosystème Aspose. Mais pour exécuter les exemples, nous avons besoin de :"
p3: "Aspose.TeX pour l'API .NET qui est une API de manipulation et de conversion de documents riche en fonctionnalités, puissante et facile à utiliser pour la plate-forme C#."
p4: "Ouvrez le gestionnaire de packages NuGet, recherchez Aspose.TeX et installez-le. Vous pouvez également utiliser la commande suivante à partir de la console du gestionnaire de packages."
---

{{<section feature1>}}
---
title: Étapes pour utiliser les répertoires ZIP pour le fichier TeX de sortie C#.
h3: "Code C# pour utiliser les répertoires ZIP pour la sortie"
item1: "Créez l'instance de [*TeXOptions Class*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/)."
item2: "Spécifiez un répertoire de travail d'archive ZIP pour la sortie à l'aide de la propriété [*OutputWorkingDirectory*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/)."
item3: "Spécifiez la console comme terminal de sortie à l'aide de la classe [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item4: "Définissez les options d'enregistrement à l'aide de la classe [*PdfSaveOptions*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfsaveoptions/)."
item5: "Exécutez la conversion à l'aide de la méthode [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) pour [*PdfDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.pdf/pdfdevice/)"
item6: Affiner la sortie.
item7: "Pour finaliser l'archive ZIP de sortie, utilisez la classe [*OutputZipDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputzipdirectory/)."
---