---
translation: true
template: /templates/_template-java.md
linktitle: インストール
title: インストール| Java用のAspose.TeX
weight: 60
url: /java/installation/
description: JavaのAspose.TeX APIドキュメントは、ダウンロードされたZIPパッケージに記載されているか、単純な構成を備えたMavenプロジェクトから入手できます。
lastmod: "2026-04-21"
---

{{<section overview>}}

## Aspose.TeXのAspose Repositoryからのインストール

Asposeは、すべてのJava APIをAspose Repositoryにホストします。簡単な構成を使用して、MavenプロジェクトでJava APIにAspose.TeXを簡単に使用できます。

## Aspose Repository構成を指定します

まず、次のように、Maven pom.xmlのAspose Repository構成 /場所を指定する必要があります。


```
<repositories>
     <repository>
         <id>snapshots</id>
         <name>repo</name>
         <url>https://releases.aspose.com/java/repo/</url>
     </repository>
</repositories>
```

## Java API依存関係のAspose.TeXを定義します

次に、次のように、pom.xmlのJava API依存関係のAspose.TeXを定義します。

```
<dependencies>
    <dependency>
        <groupId>com.aspose</groupId>
        <artifactId>aspose-tex</artifactId>
        <version>21.4</version>
    </dependency>
</dependencies>
```

上記の手順を実行した後、Java依存関係のためのAspose.TeXがMavenプロジェクトで最終的に定義されます。