---
translation: true
template: /templates/_template-cpp.md
title: TEXオプションの他の管理| C ++
linktitle: その他のオプション
weight: 17
url: /cpp/other-options/
description: C ++のAspose.TeX APIソリューションの変換機能により、エンジンが起動する初期インタラクションモードを設定できます。いくつかのコードの例を次に示します。
lastmod: "2025-06-09"
---

{{<section overview>}}

## インタラクションモードを設定する方法

[ここ](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes)、** C ++のAspose.TeXを述べたように、エンジンが起動する初期インタラクションモードを設定できます。これが私たちのやり方です：

```C++
// Create conversion options instance.
...
// Set the interaction mode.
options->set_Interaction(Interaction::NonstopMode);
```

## 求人名を設定する方法

メイン入力ファイルをファイル名として渡すと、拡張子は異なりますが、同じ名前の出力ファイルが生成されます。TeXエンジンは入力ファイル名を*ジョブ名*と呼び、明示的に別の名前が指定された補助ファイルが書き込まれる場合を除き、出力ファイルにもそれを使用します。メイン入力ファイルを[ストリーム](/tex/{{lang.url-fragment}}cpp/other-ways-of-main-input/#providing-the-main-input-file-as-a-stream)として渡すと、TeXエンジンはデフォルトのジョブ名である*texput*を使用します。
どちらの場合も、適切な変換オプションを割り当てることにより、ジョブ名をオーバーライドできます。

```C++
// Create conversion options instance.
...
// Set the job name.
options->set_JobName(u"my-job-name");
```

## 仕事を繰り返す方法

ラベルと参照に関して[上記](/tex/{{lang.url-fragment}}net/latex-io/#latex-input)を述べたように、同じジョブを2回実行したい場合があります。これがどのように行われるかは次のとおりです。

```C++
// Create conversion options instance.
...
// Set the job name.
options->set_Repeat(true);
```