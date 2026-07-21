---
translation: true
template: /templates/_template-java.md
linktitle: ライセンス
title: ライセンス| Java用のAspose.TeX
weight: 70
url: /java/licensing/
description: Java用のAspose.TeX APIソリューションのライセンス版で停止した場合、ライセンスの適用方法がわかります。
lastmod: "2026-04-21"
---

{{<section overview>}}


### 評価バージョンの制限

Aspose.TeXの評価バージョン(ライセンスを指定しない)は、出力ドキュメントで最大4つの最初のページのみを取得できることを除いて、完全な製品機能を提供します。また、これらのページには、評価モードの透かしが刻印されます。

評価の制限なしにAspose.TeXを試してみたい場合は、30日間の一時ライセンスを要求します。詳細については、[一時ライセンスの取得方法？](https://purchase.aspose.com/temporary-license/)を参照してください。

### ファイルまたはストリームオブジェクトを使用してライセンスを適用します

[License.setLicense](https://reference.aspose.com/tex/java/com.aspose.tex/license/#setLicense-java.lang.String-) メソッドを使用して、コンポーネントをライセンスします。ライセンスを設定する最も簡単な方法は、ライセンスファイルを * Aspose.TeX.jar *と同じフォルダーに配置し、以下に示すようにパスなしでファイル名を指定することです。

#### ファイルからライセンスをロードします

このコードスニペットは、ファイルまたは組み込みリソースに保存されているライセンスを初期化します。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-LoadLicenseFromFile.java" >}}

#### ストリームオブジェクトからライセンスをロードします

これらのコードスニペットは、ストリームからライセンスを初期化します。

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-LoadLicenseFromStream.java" >}}

### メーター付きライセンス

Aspose.TeXには、 *Meteredライセンス *と呼ばれる代替ライセンスメカニズムがあります。顧客がAPI機能の使用に基づいて請求されることを希望する場合、実際には暗号化キーペアを適用するのと同じくらい簡単な *メーターライセンス *を適用できます。詳細については、[メーターライセンスFAQセクション](https://purchase.aspose.com/faqs/licensing/metered/)を参照してください。

以下に示すように、メーター付きライセンスのパブリックキーとプライベートキーは、[*メーター*](https://reference.aspose.com/tex/net/Aspose.TeX/metered/)クラスのインスタンスを使用して設定できます。 

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-SetMeteredLicense.java" >}}