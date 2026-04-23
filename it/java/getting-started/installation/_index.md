---
translation: true
template: /templates/_template-java.md
linktitle: Installazione
title: Installazione | Aspose.TeX per Java
weight: 60
url: /java/installation/
description: Aspose.TeX Documentazione API per Java è disponibile nel pacchetto Zip scaricato o ottenuto da progetti Maven con semplici configurazioni.
lastmod: "2026-04-21"
---

{{<section overview>}}

## Installazione di Aspose.TeX per java dal repository Aspose

Aspose ospita tutte le API Java nel repository Aspose. È possibile utilizzare facilmente Aspose.TeX per Java direttamente nei progetti Maven con semplici configurazioni.

## Specificare la configurazione del repository Aspose

Innanzitutto, è necessario specificare la configurazione / posizione del repository Aspose in Maven Pom.xml come segue:


```
<repositories>
     <repository>
         <id>snapshots</id>
         <name>repo</name>
         <url>https://releases.aspose.com/java/repo/</url>
     </repository>
</repositories>
```

## Definisci Aspose.TeX per la dipendenza dall'API Java

Quindi definisci Aspose.TeX per la dipendenza dall'API Java nel tuo pom.xml come segue:

```
<dependencies>
    <dependency>
        <groupId>com.aspose</groupId>
        <artifactId>aspose-tex</artifactId>
        <version>21.4</version>
    </dependency>
</dependencies>
```

Dopo aver eseguito i passaggi sopra, Aspose.TeX per la dipendenza Java sarà finalmente definito nel progetto Maven.