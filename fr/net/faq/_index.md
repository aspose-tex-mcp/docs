---
translation: true
template: /templates/_template-net.md
title: Foire aux questions | Aspose.TeX pour .NET
linktitle: FAQ
weight: 80
url: /net/faq/
description: Obtenez des réponses aux questions fréquemment posées sur Aspose.TeX pour .NET, qui est une API pour la composition et la manipulation de TeX et LaTeX.
lastmod: "2026-11-02"
---

{{<section overview>}}

<br><br>

**Q : Quelle est la fonctionnalité principale de la solution API Aspose.TeX ?**

**R :** Aspose.TeX est une solution API complète pour la composition de TeX et LaTeX qui vous permet de créer des équations LaTeX, ainsi que de créer et convertir des fichiers TeX. Il s'agit d'une gestion efficace de documents TeX et de création de formules.
<br><br>

**Q : Quels formats Aspose.TeX prend-il en charge ?**

**R :** Aspose.TeX prend en charge TeX et LaTeX en entrée et les formats XPS, PDF, PNG, JPEG, TIFF, SVG et BMP en sortie.
<br><br>

**Q : Comment convertir TeX ?**

**R :** C'est très simple. Il vous suffit de faire quelques pas ! 

1. Initiez la classe [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/).
2. Spécifiez le répertoire de travail du système de fichiers pour la sortie en définissant la propriété [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/).
3. Initialisez les options de sauvegarde pour le format de sortie à l'aide de la classe (format de fichier)SaveOptions.
4. Convertissez TeX en utilisant la méthode [Run()](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/).

Pour plus d'exemples, veuillez consulter les guides [Conversion](/tex/{{lang.url-fragment}}net/conversion/).
<br><br>

**Q : Quels packages LaTeX externes sont pris en charge par Aspose.TeX ?**

