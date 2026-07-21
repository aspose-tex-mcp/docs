---
translation: true
template: /templates/_template-python-net.md
title: その他のTEX変換出力形式| .NET経由でPython用のAspose.TeX
linktitle: その他のTEX形式
weight: 18
url: /python-net/other-tex-formats/
description: Python用のAspose.TeX APIソリューションは、LaTexファイルとカスタムTEXファイルを変換できる機能を提供します。ここにいくつかのコード例があります。
lastmod: "2025-06-09"
---

{{<section overview>}}

現在、LaTex以外の形式で記述されたTEXファイルを変換する必要がある可能性は低いです。ただし、何らかの理由でTex LanguageまたはTexの内部を勉強している場合、それはまだ可能です。いずれにせよ、**pythonのAspose.TeX**を使用すると、*plane tex*形式で記述されたファイルを変換できます。また、これらの形式で設計されたカスタム形式と型文書を作成することもできます。

まず、カスタム形式を作成します。

## カスタム形式の作成

フォーマットファイルは、TEXエンジンの内部状態のバイナリ表現であることに留意してください。

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-CreateCustomTeXFormatFile.py" >}}

ご覧のとおり、コードはTEXファイルを変換するためのコードに似ています。ただし、いくつかの区別があります。

まず、この場合、[texconfig.object_ini_tex](https://reference.aspose.com/tex/python-net/Aspose.TeX/texconfig/object_ini_tex/)ジョブ構成を利用します。この構成により、エンジンの状態が「バージン」であることが保証されます。つまり、内部パラメーターにはデフォルト値があり、制御シーケンスのセットがプリミティブのセットに合わせます。この例では、一連のプリミティブが展開されます[Aspose.TeXおよびObject Texの記事](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)。

それに続いて、通常どおり、入力および出力作業ディレクトリのセットアップを進めます。入力作業ディレクトリには、メイン形式のソースファイルとそのすべての依存関係を含める必要があります。

2番目の大きな違いは、ジョブを実行する方法です。この場合、static [create_format()](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/create_format/#str-aspose.tex.TeXOptions)メソッドを使用します。これは、オプションと併せて、メインソースファイルの名前が形式名と同一であることを要求します。

## カスタム形式でTEXファイルを植林します

独自のTex形式を作成したので、この形式で記述されたTEXファイルを型付けに進めることができます。これがコードです：

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-TypesetWithCustomTeXFormat.py" >}}

形式を指定するには、[formatprovider](https://reference.aspose.com/tex/python-net/aspose.tex.resourceproviders/formatprovider/)クラスのインスタンスを作成する必要があります。 Options Constructorでは、[texconfig.object_tex()](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_tex/#aspose.tex.resourceproviders.FormatProvider)構成を使用します。これは、フォーマットプロバイダーが引数として必要で、エンジンの「処女」状態の上に形式をロードします。

残りのコードは、この[ガイド](/tex/{{lang.url-fragment}}net/conversion/)で前述した機能を利用しているため、おなじみのものでなければなりません。

## Plain Tex形式でTexファイルを植林します

上記のコードからフォーマットプロバイダーを削除すると、エンジンはデフォルト形式をロードします。これは[オブジェクトTex](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/)である4番目の意味でです。したがって、Plain Tex形式でTexファイルが記述されている場合は、このアプローチを使用してサポートされているターゲット形式に変換できます。