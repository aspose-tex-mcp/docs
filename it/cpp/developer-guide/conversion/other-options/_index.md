---
translation: true
template: /templates/_template-cpp.md
title: Altre opzioni di gestione Tex | C ++
linktitle: Altre opzioni
weight: 17
url: /cpp/other-options/
description: Funzionalità di conversione della soluzione API ASUP.TEX per C ++ consente di impostare la modalità di interazione iniziale in cui inizia il motore. Ecco alcuni esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Come impostare la modalità di interazione

Come abbiamo detto [qui](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes), **Aspose.TeX per C ++** ci consente di impostare la modalità di interazione iniziale in cui si avvia il motore. Ecco come lo facciamo:

```C++
// Create conversion options instance.
...
// Set the interaction mode.
options->set_Interaction(Interaction::NonstopMode);
```

## Come impostare il nome del lavoro

Quando passiamo il file di input principale come nome di un file, otteniamo file di output con lo stesso nome, sebbene con altre estensioni. Il motore Tex chiama il nome del file di input il *nome del lavoro* e lo utilizza per i file di output, tranne nei casi in cui vengono scritti file ausiliari con altri nomi esplicitamente specificati. Quando passiamo il file di input principale come [stream](/tex/{{lang.url-fragment}}cpp/other-ways-of-main-input/#providing-the-main-input-file-as-a-stream), il motore Tex utilizza il nome del lavoro predefinito, che è *texput*.
In entrambi i casi, possiamo sovrascrivere il nome del lavoro assegnando l'opzione di conversione appropriata.

```C++
// Create conversion options instance.
...
// Set the job name.
options->set_JobName(u"my-job-name");
```
## Come ripetere il lavoro

Come abbiamo detto [sopra](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) per quanto riguarda etichette e riferimenti, ci sono casi in cui vorremmo eseguire lo stesso lavoro due volte. Ecco come può essere fatto:
```C++
// Create conversion options instance.
...
// Set the job name.
options->set_Repeat(true);
```