---
translation: true
template: /templates/_template-python-net.md
title: Funzionalità di conversione | Aspose.TeX per Python tramite .NET
linktitle: Conversione
weight: 10
url: /python-net/conversion/
description: Funzionalità di conversione della soluzione API ASPUS.TEX per Python supporta i successivi formati di output Tex, XPS, PDF, PNG, JPEG, TIFF e PNG.
lastmod: "2025-06-13"
---

{{<section overview>}}

Se in precedenza hai esaminato il contenuto in ["Introduzione a Texs"](/tex/{{lang.url-fragment}}net/introduction-to-tex/), potresti aver notato che i termini * converti * e * conversione * non sono del tutto adatti nel contesto di Tex, poiché il processo di composizione di un file Tex non coinvolge la mappatura da un formato all'altro. Tuttavia, in linea con la tradizione e le preferenze dell'utente, consentiamo l'uso di questi termini e, in questa parte, li useremo quando sono più adatti. Inoltre, occasionalmente possiamo anche impiegare le parole *trasformazione* e *trasformazione*.

I capitoli di questa parte forniranno una procedura dettagliata delle capacità di conversione di **Aspose.TeX per Python**, a partire dagli scenari di base di utilizzo per i formati di output più comunemente usati e concludendo con opzioni di personalizzazione avanzate. Considerando la prevalenza di [file latex](/tex/{{lang.url-fragment}}net/latex-io/#latex-file) rispetto ad altri formati TEX, ci concentreremo sulla discussione della conversione dei file LaTeX anziché sulla discussione dei file TEX. Tuttavia, toccheremo brevemente la conversione dei file tex più tardi.

Vale la pena ricordare che il supporto in LaTeX di Aspose.Tex comprende tutti i file del sistema in LaTeX di base e i file dei [pacchetti più comuni](/tex/{{lang.url-fragment}}net/embedded-packages/), tra cui `amsmath`,` geometry`, `graphics` e altri. Nella maggior parte dei casi, se si verifica un errore relativo a un pacchetto mancante, la tua situazione è leggermente più complessa dello scenario più semplice. [Qui](/tex/{{lang.url-fragment}}python-net/latex-to-image/#regarding-input-options), forniamo un suggerimento verso la soluzione.