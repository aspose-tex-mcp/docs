---
translation: true
template: /templates/_template-cpp.md
title: Foire aux questions | Aspose.TeX pour C++
linktitle: FAQ
weight: 80
url: /cpp/faq/
description: Obtenez des réponses à toutes les questions les plus fréquentes sur Aspose.TeX pour C++, qui est une API complète pour la composition et la manipulation de TeX et LaTeX.
lastmod: "2024-09-27"
---

{{<section overview>}}

<br><br>

**Q : Quelle est la fonctionnalité principale de la solution API Aspose.TeX pour C++ ?**

**R :** La fonctionnalité principale d'Aspose.TeX est la création, la manipulation et la conversion par programmation de documents TeX et LaTeX. Il permet de charger des fichiers TeX/LaTeX existants, de modifier leur contenu et d'effectuer des actions telles que l'ajout ou la suppression d'éléments.
<br><br>

**Q : Quels formats Aspose.TeX pour C++ prend-il en charge ?**

**R :** Aspose.TeX prend en charge TeX et LaTeX en entrée et les formats XPS, PDF, PNG, JPEG, TIFF, SVG et BMP en sortie.
<br><br>

**Q : Comment convertir TeX ?**

**R :** C'est très simple. Il vous suffit de faire quelques pas ! 
1. Créez un objet de la classe TeXOptions.
2. Spécifiez la sortie en appelant la méthode set_OutputWorkingDirectory().
3. Initialisez les options de sauvegarde pour le format de sortie et instanciez la classe TeXJob.
4. Exécutez la conversion.

Pour plus d'exemples, veuillez consulter les guides [Conversion](/tex/{{lang.url-fragment}}cpp/conversion/).
<br><br>

**Q : Puis-je créer un format personnalisé à l'aide d'Aspose.TeX pour C++ ?**

**R :** Oui, la bibliothèque dispose de telles fonctionnalités. Il est brièvement décrit dans l'article [Autres formats de sortie de conversion TeX](/tex/cpp/other-tex-formats/#creating-a-custom-format).
<br><br>

**Q : Quels packages sont intégrés dans la solution API Aspose.TeX ?**

**R :** Il existe désormais des [packages LaTeX intégrés Aspose.TeX](/tex/{{lang.url-fragment}}net/embedded-packages/) inclus : 

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

**R :** C'est vraiment simple. Jetez un œil à l’exemple ci-dessous ! 

```C++
    // Create conversion options for the Object TeX/Object LaTeX format upon the Object TeX engine extension.
    System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::ObjectTeX()); // TeXConfig::get_ObjectLaTeX()
    // Specify a file system working directory for the output.
    options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
    // Run the job.
    System::MakeObject<Aspose::TeX::TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world"),
        System::MakeObject<XpsDevice>(), options)->Run();
```
<br><br>

**Q : Comment installer Aspose.TeX pour le package C++ à partir de Nuget ?**

**R :** Ouvrez le gestionnaire de packages NuGet, recherchez Aspose.TeX.Cpp et installez-le. Vous pouvez également utiliser la commande suivante depuis la console Package Manager :

```C++
    PM> Install-Package Aspose.TeX.Cpp
```

**Q : Puis-je restituer des formules LaTeX à l'aide d'Aspose.TeX pour C++ ?**

**R :** Oui, la bibliothèque de rendu mathématique Aspose.TeX vous permet de créer facilement une image SVG ou PNG avec une formule mathématique. 

1. Créez des options de rendu.
2. Spécifiez la couleur d'arrière-plan, le préambule, la résolution, la couleur de premier plan et le facteur de mise à l'échelle.
3. Spécifiez le flux de sortie du fichier journal.
4. Créez un flux de fichiers pour enregistrer l'image de sortie.
5. Créez un objet de la classe *(file format)MathRenderer* et exécutez le rendu de la formule en appelant la méthode *Render()*. 

Pour plus d'exemples, veuillez consulter les guides [Rendu des formules mathématiques LaTeX](/tex/{{lang.url-fragment}}cpp/latex-math-formula-rendering/).
<br><br>

**Q : Où puis-je en savoir plus sur TeX ?**

**R :** Il existe une [base de connaissances pour TeX et LaTeX](/tex/{{lang.url-fragment}}net/introduction-to-tex/) afin que vous puissiez comprendre le sujet plus en profondeur. Jetez également un œil aux [Articles généraux sur LaTeX](/tex/{{lang.url-fragment}}java/general-articles-latex/) qui vous apprendront les règles que tout auteur de document doit suivre. Il définit également la structure du fichier source, qui est essentiellement un programme de composition.
<br><br>

**Q : Aspose.TeX pour C++ peut-il fonctionner avec des archives, en les utilisant comme sortie sans décompresser au préalable les fichiers ni enregistrer le résultat directement dans l'archive ?**

**R :** Oui, ouvrez simplement un flux contenant une archive ZIP qui servira de répertoire de travail d'entrée. Vous pouvez éventuellement spécifier un sous-répertoire dans l'archive. Sinon, le fichier sera recherché dans toute l'archive. Pour spécifier les répertoires de travail de l'archive ZIP pour l'entrée et la sortie, utilisez les classes InputZipDirectory et OutputZipDirectory.
<br><br>

**Q : Puis-je essayer la solution avant de l'acheter ?**

**R :** Oui, vous pouvez facilement télécharger Aspose.TeX pour les produits C++ à des fins d'évaluation. La version d'évaluation d'Aspose.TeX (sans licence spécifiée) fournit toutes les fonctionnalités du produit, à l'exception de certaines [limitations d'évaluation](/tex/{{lang.url-fragment}}cpp/licensing/#evaluation-version-limitations).

Si vous souhaitez essayer Aspose.TeX sans limitations d'évaluation, demandez une [temporary license](https://purchase.aspose.com/temporary-license/) de 30 jours.
<br><br>

**Q : Où puis-je obtenir de l'aide si je rencontre des problèmes avec la bibliothèque ?**

**R :** Consultez le [Forum Aspose](https://forum.aspose.com/c/tex/47) pour obtenir des réponses ou ajoutez un nouveau sujet avec votre problème si vous n'avez pas trouvé celui qui convient à votre problème. 
<br><br>

**Q : Comment puis-je demander une licence pour Aspose.TeX pour C++ ?**

**R :** Utilisez la méthode `License::SetLicense` pour obtenir une licence pour le composant. Le moyen le plus simple de [définir une licence](/tex/{{lang.url-fragment}}cpp/licensing/) est de placer le fichier de licence dans le même dossier que Aspose.TeX.dll et de spécifier le nom du fichier, sans chemin.
<br><br>

**Q : Puis-je voir les fonctionnalités de cette solution API implémentées dans les applications Web ?**

**R :** Consultez nos [solutions Web](https://products.aspose.app/tex/applications) pour convertir, afficher, fusionner et modifier des fichiers TeX et LaTeX, et créer des équations mathématiques et bien d'autres.
<br><br>

