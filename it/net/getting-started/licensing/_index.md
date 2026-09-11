---
translation: true
template: /templates/_template-net.md
linktitle: Licenze
title: Licensing | Aspose.TeX per .NET
weight: 70
url: /net/licensing/
description: Quando ti sei fermato sulla versione autorizzata della soluzione API Aspose.TeX per .NET qui scopri come applicare la licenza.
lastmod: "2026-04-22"
---

{{<section overview>}}

## Valuta Aspose.TeX

È possibile scaricare facilmente Aspose.TeX per il prodotto .NET per scopi di valutazione. Fare riferimento alla pagina [Aspose.TeX per .NET Pagina di download](https://www.nuget.org/packages/Aspose.TeX/) per scoprire l'ultima versione. Il download di valutazione è uguale al download acquistato. La versione di valutazione viene semplicemente autorizzata quando si aggiungono alcune righe di codice per applicare la licenza.

### Limitazioni della versione di valutazione

La versione di valutazione di Aspose.TeX (senza una licenza specificata) fornisce funzionalità complete del prodotto, tranne per il fatto che solo fino a quattro prime pagine possono essere ottenute nel documento di output. Inoltre, quelle pagine saranno timbrate con una filigrana in modalità di valutazione.

Se si desidera provare Aspose.TeX senza limitazioni di valutazione, richiedi una licenza temporanea di 30 giorni. Si prega di fare riferimento a [Come ottenere una licenza temporanea?](https://purchase.aspose.com/temporary-license/) Per ulteriori informazioni.

## Applicazione di una licenza

Una volta che sei soddisfatto della valutazione di Aspose.TeX per .NET, acquista una licenza sul sito Web ASPE: [Portale di acquisto](https://purchase.aspose.com/pricing?). Affrontare i diversi tipi di licenza disponibili. Se hai domande, [contatta il team di vendita aspirato](https://consulting.aspose.com/) e saranno felici di aiutarti.

Ogni licenza in aspirazione porta un abbonamento di un anno per aggiornamenti gratuiti a qualsiasi nuova versioni o correzioni che si verificano durante questo periodo. Forniamo supporto tecnico gratuito e illimitato per gli utenti autorizzati e di valutazione.

La licenza è un file XML di testo semplice che contiene dettagli come il nome del prodotto, il numero di sviluppatori autorizzati, la data di scadenza dell'abbonamento e così via. Il file è firmato digitalmente, quindi non modificare il file: anche l'aggiunta di una rottura della riga extra al file lo invalida.

### Quando applicare una licenza

Segui queste semplici regole:

- La licenza deve essere impostata solo una volta per dominio dell'applicazione.
- È necessario impostare la licenza prima di utilizzare qualsiasi altra classe Aspose.TeX.
- Chiamare SetLicense più volte non è dannoso, ma perde il tempo del processore.
- Se si sta sviluppando un modulo di Windows o un'applicazione console, chiamare SetLicense nel codice di avvio, prima di utilizzare le classi Aspose.TeX.
- Quando si sviluppa un'applicazione ASP.NET, chiamare SetLicense dal file global.asax.cs, nel metodo protetto Application_Start. Si chiama una volta quando l'applicazione inizia.
- Non chiamare SetLicense dai metodi Page_Load poiché significa che la licenza verrà caricata ogni volta che viene caricata una pagina Web.
- Se stai sviluppando una libreria di classe, puoi chiamare SetLicense da un costruttore statico della classe che utilizza Aspose.TeX. Il costruttore statico esegue prima che venga creata un'istanza della classe assicurando che la licenza Aspose.TeX sia impostata correttamente.

### Applicare la licenza utilizzando il file o lo streaming oggetto

Utilizzare il metodo [Licenza.SetLicense](https://reference.aspose.com/tex/net/aspose.tex/license/) per licenza il componente. Il modo più semplice per impostare una licenza è mettere il file di licenza nella stessa cartella di *Aspose.TeX.dll* e specificare il nome file, senza percorso, come mostrato di seguito.

#### Caricamento di una licenza dal file

Questo frammento di codice inizializza una licenza memorizzata in un file o in una risorsa incorporata.

{{< gist "aspose-com-gists" "366cba3dc08d43c99c22bb33ecb5d555" "Example-SetLicenseFromFile.cs" >}}

#### Caricamento di una licenza da un oggetto Stream

Questi frammenti di codice inizializzano la licenza dal flusso.

{{< gist "aspose-com-gists" "366cba3dc08d43c99c22bb33ecb5d555" "Example-SetLicenseFromStream.cs" >}}

### Licenza misurata
Aspose.TeX ha un meccanismo di licenza alternativo. Quei clienti che desiderano essere fatturati in base all'utilizzo delle funzionalità API possono utilizzare *licenze misurate *. L'applicazione di una * patente misurata * è in realtà semplice come applicare una coppia di chiavi crittografiche. Per maggiori dettagli, consultare la sezione [FAQ di licenza misurata](https://purchase.aspose.com/faqs/licensing/metered/).

Le chiavi pubbliche e private di una licenza misurata sono impostate utilizzando un'istanza della classe [*misurata*](https://reference.aspose.com/tex/net/aspose.tex/metered/), come mostrato nell'esempio seguente: 

{{< gist "aspose-com-gists" "366cba3dc08d43c99c22bb33ecb5d555" "Example-SetMeteredLicense.cs" >}}
