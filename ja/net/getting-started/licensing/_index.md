---
translation: true
template: /templates/_template-net.md
linktitle: ライセンス
title: ライセンス| .NETのAspose.TeX
weight: 70
url: /net/licensing/
description: ライセンスバージョンのAspose.TeX APIソリューションの.NETで停止した場合、ここでライセンスの適用方法を見つけます。
lastmod: "2026-11-02"
---

{{<section overview>}}

## Aspose.TeXを評価します

Aspose.TeX for .NET 製品は、評価目的で簡単にダウンロードできます。最新バージョンについては、[Aspose.TeX for .NET のダウンロードページ](https://www.nuget.org/packages/Aspose.TeX/) をご覧ください。評価版のダウンロードは、ご購入いただいたダウンロードと同じです。評価版は、ライセンスを適用するためのコードを数行追加するだけでライセンスが有効になります。

### 評価バージョンの制限

Aspose.TeXの評価バージョン(ライセンスを指定しない)は、出力ドキュメントで最大4つの最初のページのみを取得できることを除いて、完全な製品機能を提供します。また、これらのページには、評価モードの透かしが刻印されます。

`Aspose.TeX.Drawing` パッケージを使用する場合、評価モードのラスター出力 (PNG、JPEG、BMP、TIFF) には、組み込みのグラフィックス バックエンドによる「Evaluation only Aspose.Drawing」という透かしも入ります。Aspose.TeX のライセンスを適用すると両方の透かしが消えます。Aspose.Drawing のライセンスを別途用意する必要はありません。[Linux、macOS、Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/#licensing)を参照してください。

評価の制限なしにAspose.TeXを試してみたい場合は、30日間の一時ライセンスを要求します。詳細については、[一時ライセンスの取得方法？](https://purchase.aspose.com/temporary-license/)を参照してください。

## ライセンスの適用

.NETのAspose.TeXの評価に満足したら、Aspose Webサイトでライセンスを購入します：[Purchase Portal](https://purchase.aspose.com/pricing?)。利用可能なさまざまなライセンスタイプに精通してください。ご質問がある場合は、[Aspose Sales Teamに連絡してください](https://consulting.aspose.com/)、喜んでお手伝いします。

すべてのAsposeライセンスには、この期間中に出てくる新しいバージョンまたは修正に無料のアップグレードのために1年間のサブスクリプションが搭載されています。ライセンスユーザーと評価ユーザーの両方に無料で無制限のテクニカルサポートを提供しています。

ライセンスは、製品名、ライセンス開発者の数、サブスクリプションの有効期限などの詳細を含むプレーンテキストXMLファイルです。ファイルはデジタルで署名されているため、ファイルを変更しないでください。ファイルに追加のラインブレークを追加しても無効にします。

### ライセンスを適用するタイミング

これらの簡単なルールに従ってください：

- ライセンスは、アプリケーションドメインごとに1回設定する必要があります。
- 他のAspose.TeXクラスを使用する前に、ライセンスを設定する必要があります。
- Setlicenseを複数回呼び出すことは有害ではありませんが、プロセッサ時間を無駄にします。
- Windowsフォームまたはコンソールアプリケーションを開発している場合は、Aspose.TeXクラスを使用する前に、起動コードでSetlicenseを呼び出します。
- ASP.NETアプリケーションを開発するときは、Application_Start保護されたメソッドで、global.asax.csファイルからSetLicenseを呼び出します。アプリケーションが開始されたときに1回呼び出されます。
- Webページがロードされるたびにライセンスがロードされることを意味するため、Page_loadメソッド内からSetlicenseを呼び出さないでください。
- クラスライブラリを開発している場合は、Aspose.TeXを使用するクラスの静的コンストラクターからSetlicenseを呼び出すことができます。 Static Constructorは、クラスのインスタンスが作成される前に実行され、Aspose.TeXライセンスが適切に設定されます。

### ファイルまたはストリームオブジェクトを使用してライセンスを適用します

コンポーネントをライセンスするには、[license.setlicense](https://reference.aspose.com/tex/net/Aspose.TeX/license/)メソッドを使用します。ライセンスを設定する最も簡単な方法は、ライセンスファイルを * Aspose.TeX.dll *と同じフォルダーに配置し、以下に示すようにパスなしでファイル名を指定することです。

#### ファイルからライセンスをロードします

このコードスニペットは、ファイルまたは組み込みリソースに保存されているライセンスを初期化します。

{{< gist "aspose-com-gists" "366cba3dc08d43c99c22bb33ecb5d555" "Example-SetLicenseFromFile.cs" >}}

#### ストリームオブジェクトからライセンスをロードします

これらのコードスニペットは、ストリームからライセンスを初期化します。

{{< gist "aspose-com-gists" "366cba3dc08d43c99c22bb33ecb5d555" "Example-SetLicenseFromStream.cs" >}}

### メーター付きライセンス
Aspose.TeXには、代替ライセンスメカニズムがあります。 API機能の使用に基づいて請求されることを希望する顧客は、 *メーターのライセンス *を使用できます。 *メーター付きライセンス *を適用することは、実際には暗号化キーのペアを適用するのと同じくらい簡単です。詳細については、[メーターライセンスFAQセクション](https://purchase.aspose.com/faqs/licensing/metered/)を参照してください。

次の例に示すように、メーター付きライセンスのパブリックキーとプライベートキーは、[*メーター*](https://reference.aspose.com/tex/net/Aspose.TeX/metered/)クラスのインスタンスを使用して設定されます。 

{{< gist "aspose-com-gists" "366cba3dc08d43c99c22bb33ecb5d555" "Example-SetMeteredLicense.cs" >}}
