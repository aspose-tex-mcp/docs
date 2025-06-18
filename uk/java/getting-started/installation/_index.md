---
translation: true
template: /templates/_template-java.md
linktitle: Установка 
title: Встановлення - Aspose.TeX для Java
weight: 60
url: /java/installation/
description: Документацію Aspose.TeX API для Java можна знайти в завантаженому пакеті ZIP або отримати з Maven Projects із простими налаштуваннями.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Встановлення Aspose.TeX для Java зі сховища Aspose

Aspose розміщує всі API Java у репозиторії Aspose. Ви можете легко використовувати Aspose.TeX для Java API безпосередньо у своїх проектах Maven за допомогою простих конфігурацій.

## Укажіть конфігурацію сховища Aspose

По-перше, вам потрібно вказати конфігурацію/розташування Aspose Repository у вашому Maven pom.xml наступним чином:


```
<repositories>
     <repository>
         <id>snapshots</id>
         <name>repo</name>
         <url>https://releases.aspose.com/java/repo/</url>
     </repository>
</repositories>
```

## Визначте залежність Aspose.TeX для Java API

Потім визначте залежність Aspose.TeX для Java API у вашому pom.xml наступним чином:

```
<dependencies>
    <dependency>
        <groupId>com.aspose</groupId>
        <artifactId>aspose-tex</artifactId>
        <version>21.4</version>
    </dependency>
</dependencies>
```

Після виконання наведених вище кроків залежність Aspose.TeX для Java буде остаточно визначена у вашому проекті Maven.