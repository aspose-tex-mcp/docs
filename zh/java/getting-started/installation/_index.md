---
translation: true
template: /templates/_template-java.md
linktitle: 安装
title: 安装 -  java的aspose.tex
weight: 60
url: /java/installation/
description: Aspose.TeX API文档的Java可以在下载的zip软件包中找到，也可以从具有简单配置的Maven项目中获取。
lastmod: "2025-06-10"
---

{{<section overview>}}

## 从Aspose存储库中安装Java的Aspose.TeX

Aspose在Aspose存储库上托管所有Java API。您可以在Maven项目中轻松地将Aspose.TeX用于Java API，并具有简单的配置。

## 指定aspose存储库配置

首先，您需要在maven pom.xml中指定ASPOSE存储库配置 /位置如下：


```
<repositories>
     <repository>
         <id>snapshots</id>
         <name>repo</name>
         <url>https://releases.aspose.com/java/repo/</url>
     </repository>
</repositories>
```

## 定义Java API依赖性的Aspose.TeX

然后在您的pom.xml中定义java api依赖性的aspose.tex如下：

```
<dependencies>
    <dependency>
        <groupId>com.aspose</groupId>
        <artifactId>aspose-tex</artifactId>
        <version>21.4</version>
    </dependency>
</dependencies>
```

执行以上步骤后，最终将在您的Maven项目中定义Java依赖性的Aspose.TeX。