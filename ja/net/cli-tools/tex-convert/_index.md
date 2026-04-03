---
translation: true
template: /templates/_template-net.md
title: TeX コマンドラインコンバータ | Aspose.TeX CLI ツール
linktitle: Aspose.TeX 変換
weight: 80
url: /net/cli-tools/tex-convert/
description: Aspose.TeX が提供する強力なコマンドラインコンバータツールで、TeX/LaTeX ドキュメントを簡単かつ効率的に変換できます。Aspose CLI TeX コンバータ。
keywords: tex to pdf cli converter, latex to pdf cli converter, cli tex converter
lastmod: "2026-04-03"
---

{{<section overview>}}

## Overview

[ Aspose.TeX Convert](https://www.nuget.org/packages/Aspose.TeX.Convert) ツールは、TeX および LaTeX ドキュメントをさまざまな形式に変換できる強力な CLI アプリケーションです。このツールを使用すると、開発者やデザイナーは、異なるプラットフォームやデバイス間でシームレスに動作するドキュメントを作成できます。

## Key Features

- **サポートされている入力形式**: TeX、LaTeX。  
- **サポートされている出力形式**: PDF、XPS、PNG、JPEG、BMP、TIFF、SVG。  
- **柔軟な使用方法**: シンプルなコマンドラインコマンドでも、.NET 6.0/7.0 に対応した C# コードからプログラム的にでも利用できます。

## Benefits

Aspose.TeX Convert ツールを使用することで、以下のような利点があります:

- **効率性**: 複雑なソフトウェアを必要とせず、TeX/LaTeX ドキュメントを複数形式にすばやく変換できます。  
- **自動化**: ドキュメント変換を自動化されたワークフローやスクリプトに統合できます。  
- **柔軟性**: さまざまなドキュメント形式に対応し、異なるシステムやアプリケーションとの互換性を確保できます。

## Licensing

Aspose.TeX Convert アプリケーション自体は無料で使用できますが、ドキュメントの変換には有効な Aspose.TeX [license](/tex/{{lang.url-fragment}}net/licensing/) が必要です。ライセンスを購入するか、評価目的でトライアルモードの Aspose.TeX を使用できます。

## How to install TeX Command-Line Converter?

Aspose.TeX Convert ツールは、プロジェクトの要件に応じてグローバルまたはローカルにインストールできます。バージョン競合を避けるため、プロジェクト固有の使用にはローカルインストールを推奨します。

### Global Installation

マシン全体に Aspose.TeX Convert をグローバルインストールするには、次のコマンドを使用します。

```bash
dotnet tool install --global Aspose.TeX.Convert
```

特定のバージョンが必要な場合は、`--version` オプションを指定してください。

### Local Installation

特定のプロジェクト内にローカルインストールするには、まずプロジェクトのルートディレクトリに移動し、次のコマンドを実行します。

1. ツールマニフェストがまだ存在しない場合は作成します:

   ```bash
   dotnet new tool-manifest
   ```

2. Aspose.TeX Convert をローカルにインストールします:

   ```bash
   dotnet tool install Aspose.TeX.Convert --local
   ```

特定のバージョンが必要な場合は、`--version` オプションを使用できます。

### Updating the TeX CLI Converter

Aspose.TeX Convert ツールを最新バージョンに更新するには、インストール形態に合わせて `dotnet tool update` コマンドに `--global` または `--local` を付けて実行します。

### Uninstalling the TeX CLI Converter

ツールをアンインストールする必要がある場合は、インストール形態に応じて `dotnet tool uninstall` コマンドに `--global` または `--local` を付けて実行します。

## Usage

### Command Line

コマンドライン引数を使用してドキュメントを変換します。利用可能なパラメータは以下の通りです:

- `-i, --input [Required]`: 入力 TeX または LaTeX ドキュメントへのパス。  
  - 例: `--input input.tex`
- `-o, --output [Required]`: 変換後のドキュメントの保存先パス。  
  - 例: `--output output.pdf`
- `-f, --format [Optional]`: 出力ドキュメントの形式。  
  - サポート形式: PDF、XPS、PNG、JPEG、BMP、TIFF、SVG。  
  - 例: `--format pdf`
- `-l, --license [Optional]`: Aspose.TeX .NET ライセンスファイルへのパス。  
  - 例: `--license path_to_license.lic`
- `-v, --verbose [Optional]`: 詳細出力を有効にします。  
  - 例: `--verbose`

コマンドライン使用例:

```bash
Aspose.TeX.Convert --input input.tex --output output.pdf --format pdf
```

### How to integrate CLI LaTeX Converter into C# Projects?

Aspose.TeX Convert アプリケーションは、コマンドラインを介して .NET プロジェクトに直接組み込むこともでき、C# コード内からプログラム的に TeX 変換機能にアクセスできます。

**プロジェクトに LaTeX コマンドラインコンバータを追加する方法:**

Visual Studio プロジェクトのルートディレクトリで次のコマンドを実行して、Aspose.TeX Convert ツールをプロジェクトに追加します。

```bash
dotnet Aspose.TeX.Convert add
```

このコマンドにより、Aspose.TeX Convert の機能がプロジェクトに直接組み込まれ、コードからライブラリのメソッドやプロパティを使用できるようになります。カスタマイズした TeX 変換プロセスをアプリケーションに実装したい開発者に特に有用です。

### Use from Code

以下は、C# コード内で Aspose.TeX CLI ツールをプログラム的に使用する例です。

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

詳しい情報や使用例については、[Aspose.TeX for .NET documentation](/tex/{{lang.url-fragment}}net/) をご覧ください。
