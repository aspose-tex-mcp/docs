---
translation: true
template: /templates/_template-java.md
linktitle: Установка
title: Установка - Aspose.TeX для Java
weight: 60
url: /java/installation/
description: Документацию по API Aspose.TeX для Java можно найти в загруженном ZIP-пакете или получить из проектов Maven с помощью простых конфигураций.
lastmod: "2024-09-24"
---

{{<section overview>}}

## Установка Aspose.TeX для Java из репозитория Aspose

Aspose размещает все API Java в репозитории Aspose. Вы можете легко использовать Aspose.TeX для Java API непосредственно в своих проектах Maven с помощью простых конфигураций.

## Укажите конфигурацию репозитория Aspose

Во-первых, вам необходимо указать конфигурацию/расположение репозитория Aspose в вашем Maven pom.xml следующим образом:


```
<repositories>
     <repository>
         <id>snapshots</id>
         <name>repo</name>
         <url>https://releases.aspose.com/java/repo/</url>
     </repository>
</repositories>
```

## Определите Aspose.TeX для зависимости Java API

Затем определите зависимость Aspose.TeX для Java API в вашем pom.xml следующим образом:

```
<dependencies>
    <dependency>
        <groupId>com.aspose</groupId>
        <artifactId>aspose-tex</artifactId>
        <version>21.4</version>
    </dependency>
</dependencies>
```

После выполнения вышеуказанных шагов зависимость Aspose.TeX для Java будет окончательно определена в вашем проекте Maven.