---
translation: true
template: /templates/_template-cpp.md
title: Altri modi per fornire il principale file di input Tex | C ++
linktitle: Altri modi per fornire il principale file di input Tex
weight: 14
url: /cpp/other-ways-of-main-input/
description: La funzionalità di conversione della soluzione API ASPUS.TEX per C ++ ha un costruttore che accetta un flusso come primo argomento. Ecco alcuni esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Fornire il file di input principale al motore TEX come flusso

Fino a questo punto, sapevamo solo come passare il [file di input principale](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) al motore TEX come nome di un file, sia completamente specificato che in breve, sia con un'estensione che senza di essa. Ma c'è un altro [costruttore](https://reference.aspose.com/tex/cpp/aspose.tex/texjob/) della classe `Texjob`, che prende un flusso come primo argomento. Questo è conveniente se per qualche motivo abbiamo il file di input principale in un modulo diverso da un file sul file system disco. Ecco come può essere implementato:

```C++
// Create conversion options instance.
...
// Create some device.
...
// Run LaTeX to XPS conversion.
System::MakeObject<Aspose::TeX::TeXJob>(System::MakeObject<System::IO::MemoryStream>(System::Text::Encoding::get_ASCII()->GetBytes(
    u"\\documentclass{article} \\begin{document} Hello, World! \\end{document}")), device, options)->Run();


```

Si noti che tutti i file di output avranno il nome *texput*. Questo perché il motore non può ottenere nessun altro nome da nessuna parte. *texput* è il nome del lavoro predefinito. [Qui](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) e [qui](/tex/{{lang.url-fragment}}cpp/other-options/#how-to-set-the-job-name) sono dettagli sui nomi dei lavori.

## Immettere il file di input tex principale dal terminale

C'è ancora un altro [costruttore](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job/main) della classe `Texjob`, che non ci consente affatto di specificare l'input. Allora, cosa sta per elaborare un lavoro del genere, potresti chiederti? Questa volta avremo bisogno di un terminale di input. Il motore Tex ci chiederà di inserire il nome del file dal terminale.

Ecco il codice:

```C++
// Create conversion options instance.
...
// Run LaTeX to XPS conversion.
System::MakeObject<Aspose::TeX::TeXJob>(System::MakeObject<XpsDevice>(), options)->Run();


```

Non appena viene eseguito, il motore si attacca, aspettando che inseriamo il nome del file (con o senza percorso, con o senza estensione):


![Finestra terminale](/tex/images/cpp/Conversion-MainInputTerminal.png)

Ed è così che sembrerebbe sul terminale di uscita che è la console:

```text
This is ObjectTeX, Version 3.1415926-1.0 (Aspose.TeX 21.8)
entering extended mode
**<path_to_the_file>/hello-world.ltx
(<path_to_the_file>/hello-world.ltx
LaTeX2e <2011/06/27>
(article.cls
Document Class: article 2007/10/19 v1.4h Standard LaTeX document class
(size10.clo))
No file hello-world.aux.
[1]
(<output_directory>\hello-world.aux) )
Output written on hello-world.xps (1 page).
Transcript written on hello-world.log.
```