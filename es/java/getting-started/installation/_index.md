---
translation: true
template: /templates/_template-java.md
linktitle: Instalación
title: Instalación | Aspose.TeX para Java
weight: 60
url: /java/installation/
description: La documentación de la API de Aspose.TeX para Java se puede encontrar en el paquete ZIP descargado o se puede obtener de Proyectos Maven.
lastmod: "2024-10-30"
---

{{<section overview>}}

## Instalación de Aspose.TeX para Java desde el repositorio Aspose

Aspose aloja todas las API de Java en el repositorio Aspose. Puede utilizar fácilmente Aspose.TeX para Java API directamente en sus proyectos Maven con configuraciones simples.

## Especificar la configuración del repositorio Aspose

Primero, debe especificar la configuración/ubicación del repositorio Aspose en su Maven pom.xml de la siguiente manera:


```
<repositories>
     <repository>
         <id>snapshots</id>
         <name>repo</name>
         <url>https://releases.aspose.com/java/repo/</url>
     </repository>
</repositories>
```

## Definir Aspose.TeX para la dependencia de la API de Java

Luego defina Aspose.TeX para la dependencia de la API de Java en su pom.xml de la siguiente manera:

```
<dependencies>
    <dependency>
        <groupId>com.aspose</groupId>
        <artifactId>aspose-tex</artifactId>
        <version>21.4</version>
    </dependency>
</dependencies>
```

Después de realizar los pasos anteriores, la dependencia de Aspose.TeX para Java finalmente se definirá en su proyecto Maven.