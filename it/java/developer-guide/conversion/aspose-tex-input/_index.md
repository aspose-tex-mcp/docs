---
translation: true
template: /templates/_template-java.md
title: Asspose.Tex's Input Interface | Java
linktitle: Aspose.TeX's Input Interface
weight: 15
url: /java/aspose-tex-input/
description: Funzionalità di conversione della soluzione API ASPUS.TEX per Java con Tex, poiché un formato di input è spiegato qui con gli esempi di codice.
lastmod: "2025-06-13"
---

{{<section overview>}}

Si prega di fare riferimento a **Aspose.TeX per java** [riferimento API](https://reference.aspose.com/tex/java/com.aspose.tex/) per definizioni formali di implementazione I/O.

Gli esempi del file system e ZIP compongono `hello-world.tex` in `hello-world.xps`. Impostare `inputDirectory` su una cartella con il file TeX e `outputDirectory` su una cartella di output esistente. Per l’input ZIP, `inputZip` deve essere un `java.nio.file.Path` a un archivio contenente `in/hello-world.tex`. Importare le classi Aspose.TeX utilizzate nell’esempio scelto, `com.aspose.tex.rendering.XpsDevice` e le classi necessarie di `java.io` e `java.nio.file`. Il metodo chiamante deve gestire o dichiarare le eccezioni. Applicare una licenza come descritto nella [guida alle licenze](/tex/{{lang.url-fragment}}java/licensing/) per evitare le limitazioni della versione di valutazione.

## Il concetto della directory di input

Poiché i primitivi I/O della lingua tex possono solo affrontare i nomi dei file, **Aspose.TeX per Java** definisce una directory come una mappatura tra nomi e numeri di dati. I BUSI DEI DATI dovrebbero essere file, flussi, array o qualsiasi altra cosa. L'API ci consente di specificare separatamente le directory di lavoro input e output. Fornisce l'interfaccia generale [IinputworkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), che l'utente può implementare per i propri scopi. Fornisce inoltre le proprie implementazioni, che saranno discusse di seguito. L'interfaccia definisce il metodo [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-), che restituisce il flusso di dati e determina il nome completo del file, pur assumendo un po ', ipoteticamente diverso, il nome come il primo argomento, che, in effetti, è il tasto di mappatura.

### Ottenere l'input del file dal file system disco

Ecco come lo faremmo:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputFileSystemDirectory.java" >}}

Questo caso d'uso è abbastanza semplice, quindi non ci soffermeremo da molto tempo.

### Ottenere l'input di file da un archivio con zip

Possiamo anche mettere i file di input in un archivio ZIP e considerarlo una directory di input. In questo caso, dovremmo procedere come segue:

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputZipDirectory.java" >}}

Innanzitutto, creiamo il flusso contenente il file zip. Quindi, dopo aver creato le opzioni di conversione, impostiamo l'opzione [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getInputWorkingDirectory--) per essere un'istanza della classe [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/). Il secondo argomento del costruttore è il percorso di base all'interno dell'archivio. Se vogliamo che l'intero archivio sia una directory di input, dovremmo passare la stringa vuota. L’esempio mantiene aperti il flusso ZIP e la directory di input fino al termine del lavoro TeX, quindi li chiude. Viene eseguito senza interazione e acquisisce l’output del terminale in memoria.

## Il concetto del terminale di input

Ora ricordiamo che c'è anche l'input del terminale. Per quanto riguarda questo, **Aspose.TeX per java** definisce l'interfaccia generale [iinputterminal](https://reference.aspose.com/tex/java/com.aspose.tex/iinputterminal/) con due metodi. Uno di questi restituisce un'istanza [bufferedReader](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedReader.html). Un altro metodo restituisce un [inputstream](https://docs.oracle.com/javase/6/docs/api/java/io/InputStream.html) come flusso sottostante. Le implementazioni fornite dell'interfaccia sono discusse di seguito.

### Ottenere l'input del terminale dalla console

Per fare ciò, dobbiamo impostare l'opzione [Terminalin](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getTerminalIn--) per essere un'istanza della classe [InputConsoleterminal](https://reference.aspose.com/tex/java/com.aspose.tex/inputconsoleterminal/).

{{< gist "aspose-com-gists" "41e7e83784a6856ab3955f319608ef96" "Example-InputConsoleTerminal.java" >}}

`InputConsoleTerminal` è il valore predefinito di questa opzione. Questo esempio mostra solo la configurazione del terminale e non esegue un lavoro. Un lavoro che richiede input dal terminale necessita di dati dall’utente o di un’implementazione personalizzata del terminale. Gli esempi del file system e ZIP precedenti vengono eseguiti senza interazione con file di input completi.

Teoricamente, se abbiamo un file TEX interattivo (o script) con un comportamento prevedibile, potremmo voler implementare una versione del terminale di input che contiene uno script complementare per rispondere alle richieste del motore TEX. Prova la tua mano quando hai tempo!