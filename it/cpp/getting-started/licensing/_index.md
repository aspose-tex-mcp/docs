---
translation: true
template: /templates/_template-cpp.md
title: Licensing | Aspose.TeX per C++
linktitle: Licenze
weight: 70
url: /cpp/licensing/
description: Quando ti sei fermato sulla versione autorizzata della soluzione API Aspose.TeX per C ++ qui scopri come applicare la licenza.
lastmod: "2026-04-20"
---

{{<section overview>}}

## Valuta Aspose.TeX

È possibile scaricare facilmente Aspose.Tex per il prodotto C ++ per scopi di valutazione. Fare riferimento alla pagina di download [Aspose.Tex per C ++](https://www.nuget.org/packages/Aspose.TeX.Cpp/) per scoprire l'ultima versione. Il download di valutazione è uguale al download acquistato. La versione di valutazione viene semplicemente autorizzata quando si aggiungono alcune righe di codice per applicare la licenza.

### Limitazioni della versione di valutazione

La versione di valutazione di Aspose.Tex (senza una licenza specificata) fornisce funzionalità complete del prodotto, tranne per il fatto che solo fino a quattro prime pagine possono essere ottenute nel documento di output. Inoltre, quelle pagine saranno timbrate con una filigrana in modalità di valutazione.

Se si desidera provare Aspose.Tex senza limitazioni di valutazione, richiedi una licenza temporanea di 30 giorni. Si prega di fare riferimento a [Come ottenere una licenza temporanea?](https://purchase.aspose.com/temporary-license/) Per ulteriori informazioni.

## Applicazione di una licenza

Una volta che sei soddisfatto della valutazione di Aspose.Tex per C ++, acquista una licenza sul sito Web ASPE: [Portale di acquisto](http://www.aspose.com/purchase/default.aspx). Affrontare i diversi tipi di licenza disponibili. Se hai domande, [contatta il team di vendita aspirato](http://www.aspose.com/corporate/contact/default.aspx) e saranno felici di aiutarti.

Ogni licenza in aspirazione porta un abbonamento di un anno per aggiornamenti gratuiti a qualsiasi nuova versioni o correzioni che si verificano durante questo periodo. Forniamo supporto tecnico gratuito e illimitato per gli utenti autorizzati e di valutazione.

La licenza è un file XML di testo semplice che contiene dettagli come il nome del prodotto, il numero di sviluppatori autorizzati, la data di scadenza dell'abbonamento e così via. Il file è firmato digitalmente, quindi non modificare il file: anche l'aggiunta di una rottura della riga extra al file lo invalida.

### Quando applicare una licenza

Segui queste semplici regole:

- La licenza deve essere impostata solo una volta per dominio dell'applicazione.
- È necessario impostare la licenza prima di utilizzare qualsiasi altra aspira :: Classi tex.
- Chiamare setLicense più volte non è dannoso, ma perde il tempo del processore.
- Se si sta sviluppando un'applicazione, chiama setLicense nel codice di avvio, prima di utilizzare le classi ASPUS :: Tex.
- Se stai sviluppando una libreria di classe, puoi chiamare setLicense da un costruttore statico della classe che utilizza Aspose :: Tex. Il costruttore statico esegue prima che venga creata un'istanza della tua classe assicurando che la licenza ASPUTI :: TEX sia impostata correttamente.

### Applicare la licenza utilizzando il file o lo streaming oggetto

Utilizzare il metodo [Licenza :: SetLicense](https://reference.aspose.com/tex/cpp/aspose.tex/license/) per la licenza del componente. Il modo più semplice per impostare una licenza è mettere il file di licenza nella stessa cartella di Aspose.TeX.dll e specificare il nome file, senza un percorso, come mostrato di seguito.

#### Caricamento di una licenza dal file

Questo frammento di codice inizializza una licenza memorizzata in un file o in una risorsa incorporata.

{{< gist "aspose-com-gists" "d3eef38ac5b929503e8edee25e0873ce" "Aspose.TeX.Examples-LoadLicenseFromFile.cpp" >}}

#### Caricamento di una licenza da un oggetto Stream

Questi frammenti di codice inizializzano la licenza dal flusso.

{{< gist "aspose-com-gists" "d3eef38ac5b929503e8edee25e0873ce" "Aspose.TeX.Examples-LoadLicenseFromStream.cpp" >}}