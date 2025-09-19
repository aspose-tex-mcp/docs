---
translation: true
template: /templates/_template-java.md
linktitle: Licenze
title: Licensing | Aspose.TeX per Java
weight: 70
url: /java/licensing/
description: Quando ti sei fermato sulla versione autorizzata della soluzione API Aspose.Tex per Java qui scopri come applicare la licenza.
lastmod: "2025-06-13"
---

{{<section overview>}}


### Limitazioni della versione di valutazione

La versione di valutazione di Aspose.Tex (senza una licenza specificata) fornisce funzionalità complete del prodotto, tranne per il fatto che solo fino a quattro prime pagine possono essere ottenute nel documento di output. Inoltre, quelle pagine saranno timbrate con una filigrana in modalità di valutazione.

Se si desidera provare Aspose.Tex senza limitazioni di valutazione, richiedi una licenza temporanea di 30 giorni. Si prega di fare riferimento a [Come ottenere una licenza temporanea?](https://purchase.aspose.com/temporary-license/) Per ulteriori informazioni.

### Applicare la licenza utilizzando il file o lo streaming oggetto

Utilizzare il metodo [Licenza.setLicense](https://reference.aspose.com/tex/java/com.aspose.tex/License#setLicense-java.lang.String-) per licenza il componente. Il modo più semplice per impostare una licenza è mettere il file di licenza nella stessa cartella del * aspose.tex.jar * e specificare il nome file, senza percorso, come mostrato di seguito.

#### Caricamento di una licenza dal file

Questo frammento di codice inizializza una licenza memorizzata in un file o in una risorsa incorporata.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-LoadLicenseFromFile.java" >}}

#### Caricamento di una licenza da un oggetto Stream

Questi frammenti di codice inizializzano la licenza dal flusso.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-LoadLicenseFromStream.java" >}}

### Licenza misurata

Aspose.TeX ha un meccanismo di licenza alternativo chiamato *licenza misurata *. Se un cliente desidera essere fatturato in base all'utilizzo delle funzionalità API, può applicare una *licenza misurata *, che in realtà è semplice come applicare una coppia di chiavi crittografiche. Per maggiori dettagli, consultare la sezione [FAQ di licenze misurate](https://purchase.aspose.com/faqs/licensing/metered/).

Le chiavi pubbliche e private di una licenza misurata possono essere impostate utilizzando un'istanza della classe [*misurata*](https://reference.aspose.com/tex/net/aspose.tex/metered/), come mostrato di seguito: 

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-SetMeteredLicense.java" >}}