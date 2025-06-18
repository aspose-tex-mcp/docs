---
translation: true
template: /templates/_template-cpp.md
title: Altri formati di output di conversione Tex | C ++
linktitle: Altri formati di Tex
weight: 18
url: /cpp/other-tex-formats/
description: La funzionalità di conversione della soluzione API ASPUS.TEX per C ++ consente di convertire i file in LaTeX e i tuoi file TEX personalizzati. Ecco alcuni esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}

È altamente improbabile che tu voglia attualmente convertire un file Tex scritto in qualsiasi altro formato rispetto a LaTex. Ma questo è possibile se stai studiando la lingua Tex e/o gli interni per qualche motivo. Comunque, **Aspose.TeX per C ++** ti consente di convertire i file scritti in un semplice formato Tex. Inoltre, consente di creare formati personalizzati e documenti di composizione progettati in questi formati.

Inizieremo con la creazione di un formato personalizzato.

## Creazione di un formato personalizzato

Ricordiamo che il file di formato è una dump binaria dello stato interno del motore Tex.

```C++
// Create typesetting options for no format on ObjectTeX engine extension.
System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectIniTeX());
// Specify a file system working directory for input.
options->set_InputWorkingDirectory(System::MakeObject<InputFileSystemDirectory>(RunExamples::InputDirectory));
// Specify a file system working directory for output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
    
// Run format creation.
Aspose::TeX::TeXJob::CreateFormat(u"customtex", options);
    
// For further output to look write.
options->get_TerminalOut()->get_Writer()->WriteLine();
```
Come puoi vedere, il codice è simile al codice per la conversione di un file Tex. Ma ci sono alcune differenze.

Innanzitutto, qui utilizziamo la configurazione del lavoro [TexConfig.ObjectInitex](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_config#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e). Questa è una configurazione speciale che lascia lo stato del motore "vergine", ovvero i parametri interni hanno i loro valori predefiniti e l'insieme di sequenze di controllo coincide con l'insieme di primitive. Nel nostro esempio, l'insieme di primitive è esteso nel senso menzionato [qui](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

Successivamente, impostiamo le directory di lavoro input e output come al solito. La directory di lavoro input deve contenere il file di origine del formato principale e tutte le sue dipendenze.

E la seconda differenza chiave è il modo in cui gestiamo il lavoro. Questa volta utilizziamo il metodo statico [createFormat()](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/), che insieme alle opzioni prende il nome del file di origine principale, che deve essere uguale al nome del formato.

## Compromettere un file tex nel tuo formato personalizzato

Ora che abbiamo il nostro formato tex, vogliamo scrivere un file Tex scritto in questo formato. Ecco il codice:

```C++
// Create typesetting options for a custom format on ObjectTeX engine extension.
System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::ObjectTeX(formatProvider));
options->set_JobName(u"typeset-with-custom-format");
// Specify the input working directory.
options->set_InputWorkingDirectory(wd);
// Specify a file system working directory for output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
            
// Run typesetting.
System::MakeObject<Aspose::TeX::TeXJob>(System::MakeObject<System::IO::MemoryStream>(System::Text::Encoding::get_ASCII()->GetBytes(u"Congratulations! You have successfully typeset this text with your own TeX format!\\end")), System::MakeObject<XpsDevice>(), options)->Run();
            
// For further output to look write.
options->get_TerminalOut()->get_Writer()->WriteLine();
```
Ovviamente, dobbiamo in qualche modo specificare il formato. Prima di tutto, dobbiamo creare un'istanza della classe [FormatProvider](https://reference.aspose.com/tex/cpp/class/aspose.te_x.resource_providers.format_provider). Quindi, nel costruttore di opzioni, utilizziamo la configurazione [TexConfig.objectx()](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_config#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e), che prende il nostro fornitore di formato come argomento e carica il formato in cima allo stato "vergine" del motore.

Il resto del codice dovrebbe essere familiare a te. Utilizza le funzionalità discusse in precedenza in questa [guida](/tex/{{lang.url-fragment}}cpp/conversion/).

## Testa di un file tex in un formato Tex semplice

Se gettiamo via il provider di formato dal codice appena dimostrato, il motore caricherà il formato predefinito, che è [Object Tex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) nel suo quarto senso. Pertanto, se hai un file Tex scritto in un semplice formato Tex, in questo modo puoi convertirlo in qualsiasi formato target supportato.