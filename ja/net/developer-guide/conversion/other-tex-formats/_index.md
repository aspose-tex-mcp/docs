---
translation: true
template: /templates/_template-net.md
title: その他のTeX変換出力形式| Aspose.TeX for .NET 開発者ガイド
linktitle: その他のTeX形式
weight: 18
url: /net/other-tex-formats/
description: .NET用のAspose.TeX APIソリューションの変換機能により、LaTeXファイルと独自のカスタムTeXファイルを変換できます。いくつかのコードの例を次に示します。
lastmod: "2026-04-22"
---

{{<section overview>}}

現在、ラテックス以外の形式で記述されたTeXファイルを変換したいと思う可能性は非常に低いです。しかし、これは、何らかの理由でTeX言語や内部を勉強している場合に可能です。とにかく、**Aspose.TeX for .net**では、プレーンTeX形式で記述されたファイルを変換できます。また、これらの形式で設計されたカスタム形式とタイプセットドキュメントを作成することもできます。

カスタム形式の作成から始めます。

## カスタム形式の作成

フォーマットファイルは、TeXエンジンの内部状態のバイナリダンプであることを覚えておいてください。

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-CreateCustomFormat.cs" >}}

ご覧のとおり、コードはTeXファイルを変換するためのコードに似ています。しかし、いくつかの違いがあります。

まず、[TeXConfig.ObjectIniTeX](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objectinitex/)ジョブ構成を使用します。これは、エンジンの状態「Virgin」を離れる特別な構成です。つまり、内部パラメーターにはデフォルト値があり、コントロールシーケンスのセットはプリミティブのセットと一致します。私たちの例では、プリミティブのセットは、[ここ](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex)に言及された意味で拡張されます。

次に、通常どおり、入力および出力作業ディレクトリを設定します。入力作業ディレクトリには、メイン形式のソースファイルとそのすべての依存関係を含める必要があります。

そして、2番目の重要な違いは、私たちが仕事をする方法です。今回は、static [CreateFormat()](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/)メソッドを使用します。これは、オプションとともにメインソースファイルの名前を取得し、形式名と同じでなければなりません。

## カスタム形式でTeXファイルを組版します

独自のTeX形式ができたので、この形式で記述されたTeXファイルを組版したいと考えています。これがコードです：

{{< gist "aspose-com-gists" "deadfd7c29ffe40024a9b6d12f0ed18a" "Example-TypesetWithCustomFormat.cs" >}}

明らかに、形式を何らかの形で指定する必要があります。まず、[FormatProvider](https://reference.aspose.com/tex/net/aspose.tex.resourceproviders/formatprovider/)クラスのインスタンスを作成する必要があります。次に、オプションコンストラクターで[TeXConfig.ObjectTeX()](https://reference.aspose.com/tex/net/aspose.tex/texconfig/objecttex/)構成を使用します。これは、フォーマットプロバイダーを引数として受け取り、エンジンの「処女」状態の上に形式をロードします。

残りのコードはあなたに馴染みがあるはずです。この[ガイド](/tex/{{lang.url-fragment}}net/conversion/)で前述した機能を使用します。

## Plain TeX形式でTeXファイルを組版します

実証されたコードからフォーマットプロバイダーを捨てると、エンジンはデフォルト形式をロードします。これは[オブジェクトTeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/)である4番目の意味でです。したがって、Plain TeX形式でTeXファイルが書かれている場合、この方法では、サポートされているターゲット形式に変換できます。
