---
translation: true
template: /templates/_template-cpp.md
title: ライセンス| C++のAspose.TeX
linktitle: ライセンス
weight: 70
url: /cpp/licensing/
description: C ++用のAspose.TeX APIソリューションのライセンス版で停止した場合、ライセンスの適用方法がわかります。
lastmod: "2026-04-20"
---

{{<section overview>}}

## Aspose.TeXを評価します

評価のために、C ++製品のAspose.TeXを簡単にダウンロードできます。 [C++ 用の Aspose.TeX download page](https://www.nuget.org/packages/aspose.tex.Cpp/)を参照して、最新バージョンを確認してください。評価のダウンロードは、購入したダウンロードと同じです。評価バージョンは、ライセンスを適用するために数行のコードを追加すると、単にライセンスされます。

### 評価バージョンの制限

Aspose.TeXの評価バージョン(ライセンスを指定しない)は、出力ドキュメントで最大4つの最初のページのみを取得できることを除いて、完全な製品機能を提供します。また、これらのページには、評価モードの透かしが刻印されます。

評価の制限なしにAspose.TeXを試してみたい場合は、30日間の一時ライセンスを要求します。詳細については、[一時ライセンスの取得方法？](https://purchase.aspose.com/temporary-license/)を参照してください。

## ライセンスの適用

C ++のAspose.TeXの評価に満足したら、Aspose Webサイトでライセンスを購入します：[Purchase Portal](http://www.aspose.com/purchase/default.aspx)。利用可能なさまざまなライセンスタイプに精通してください。ご質問がある場合は、[Aspose Sales Teamに連絡してください](http://www.aspose.com/corporate/contact/default.aspx)、喜んでお手伝いします。

すべてのAsposeライセンスには、この期間中に出てくる新しいバージョンまたは修正に無料のアップグレードのために1年間のサブスクリプションが搭載されています。ライセンスユーザーと評価ユーザーの両方に無料で無制限のテクニカルサポートを提供しています。

ライセンスは、製品名、ライセンス開発者の数、サブスクリプションの有効期限などの詳細を含むプレーンテキストXMLファイルです。ファイルはデジタルで署名されているため、ファイルを変更しないでください。ファイルに追加のラインブレークを追加しても無効にします。

### ライセンスを適用するタイミング

これらの簡単なルールに従ってください：

- ライセンスは、アプリケーションドメインごとに1回設定する必要があります。
- 他のAspose::Texクラスを使用する前に、ライセンスを設定する必要があります。
- Setlicenseを複数回呼び出すことは有害ではありませんが、プロセッサ時間を無駄にします。
- アプリケーションを開発している場合は、Aspose::Texクラスを使用する前に、スタートアップコードでSetlicenseを呼び出します。
- クラスライブラリを開発している場合は、Aspose::Texを使用するクラスの静的コンストラクターからSetlicenseを呼び出すことができます。 Static Constructorは、クラスのインスタンスが作成される前に実行され、Aspose::Texライセンスが適切に設定されます。

### ファイルまたはストリームオブジェクトを使用してライセンスを適用します

[License::SetLicense](https://reference.aspose.com/tex/cpp/class/aspose.te_x.license)メソッドを使用して、コンポーネントをライセンスします。ライセンスを設定する最も簡単な方法は、ライセンスファイルをAspose.TeX.dllと同じフォルダーに配置し、以下に示すようにパスなしでファイル名を指定することです。

#### ファイルからライセンスをロードします

このコードスニペットは、ファイルまたは組み込みリソースに保存されているライセンスを初期化します。

{{< gist "aspose-com-gists" "d3eef38ac5b929503e8edee25e0873ce" "Aspose.TeX.Examples-LoadLicenseFromFile.cpp" >}}

#### ストリームオブジェクトからライセンスをロードします

これらのコードスニペットは、ストリームからライセンスを初期化します。

{{< gist "aspose-com-gists" "d3eef38ac5b929503e8edee25e0873ce" "Aspose.TeX.Examples-LoadLicenseFromStream.cpp" >}}