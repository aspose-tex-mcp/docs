---
translation: true
template: /_templates/_conversion-cpp.md
title: Conversion de fichiers TeX (LaTeX) | C++
url: /cpp/conversion/
keywords: convertisseur tex cpp api, convertisseur tex c++ api
description: Solution d'API C++ de conversion TeX (LaTeX). Convertissez des fichiers LaTeX en PDF, XPS et images, y compris PNG, JPEG, TIFF, BMP avec quelques lignes de code C++.
family: tex
platformtag: cpp
feature: conversion
---

{{<section banner>}}
---
h1: Convertir TeX et LaTeX
h2: "Solution d'API de conversion TeX pour C++."
---

{{<section overview>}}
---
p1: "Aspose.TeX est une API du système Object TeX, pour plus de détails sur le fichier Tex, voici l'[introduction de Tex](https://docs.aspose.com/tex/cpp/what-is-tex/). Les développeurs peuvent facilement convertir TeX en formats PDF, XPS, PNG, JPG, BMP et TIFF en intégrant l'API pour C++. Vous trouverez ci-dessous quelques exemples de code que les programmeurs peuvent améliorer et intégrer dans les solutions LaTex."
p2: "La solution API pour Java ici vous permet de convertir les fichiers TeX et LaTeX par programme, mais vous trouverez peut-être utile de voir et d'essayer [les convertisseurs multiplateformes](https://products.aspose.app/tex/conversion) développés sur ces natifs Apis. Vous y trouverez également des [applications](https://products.aspose.app/tex/applications) pour créer et éditer des fichiers TeX, des tableaux, des graphiques, pour fusionner des fichiers au format PDF, etc."
---

{{<section feature1>}}
---
title: "Convertissez LaTeX en images, XPS, PDF, SVG C++."
h3: "Exemple de code C++ Conversion de TeX en images, XPS, PDF ou SVG."
item1: "L'API prend en charge les formats de sortie BMP, JPEG, PDF, SVG, TIFF, XPS et PNG. Pour convertir des fichiers TeX en images, PDF, XPS ou SVG, procédez comme suit :"
item2: "Créez une instance de la [classe TeXOptions](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options)."
item3: "Définissez le type et la taille de l'image à l'aide de [*ImageDevice*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device)."
item4: "Spécifiez le répertoire de travail du système de fichiers pour la sortie/l'entrée à l'aide de [*OutputWorkingDirectory*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)/[*InputWorkingDirectory*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)."
item5: "Initialisez les options d'enregistrement à l'aide de [*BmpSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.bmp_save_options), [*PngSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.png_save_options), [*TiffSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.tiff_save_options), [*JpegSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.jpeg_save_options) ou [*PdfSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_save_options), [*SvgSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_save_options), [*XpsSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_save_options), qui est la valeur par défaut, pas besoin de définir."
item6: "Exécutez la conversion à l'aide de la méthode Run de [*TeXJob()*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job) pour [ImageDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device) ou [PdfDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_device), [ SvgDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_device), [XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device)."
item7: "Aspose.TeX pour C++ fonctionne bien dans n'importe quel environnement de développement prenant en charge C++, mais les exigences suivantes sont fortement conseillées :"
item8: Microsoft Visual Studio 2015 ou version ultérieure.
item9: Bureau Microsoft Windows (7, 8, 10).
item10: Systèmes d'exploitation serveur (2008, 2012), etc.
item11: Systèmes Linux (Ubuntu-16.04 ou version ultérieure).
---


