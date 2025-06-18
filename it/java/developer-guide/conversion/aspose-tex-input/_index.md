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

Si prega di fare riferimento a **Aspose.TeX per java** [riferimento API](https://reference.aspose.com/tex/java/com.aspose.tex/package-frame) per definizioni formali di implementazione I/O.

## Il concetto della directory di input

Poiché i primitivi I/O della lingua tex possono solo affrontare i nomi dei file, **Aspose.TeX per Java** definisce una directory come una mappatura tra nomi e numeri di dati. I BUSI DEI DATI dovrebbero essere file, flussi, array o qualsiasi altra cosa. L'API ci consente di specificare separatamente le directory di lavoro input e output. Fornisce l'interfaccia generale [IinputworkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory), che l'utente può implementare per i propri scopi. Fornisce inoltre le proprie implementazioni, che saranno discusse di seguito. L'interfaccia definisce il metodo [getFile()](https://reference.aspose.com/tex/java/com.aspose.tex/IInputWorkingDirectory#getFile-java.lang.String-java.lang.String:A-boolean-), che restituisce il flusso di dati e determina il nome completo del file, pur assumendo un po ', ipoteticamente diverso, il nome come il primo argomento, che, in effetti, è il tasto di mappatura.

### Ottenere l'input del file dal file system disco

Ecco come lo faremmo:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-InputFileSystemDirectory.java" >}}

Questo caso d'uso è abbastanza semplice, quindi non ci soffermeremo da molto tempo.

### Ottenere l'input di file da un archivio con zip

Possiamo anche mettere i file di input in un archivio ZIP e considerarlo una directory di input. In questo caso, dovremmo procedere come segue:

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-InputZipDirectory.java" >}}

Innanzitutto, creiamo il flusso contenente il file zip. Quindi, dopo aver creato le opzioni di conversione, impostiamo l'opzione [InputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getInputWorkingDirectory--) per essere un'istanza della classe [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/InputZipDirectory). Il secondo argomento del costruttore è il percorso di base all'interno dell'archivio. Se vogliamo che l'intero archivio sia una directory di input, dovremmo passare la stringa vuota. 

## Il concetto del terminale di input

Ora ricordiamo che c'è anche l'input del terminale. Per quanto riguarda questo, **Aspose.TeX per java** definisce l'interfaccia generale [iinputterminal](https://reference.aspose.com/tex/java/com.aspose.tex/IInputTerminal) con due metodi. Uno di questi restituisce un'istanza [bufferedReader](https://docs.oracle.com/javase/6/docs/api/java/io/BufferedReader.html). Un altro metodo restituisce un [inputstream](https://docs.oracle.com/javase/6/docs/api/java/io/InputStream.html) come flusso sottostante. Le implementazioni fornite dell'interfaccia sono discusse di seguito.

### Ottenere l'input del terminale dalla console

Per fare ciò, dobbiamo impostare l'opzione [Terminalin](https://reference.aspose.com/tex/java/com.aspose.tex/TeXOptions#getTerminalIn--) per essere un'istanza della classe [InputConsoleterminal](https://reference.aspose.com/tex/java/com.aspose.tex/InputConsoleTerminal).

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-Conversion-InputConsoleTerminal.java" >}}

Ma, per dirti la verità, questo è il valore predefinito dell'opzione, quindi non è necessario specificarla. Per questo fatto, e fintanto che non ci sono altre implementazioni, questa sezione ha solo scopi dimostrativi.

Teoricamente, se abbiamo un file TEX interattivo (o script) con un comportamento prevedibile, potremmo voler implementare una versione del terminale di input che contiene uno script complementare per rispondere alle richieste del motore TEX. Prova la tua mano quando hai tempo!