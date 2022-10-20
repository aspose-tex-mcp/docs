---
translation: true
template: /_templates/_conversion-cpp.md
title: Conversione file TeX (LaTeX) | C++
url: /cpp/conversion/
keywords: tex converter cpp api, tex converter c++ api
description: Soluzione API C++ di conversione TeX(LaTeX). Converti file LaTeX in PDF, XPS e immagini inclusi PNG, JPEG, TIFF, BMP con poche righe di codice C++.
family: tex
platformtag: cpp
feature: conversion
---

{{<section banner>}}
---
h1: Converti TeX e LaTeX
h2: "Soluzione API convertitore TeX per C++."
---

{{<section overview>}}
---
p1: "Aspose.TeX è un'API per il sistema Object TeX, per i dettagli del file Tex, ecco l'[introduzione a Tex](https://docs.aspose.com/tex/cpp/what-is-tex/). Gli sviluppatori possono convertire facilmente TeX in formati PDF, XPS, PNG, JPG, BMP e TIFF integrando l'API per C++. Di seguito sono riportati alcuni esempi di codice che i programmatori possono migliorare e integrare all'interno delle soluzioni LaTex."
p2: "La soluzione API per Java qui ti consente di convertire file TeX e LaTeX in modo programmatico, ma potresti trovare utile vedere e provare [convertitori multipiattaforma](https://products.aspose.app/tex/conversion) sviluppati su questi nativi API. Lì puoi anche trovare [applications](https://products.aspose.app/tex/applications) per creare e modificare file TeX, tabelle, grafici, per unire file in formato PDF, ecc."
---

{{<section feature1>}}
---
title: "Converti LaTeX in Immagini, XPS, PDF, SVG C++."
h3: "Esempio di codice C++ Conversione da TeX a immagini, XPS, PDF o SVG."
item1: "L'API supporta BMP, JPEG, PDF, SVG, TIFF, XPS e PNG come formati di output. Per convertire i file TeX in immagini, PDF, XPS o SVG, procedi nei passaggi successivi:"
item2: "Crea un'istanza della [Classe TeXOptions](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options)."
item3: "Definisci il tipo e la dimensione dell'immagine utilizzando [*ImageDevice*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device)."
item4: "Specificare la directory di lavoro del file system per l'output/input utilizzando [*OutputWorkingDirectory*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)/[*InputWorkingDirectory*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)."
item5: "Inizializzare le opzioni per il salvataggio utilizzando [*BmpSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.bmp_save_options), [*PngSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.png_save_options), [*TiffSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.tiff_save_options), [*JpegSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.jpeg_save_options) o [*PdfSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_save_options), [*SvgSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_save_options), [*XpsSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_save_options), che è predefinito, non è necessario impostarlo."
item6: "Eseguire la conversione utilizzando il metodo Run di [*TeXJob()*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job) per [ImageDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device) o [PdfDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_device), [SvgDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_device), [XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device)."
item7: "Aspose.TeX per C++ funziona bene all'interno di qualsiasi ambiente di sviluppo che supporta C++, ma i requisiti successivi sono altamente consigliati:"
item8: Microsoft Visual Studio 2015 o versioni successive.
item9: Desktop di Microsoft Windows (7, 8, 10).
item10: Sistemi operativi server (2008, 2012), ecc.
item11: Sistemi Linux (Ubuntu-16.04 o successivo).
---


