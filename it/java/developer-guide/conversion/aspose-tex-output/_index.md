---
translation: true
template: /templates/_template-java.md
title: Aspose.TeX's Output Interface | Java
linktitle: Aspose.TeX's Output Interface
weight: 16
url: /java/aspose-tex-output/
description: Funzionalità di conversione della soluzione API ASPUS.TEX per Java con Tex, poiché un formato di output viene spiegato qui con gli esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}

Si prega di fare riferimento a **Aspose.TeX per java** [riferimento API](https://reference.aspose.com/tex/java/com.aspose.tex/) per definizioni formali di implementazione I/O.

## Il concetto della directory di output

Poiché i primitivi I/O della lingua tex possono solo affrontare i nomi dei file, Aspose.Tex definisce una directory come una mappatura tra nomi e numeri di dati. I BUSI DEI DATI dovrebbero essere file, flussi, array o qualsiasi altra cosa. L'API ci consente di specificare separatamente le directory di lavoro input e output. Fornisce l'interfaccia generale [IoutputworkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/) per l'output, che l'utente può implementare per i propri scopi. Fornisce inoltre le proprie implementazioni, che saranno discusse di seguito. L'interfaccia estende [IinputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), poiché il motore può prima creare e scrivere un file, quindi riatterlo. Il metodo dell'interfaccia [getouputfile()](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputworkingdirectory/#getOutputFile-java.lang.String-java.lang.String:A-) restituisce il flusso in cui scrivere, al contrario del flusso da leggere restituito da [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-).

### Scrivere l'output di file sul file system disco

Come accennato [sopra](/tex/{{lang.url-fragment}}/java/conversion/), il valore più comune per la [outputworkingdirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) sarebbe probabilmente un'istanza della classe [OutputFilesystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputfilesystemdirectory/).

Ecco come lo imposteremmo:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputFileSystemDirectory.java" >}}

Questo caso d'uso è abbastanza semplice, quindi non ci soffermeremo da molto tempo.

### Scrivere l'output di file in un archivio zip

Possiamo anche creare un file (o streaming) e lasciare che il motore TEX lo utilizzi come archivio zip per archiviare i file di output. Ecco qui:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputZipDirectory.java" >}}

Innanzitutto, creiamo un flusso di output per il file zip. Quindi, dopo aver creato le opzioni di conversione, impostiamo l'opzione [OutputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getOutputWorkingDirectory--) per essere un'istanza della classe [OutputzipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/outputzipdirectory/).

## Il concetto del terminale di output

C'è un'altra parte importante dell'uscita --- l'output del terminale. Per quanto riguarda questo, **Aspose.TeX per java** definisce l'interfaccia generale [IoutPutterminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/) (11) con due metodi. Uno di questi restituisce un'istanza [bufferedwriter](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedWriter.html). Un altro restituisce un'istanza [outputstream](https://docs.oracle.com/javase/6/docs/api/java/io/OutputStream.html) come flusso sottostante. Le implementazioni fornite dell'interfaccia sono discusse di seguito.

### Scrivere l'output del terminale sulla console

Per fare ciò, dobbiamo impostare l'opzione [terminale](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalOut--) per essere un'istanza della classe [outputConsoleterminal](https://reference.aspose.com/tex/java/com.aspose.tex/outputconsoleterminal/).

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputConsoleTerminal.java" >}}

Ancora una volta, questo è il valore predefinito dell'opzione, quindi non è necessario specificarlo. Per questo motivo, questa sezione ha solo scopi dimostrativi.

### Scrivere l'output del terminale in un file

A differenza del terminale di input, **Aspose.TeX per java** fornisce un'implementazione di [IoutPutterminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/), che ci consente di scrivere l'output del terminale in un file in una directory di output.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-OutputFileTerminal.java" >}} 

Qui chiediamo al motore TEX di scrivere l'output del terminale nel file con il nome [<job_name>](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) .trm, che verrà archiviato nella stessa directory di output che abbiamo specificato per il resto dell'output. Ma questo non è necessario. Potremmo anche passare qualsiasi altra istanza di qualsiasi implementazione di [IoutPutterminal](https://reference.aspose.com/tex/java/com.aspose.tex/ioutputterminal/) al costruttore.