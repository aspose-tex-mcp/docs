---
translation: true
template: /templates/_template-net.md
title: TEXコマンドラインコンバーター| Aspose.TeX CLIツール
linktitle: Aspose.TeX convert
weight: 80
url: /net/cli-tools/tex-convert/
description: Aspose.TeXからの強力なコマンドラインコンバーターツールは、Tex/Latexドキュメントを簡単かつ効率的に変換します。 Asposes Cli Texコンバーター。
keywords: TEXからPDF CLIコンバーター、ラテックスからPDF CLIコンバーター、CLI TEXコンバーター
lastmod: "2025-06-09"
---

{{<section overview>}}

## 概要

[Aspose.TeX Convert](https://www.nuget.org/packages/aspose.tex.Convert)ツールは、TexおよびLaTexドキュメントのさまざまな形式への変換を容易にする強力なCLIアプリケーションです。このツールにより、開発者と設計者は、さまざまなプラットフォームやデバイスでシームレスに動作するドキュメントを作成できます。

## 重要な機能

- **サポートされている入力形式**：Tex、LaTex。
- **サポートされている出力形式**：PDF、XPS、PNG、JPEG、BMP、TIFF、SVG。
- **柔軟な使用法**：.NET 6.0/7.0と互換性のあるC＃コードで、単純なコマンドラインコマンドを介してプログラムで使用できます。

## 利点

Aspose.TeXの使用ツールを使用すると、いくつかの利点があります。

- **効率**：複雑なソフトウェアを必要とせずに、Tex/LaTexドキュメントを複数の形式にすばやく変換します。
- **自動化**：ドキュメント変換を自動化されたワークフローとスクリプトに統合します。
- **柔軟性**：さまざまなドキュメント形式を処理して、さまざまなシステムやアプリケーションとの互換性を確保します。

## ライセンス

Aspose.TeXのコンバートアプリケーション自体は自由に使用できますが、ドキュメントを変換するには有効なAsopsion.tex [ライセンス](/tex/{{lang.url-fragment}}net/licensing/)が必要です。ライセンスを購入するか、評価の目的でトライアルモードでasophes.texを使用できます。

## Texコマンドラインコンバーターをインストールする方法は？

Aspose.TeX変換ツールは、プロジェクトのニーズに応じて、グローバルまたはローカルにインストールできます。バージョンの競合を回避するために、プロジェクト固有の使用のためにローカルインストールを使用することをお勧めします。

### グローバルインストール

Aspose.TeXをインストールするには、マシンにグローバルに変換するには、次のコマンドを使用してください。


```bash
dotnet tool install --global Aspose.TeX.Convert
```

ツールの特定のバージョンが必要な場合は、 `-version`オプションを指定します。

### ローカルインストール

特定のプロジェクト内のローカルインストールについては、最初に、プロジェクトのルートディレクトリに移動します。次に、次のコマンドを実行します。


1. まだ存在していない場合は、ツールマニフェストを作成します。

   ```bash
   dotnet new tool-manifest
   ```

2. Aspose.TeXをローカルにインストールします。

   ```bash
   dotnet tool install Aspose.TeX.Convert --local
   ```

繰り返しますが、特定のバージョンに `-version`オプションを指定できます。

### Tex CLIコンバーターの更新

Aspose.TeXを最新バージョンに変換するには、「Global」または ` -  local`を使用して` dotnetツール更新 `コマンドを使用して、インストールタイプに一致します。

### Tex CLIコンバーターのアンインストール

ツールをアンインストールする必要がある場合は、ツールのインストール方法に応じて、「Global」または `-local`を使用して「dotnetツールUninstall」コマンドを使用します。

## 使用法

### コマンドライン

コマンドライン引数を使用してドキュメントを変換します。利用可能なパラメーターは次のとおりです。


- `-i、 - 入力[必須]`：入力TEXまたはLATEXドキュメントへのパス。
  - Example: `--input input.tex`
- `-o、-output [必須]`：変換されたドキュメントのパス。
  - Example: `--output output.pdf`
- `-f、 -  format [optional]`：ドキュメント形式を出力します。
  - Supported formats: PDF, XPS, PNG, JPEG, BMP, TIFF, SVG.
  - Example: `--format pdf`
- `-l、 -  license [optional]`：Aspose.TeX .netライセンスファイルへのパス。
  - Example: `--license path_to_license.lic`
- `-v、-verbose [optional]`：verbose出力を有効にします。
  - Example: `--verbose`

例コマンドラインの使用法：


```bash
Aspose.TeX.Convert --input input.tex --output output.pdf --format pdf
```

### CLIラテックスコンバーターをC＃プロジェクトに統合する方法は？

Aspose.TeXコンバートアプリケーションは、コマンドラインを使用して.NETプロジェクトに直接統合して、C＃コード内のTEX変換機能へのプログラムアクセスを可能にすることもできます。

**プロジェクトにラテックスコマンドラインコンバーターを追加する：**

Aspose.TeXをVisual Studioプロジェクトに変換するには、プロジェクトのルートディレクトリに移動し、次のコマンドを実行します。

```bash
dotnet Aspose.TeX.Convert add
```

このコマンドは、Aspose.TeXをプロジェクトに直接変換するため、コードを介してライブラリのメソッドとプロパティを使用できるようにします。これは、アプリケーション内にカスタマイズされたTEX変換プロセスを直接実装しようとする開発者にとって特に役立ちます。

### コードから使用します

以下は、C＃コードでプログラムでAspose.TeX CLIツールを使用する例を示します。


```csharp
using Aspose.TeX.MicroApps.Convert;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        // Initialize convert options
        var options = new ConvertOptions
        {
            // Required: Specify the input document path
            InputDocument = "input.tex",
            
            // Required: Specify the output document path
            OutputFilePath = "output.pdf",
            
            // Optional: Specify the output format
            ToFormat = "pdf"
        };

        // Conditional: Apply license if you have one
        if (isLicensed)
        {
            options.LicenseFile = "path_to_license.lic";
        }

        // Execute the conversion task
        await ConvertTasks.Create(options).Execute();
    }
}
```

詳細情報と使用例については、[Aspose.TeX for .NET のドキュメント](/tex/{{lang.url-fragment}}net/)をご覧ください。