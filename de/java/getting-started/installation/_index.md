---
translation: true
template: /templates/_template-java.md
linktitle: Installation
title: Installation - Aspose.TeX für Java
weight: 60
url: /java/installation/
description: Die Aspose.TeX-API für Java kann im heruntergeladenen ZIP-Paket gefunden oder mit einfachen Konfigurationen von Maven Projects bezogen werden.
lastmod: "2024-09-26"
---

{{<section overview>}}

## Installieren von Aspose.TeX für Java aus dem Aspose Repository

Aspose hostet alle Java-APIs im Aspose Repository. Mit einfachen Konfigurationen können Sie Aspose.TeX für Java API problemlos direkt in Ihren Maven-Projekten verwenden.

## Geben Sie die Aspose-Repository-Konfiguration an

Zuerst müssen Sie die Konfiguration/den Speicherort des Aspose-Repositorys in Ihrer Maven pom.xml wie folgt angeben:


```
<repositories>
     <repository>
         <id>snapshots</id>
         <name>repo</name>
         <url>https://releases.aspose.com/java/repo/</url>
     </repository>
</repositories>
```

## Definieren Sie Aspose.TeX für die Java-API-Abhängigkeit

Definieren Sie dann Aspose.TeX für die Java-API-Abhängigkeit in Ihrer pom.xml wie folgt:

```
<dependencies>
    <dependency>
        <groupId>com.aspose</groupId>
        <artifactId>aspose-tex</artifactId>
        <version>21.4</version>
    </dependency>
</dependencies>
```

Nachdem Sie die oben genannten Schritte ausgeführt haben, wird die Abhängigkeit von Aspose.TeX für Java schließlich in Ihrem Maven-Projekt definiert.