**R :** Vous pouvez utiliser la plupart des packages mais il y a quelques [restrictions](/tex/{{lang.url-fragment}}net/external-latex-packages/#restrictions) ici.
<br><br>

**Q : Quels packages sont intégrés dans la solution API Aspose.TeX ?**

**R :** Selon la liste des [packages LaTeX intégrés Aspose.TeX](/tex/{{lang.url-fragment}}net/embedded-packages/), ils sont : 

- eurosym
- geometry
- graphics
- hyperref
- multirow
- pgf
- pict2e
- setspace
- latex-tools bundle: array, bm, calc, dcolumn, delarray, enumerate, fileerr, fontsmpl, ftnright, hhline, indentfirst, layout, longtable, multicol, rawfonts, showkeys, somedefs, tabularx, theorem, trace, varioref, verbatim, xr et xspace.
- url
- wasysym
- xcolor 
<br><br>

**Q : Comment composer des fichiers TeX ?**

**R :** C'est très simple. Il vous suffit de faire quelques pas ! 
1. Créez des paramètres de conversion adaptés au format Object TeX ou Object LaTeX.
2. Désignez un répertoire dans le système de fichiers pour la sortie résultante.
3. Instanciez la classe TeXJob et lancez l'opération de composition en appelant la méthode *TeXJob.Run*().
<br><br>

**Q : Comment installer le package Aspose.TeX à partir de Nuget ?**

**R :** Ouvrez le gestionnaire de packages NuGet, recherchez Aspose.TeX et installez-le. Vous pouvez également utiliser la commande suivante depuis la console Package Manager :

{{< highlight csharp>}}
    PM> Install-Package Aspose.TeX
{{< /highlight >}}

**Q : Comment afficher des formules LaTeX à l'aide d'Aspose.TeX ?**

**R :** La bibliothèque de rendu mathématique Aspose.TeX vous permet de créer une image SVG ou PNG contenant une formule mathématique en quelques étapes seulement :

1. Créez un objet de la classe *(file format)MathRendererOptions*.
2. Spécifiez la couleur d'arrière-plan à l'aide de la propriété BackgroundColor des options si nécessaire.
3. Configurez un flux de mémoire pour capturer la sortie du journal générée pendant le processus de rendu à l'aide de la propriété *LogStream*.
4. Créez un flux de fichiers pour enregistrer l'image de sortie.
5. Créez un objet de la classe *(file format)MathRenderer* et exécutez le rendu de la formule en appelant la méthode *Render()*. 

Pour plus d'exemples, veuillez consulter les guides [Rendu des formules mathématiques LaTeX](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/).
<br><br>

**Q : Où puis-je en savoir plus sur TeX ?**

**R :** Il existe une [base de connaissances pour TeX et LaTeX](/tex/{{lang.url-fragment}}net/introduction-to-tex/) afin que vous puissiez comprendre le sujet plus en profondeur. Jetez également un œil aux [Articles généraux sur LaTeX](/tex/{{lang.url-fragment}}java/general-articles-latex/) qui vous apprendront les règles que tout auteur de document doit suivre. Il définit également la structure du fichier source, qui est essentiellement un programme de composition.
<br><br>

**Q : Quelles méthodes de lecture des entrées et d'écriture des sorties sont prises en charge par Aspose.TeX ?**

**R :** Dans cette solution API, vous pouvez charger des fichiers TeX et écrire la sortie depuis/vers :

- Répertoire du système de fichiers
- Archives ZIP
- Le fichier TeX principal peut également être transmis via un flux
<br><br>

**Q : Puis-je essayer la solution avant de l'acheter ?**

**R :** Oui, vous pouvez facilement télécharger le produit Aspose.TeX pour .NET à des fins d'évaluation. La version d'évaluation d'Aspose.TeX (sans licence spécifiée) fournit toutes les fonctionnalités du produit, à l'exception de certaines [limitations d'évaluation](/tex/{{lang.url-fragment}}net/licensing/#evaluation-version-limitations).

Si vous souhaitez essayer Aspose.TeX sans limitations d'évaluation, demandez une [licence temporaire](https://purchase.aspose.com/temporary-license/) de 30 jours.
<br><br>

**Q : Où puis-je obtenir de l'aide en cas de problème avec la solution ?**

**R :** Consultez le [Forum Aspose](https://forum.aspose.com/c/tex/47) pour obtenir des réponses ou ajoutez un nouveau sujet avec votre problème si vous n'avez pas trouvé celui qui convient à votre problème. 
<br><br>

**Q : Comment la solution API Aspose.TeX garantit-elle la compatibilité multiplateforme ?**

**R :** La solution API Aspose.TeX est conçue pour être indépendante de la plate-forme, permettant aux développeurs de créer des fonctionnalités qui fonctionnent de manière cohérente sur différents systèmes d'exploitation et environnements. Sous Windows, vous pouvez utiliser le package NuGet `Aspose.TeX` ou `Aspose.TeX.Drawing`. Sous Linux, macOS et dans des conteneurs Docker, utilisez `Aspose.TeX.Drawing`, qui ne dépend pas de `System.Drawing.Common`. Voir [Linux, macOS et Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/).
<br><br>

**Q : Pourquoi est-ce que j'obtiens « PlatformNotSupportedException: System.Drawing.Common is not supported on this platform » ?**

**R :** Votre application utilise le package `Aspose.TeX` sous Linux ou macOS. Ce package dépend de `System.Drawing.Common`, que Microsoft ne prend en charge que sous Windows à partir de .NET 6. Remplacez-le par le package `Aspose.TeX.Drawing`, qui a la même API. Voir [Linux, macOS et Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/) pour plus de détails.
<br><br>

**Q : Où puis-je voir les fonctionnalités de cette solution API implémentées dans les applications Web ?**

**R :** Consultez nos [solutions Web](https://products.aspose.app/tex/applications) pour convertir, afficher, fusionner et modifier des fichiers TeX et LaTeX et créer des équations mathématiques. Ce sont les exemples les plus brillants que vous pouvez utiliser l’API pour développer vos propres produits.

Consultez également [Aspose.TeX AI Agents**](https://products.aspose.ai/tex/) - une combinaison de notre expérience dans le développement d'API pour le traitement de fichiers TeX et LaTeX et d'intelligence artificielle.
<br><br>

