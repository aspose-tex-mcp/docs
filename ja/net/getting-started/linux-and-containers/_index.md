---
translation: true
template: /templates/_template-net.md
title: Linux、macOS、Docker | .NETのAspose.TeX
linktitle: Linux、macOS、Docker
weight: 55
url: /net/linux-and-containers/
description: Aspose.TeX.Drawing パッケージを使用して、Aspose.TeX for .NET を Linux、macOS、Docker コンテナーで実行します。パッケージの選択、Aspose.TeX からの移行、Dockerfile、既知の制限について説明します。
keywords: aspose.tex linux, aspose.tex docker, aspose.tex macos, aspose.tex.drawing, latex から pdf linux .NET, latex から png docker .NET, System.Drawing.Common is not supported on this platform
lastmod: "2026-11-02"
---

{{<section overview>}}

## 適切なパッケージを選択する {#choose-the-right-package}

Aspose.TeX for .NET は、API とバージョン番号が同じ 2 つの NuGet パッケージとして公開されています。

| パッケージ | グラフィックス バックエンド | Windows | Linux、macOS | ターゲット フレームワーク |
|---|---|---|---|---|
| [`Aspose.TeX`](https://www.nuget.org/packages/Aspose.TeX) | `System.Drawing.Common` (GDI+) | はい | いいえ | .NET Framework 4.0、.NET Standard 2.0、.NET 6.0、.NET 7.0 |
| **[`Aspose.TeX.Drawing`](https://www.nuget.org/packages/Aspose.TeX.Drawing)** | Aspose.Drawing (マネージド、パッケージに組み込み) | **はい** | **はい** | .NET Standard 2.0、.NET 7.0 |

.NET 6 以降、Microsoft は `System.Drawing.Common` を Windows でのみサポートしています。アプリケーションが Linux または macOS で `Aspose.TeX` パッケージを使用すると、何かをレンダリングした時点で次のエラーが発生します。

```
System.PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.
```

アプリケーションを Linux、macOS、Docker コンテナー、またはその他の Windows 以外の環境で実行する場合は、`Aspose.TeX.Drawing` を使用してください。このパッケージは Windows でも動作するため、1 つのアプリケーションを複数のプラットフォーム向けにビルドする場合は、どこでも使用できます。

`Aspose.TeX.Drawing` は `System.Drawing.Common` にも `libgdiplus` にも依存しません。グラフィックス バックエンド Aspose.Drawing は `Aspose.TeX.dll` に組み込まれているため、このパッケージがアプリケーションに追加するアセンブリは 1 つだけです。.NET 7.0 用ビルドは .NET 7、8、9、10 以降で使用され、.NET Standard 2.0 用ビルドは .NET Framework 4.7.2 以降で使用されます。

## パッケージをインストールする {#install-the-package}

プロジェクトのフォルダーで次のいずれかのコマンドを実行します。

```bash
dotnet add package Aspose.TeX.Drawing
```

```powershell
Install-Package Aspose.TeX.Drawing
```

パッケージを参照するその他の方法については、[インストール](/tex/{{lang.url-fragment}}net/installation/)を参照してください。

{{% alert color="primary" %}}
2 つのパッケージのうち 1 つだけを参照してください。プロジェクトが `Aspose.TeX` と `Aspose.TeX.Drawing` の両方を参照している場合、ビルドは警告なしで成功しますが、出力フォルダーにコピーされる `Aspose.TeX.dll` は 1 つだけで、実行時にアプリケーションがエラーになります (例: `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.SizeF' from assembly 'Aspose.TeX'`)。`Aspose.TeX.Drawing` に切り替えるときは、先に `Aspose.TeX` パッケージを削除してください。

```bash
dotnet remove package Aspose.TeX
dotnet add package Aspose.TeX.Drawing
```
{{% /alert %}}

## Aspose.TeX から Aspose.TeX.Drawing に切り替える {#switch-from-asposetex-to-asposetexdrawing}

名前空間、クラス、メンバーは両方のパッケージで同じであるため、パッケージを置き換えた後もほとんどのコードは変更不要です。

### 色とサイズ {#colors-and-sizes}

レンダリングのオプションと結果では、`MathRendererOptions.TextColor`、`FigureRendererOptions.BackgroundColor`、`MathRenderer.Render` の戻り値など、色とサイズが使用されます。`Aspose.TeX.Drawing` では、これらのメンバーの型は `Aspose.TeX.Drawing.Color` と `Aspose.TeX.Drawing.SizeF` です。どちらの型も `System.Drawing.Color` および `System.Drawing.SizeF` との間で暗黙的に変換されます。これらは `System.Drawing.Common` なしですべてのプラットフォームで使用できる標準の .NET 型であるため、次のようなコードはどちらのパッケージでもコンパイルおよび実行できます。

```csharp
using System.Drawing;
using System.IO;
using Aspose.TeX.Features;

PngMathRendererOptions options = new PngMathRendererOptions
{
    Resolution = 150,
    TextColor = Color.Black,
    BackgroundColor = Color.White
};

using (Stream stream = File.Create("formula.png"))
{
    SizeF size = new PngMathRenderer().Render(@"$$E = mc^2$$", stream, options);
}
```

### スムージング モードと補間モード {#smoothing-and-interpolation-modes}

唯一の違いは、画像の保存オプション (`PngSaveOptions`、`JpegSaveOptions`、`BmpSaveOptions`、`TiffSaveOptions`) の `SmoothingMode` プロパティと `InterpolationMode` プロパティです。`Aspose.TeX` パッケージでは、これらは `System.Drawing.Common` に属する `System.Drawing.Drawing2D` 名前空間の列挙型を使用します (コンパイラは警告 CA1416 でこれらを Windows 専用として報告します)。`Aspose.TeX.Drawing` では、同じメンバーを持つ `Aspose.TeX.Drawing.SmoothingMode` 列挙型と `Aspose.TeX.Drawing.InterpolationMode` 列挙型を使用します。`using` ディレクティブを置き換え、残りのコードはそのままにします。

`Aspose.TeX` の場合:

```csharp
using System.Drawing.Drawing2D;
using Aspose.TeX.Presentation.Image;

PngSaveOptions saveOptions = new PngSaveOptions
{
    Resolution = 300,
    SmoothingMode = SmoothingMode.AntiAlias,
    InterpolationMode = InterpolationMode.HighQualityBicubic
};
```

`Aspose.TeX.Drawing` の場合:

```csharp
using Aspose.TeX.Presentation.Image;
using SmoothingMode = Aspose.TeX.Drawing.SmoothingMode;
using InterpolationMode = Aspose.TeX.Drawing.InterpolationMode;

PngSaveOptions saveOptions = new PngSaveOptions
{
    Resolution = 300,
    SmoothingMode = SmoothingMode.AntiAlias,
    InterpolationMode = InterpolationMode.HighQualityBicubic
};
```

この 2 つの型は、`using Aspose.TeX.Drawing;` ではなく、上記のようにエイリアスを使用してインポートしてください。`Aspose.TeX.Drawing` 名前空間には `Color` と `SizeF` も含まれているため、`System.Drawing` と一緒にインポートすると、コンパイラ エラー `CS0104: 'Color' is an ambiguous reference` が発生します。

### Aspose.TeX.Drawing 名前空間の型 {#types-of-the-asposetexdrawing-namespace}

`Aspose.TeX.Drawing` 名前空間は `Aspose.TeX.Drawing` パッケージにのみ存在します。

| 型 | 使用箇所 | System.Drawing との互換性 |
|---|---|---|
| `Color` | `MathRendererOptions.TextColor`、`FigureRendererOptions.BackgroundColor` | `System.Drawing.Color` との間の暗黙的な変換 |
| `SizeF` | `MathRenderer.Render` と `FigureRenderer.Render` の戻り値、`MathRendererPluginResult` と `FigureRendererPluginResult` の `Size` | `System.Drawing.SizeF` との間の暗黙的な変換 |
| `SmoothingMode` | `ImageSaveOptions.SmoothingMode` | `System.Drawing.Drawing2D.SmoothingMode` と同じメンバーと値 |
| `InterpolationMode` | `ImageSaveOptions.InterpolationMode` | `System.Drawing.Drawing2D.InterpolationMode` と同じメンバーと値 |

## Docker で実行する {#run-in-docker}

Aspose.TeX は独自の組み込み TeX フォントでドキュメントを組版し、`Aspose.TeX.Drawing` は独自のグラフィックス バックエンドを含んでいます。コンテナーには `libgdiplus`、`fontconfig`、インストール済みフォントのいずれも必要ありません。重要なシステム コンポーネントは ICU だけで、これは XPS と SVG の出力に必要です ([グローバリゼーション インバリアント モード](#globalization-invariant-mode)を参照)。

Debian と Ubuntu をベースとする公式の .NET イメージは、追加のセットアップなしで動作します。

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /src
COPY . .
RUN dotnet publish -c Release -o /app

FROM mcr.microsoft.com/dotnet/runtime:8.0
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "MyApp.dll"]
```

`MyApp.dll` はアプリケーションの名前に置き換えてください。ASP.NET Core アプリケーションの場合は、`mcr.microsoft.com/dotnet/runtime` の代わりに `mcr.microsoft.com/dotnet/aspnet` を使用します。同じルールが適用されます。

次の表は、イメージの種類ごとに必要な設定を示しています。

| ベース イメージ | 追加のセットアップ |
|---|---|
| `runtime:8.0`、`aspnet:8.0` (Debian) | 不要 |
| `runtime:8.0-noble`、`aspnet:8.0-noble` (Ubuntu) | 不要 |
| `runtime:8.0-alpine`、`aspnet:8.0-alpine` | ICU をインストールし、インバリアント モードをオフにする (下記参照) |
| `runtime:8.0-noble-chiseled`、`aspnet:8.0-noble-chiseled` | ICU を含む `-noble-chiseled-extra` バリアントを使用する |
| `runtime:8.0-noble-chiseled-extra`、`aspnet:8.0-noble-chiseled-extra` | 不要 |

.NET 9 と .NET 10 のイメージにも同じことが当てはまります。`linux/amd64` と `linux/arm64` のイメージがサポートされています。

### Alpine {#alpine}

Alpine イメージは .NET をグローバリゼーション インバリアント モードで実行し、ICU を含んでいません。`icu-libs` パッケージをインストールし、インバリアント モードをオフにしてください。

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /src
COPY . .
RUN dotnet publish -c Release -o /app

FROM mcr.microsoft.com/dotnet/runtime:8.0-alpine
RUN apk add --no-cache icu-libs
ENV DOTNET_SYSTEM_GLOBALIZATION_INVARIANT=false
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "MyApp.dll"]
```

### Chiseled (distroless) イメージ {#chiseled-distroless-images}

Chiseled イメージにはシェルもパッケージ マネージャーも含まれていないため、ICU をインストールすることはできません。ICU をすでに含んでいる `-chiseled-extra` バリアントを使用してください。

```dockerfile
FROM mcr.microsoft.com/dotnet/sdk:8.0 AS build
WORKDIR /src
COPY . .
RUN dotnet publish -c Release -o /app

FROM mcr.microsoft.com/dotnet/runtime:8.0-noble-chiseled-extra
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "MyApp.dll"]
```

Chiseled イメージは、root 以外のユーザーとしてアプリケーションを実行します。出力ファイルは、アプリケーション フォルダーではなく、マウントしたボリュームや `/tmp` などの書き込み可能な場所に書き込んでください。

## グローバリゼーション インバリアント モード {#globalization-invariant-mode}

XPS と SVG の出力には ICU が必要です。.NET が[グローバリゼーション インバリアント モード](https://aka.ms/GlobalizationInvariantMode)で実行されている場合、XPS または SVG への変換は次のような例外で失敗します。

```
System.Globalization.CultureNotFoundException: Only the invariant culture is supported in globalization-invariant mode. See https://aka.ms/GlobalizationInvariantMode for more information. (Parameter 'name')
en-US is an invalid culture identifier.
```

インバリアント モードは、Alpine イメージと chiseled イメージで既定でオンになっており、プロジェクト プロパティ `<InvariantGlobalization>true</InvariantGlobalization>` によってもオンになります。PDF、PNG、JPEG、BMP、TIFF の出力はインバリアント モードでも動作します。XPS または SVG の出力が必要な場合は、[Docker で実行する](#run-in-docker)に示すように ICU をインストールし、プロジェクトでインバリアント モードをオンにしないでください。

## ライセンス {#licensing}

`Aspose.TeX.Drawing` は `Aspose.TeX` と同じライセンスを使用し、適用方法も同じです ([ライセンス](/tex/{{lang.url-fragment}}net/licensing/)を参照)。このライセンスは組み込みのグラフィックス バックエンド Aspose.Drawing にも適用されるため、Aspose.Drawing のライセンスを別途用意する必要はありません。

評価モードでは、`Aspose.TeX.Drawing` のラスター出力 (PNG、JPEG、BMP、TIFF) に 2 つの透かしが入ります。Aspose.TeX の評価版の透かしと、「Evaluation only Aspose.Drawing」という透かしです。Aspose.TeX のライセンスを適用すると、両方とも消えます。

## 既知の制限 {#known-limitations}

`Aspose.TeX.Drawing` は、まだマルチページ TIFF ファイルを保存できません。`TiffSaveOptions.Multipage` を `true` に設定すると、生成される TIFF ファイルにはドキュメントの最初のページしか含まれず、例外も発生しません。すべてのページを取得するには、`Multipage` を `false` に設定してページごとに個別の TIFF 画像を取得するか、ドキュメントを PDF または XPS に変換してください。

## トラブルシューティング {#troubleshooting}

| エラー | 原因 | 解決策 |
|---|---|---|
| `PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.` | アプリケーションが Linux または macOS で `Aspose.TeX` パッケージを使用している。 | `Aspose.TeX.Drawing` パッケージを使用します。 |
| `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.…' from assembly 'Aspose.TeX'` | プロジェクトが `Aspose.TeX` と `Aspose.TeX.Drawing` の両方を参照している。 | `Aspose.TeX` パッケージを削除します。 |
| XPS または SVG への保存時の `CultureNotFoundException: … en-US is an invalid culture identifier.` | .NET がグローバリゼーション インバリアント モードで実行されている。 | ICU をインストールし、インバリアント モードをオフにします。[グローバリゼーション インバリアント モード](#globalization-invariant-mode)を参照してください。 |
| `error CS0104: 'Color' is an ambiguous reference between 'System.Drawing.Color' and 'Aspose.TeX.Drawing.Color'` | コードが `System.Drawing` と `Aspose.TeX.Drawing` の両方をインポートしている。 | `Aspose.TeX.Drawing` の型をエイリアスでインポートします。[スムージング モードと補間モード](#smoothing-and-interpolation-modes)を参照してください。 |
| マルチページ TIFF ファイルに 1 ページしか含まれない。 | `Aspose.TeX.Drawing` の既知の制限。 | [既知の制限](#known-limitations)を参照してください。 |

## Linux とコンテナーへのデプロイのチェックリスト {#checklist-for-linux-and-container-deployment}

- [ ] `Aspose.TeX` の代わりに `Aspose.TeX.Drawing` を参照し、2 つのパッケージのうち 1 つだけを参照します。
- [ ] コードが `System.Drawing` と `Aspose.TeX.Drawing` の両方をインポートする場合は、`Aspose.TeX.Drawing` の型をエイリアスでインポートします。
- [ ] XPS または SVG の出力が必要な場合は、ICU が利用可能でインバリアント モードがオフであることを確認します。Alpine では `icu-libs` をインストールし、chiseled イメージでは `-chiseled-extra` バリアントを使用し、プロジェクトで `InvariantGlobalization` を設定しないでください。
- [ ] 出力ファイルは書き込み可能な場所に書き込みます。特に、root 以外のユーザーでアプリケーションを実行する chiseled イメージでは注意してください。
- [ ] ライセンスは、アプリケーションの起動時に、最初の変換の前に 1 回だけ適用します。
- [ ] TIFF 形式ですべてのページが必要な場合は、`TiffSaveOptions.Multipage` を `false` に設定するか、PDF または XPS の出力を使用します。
