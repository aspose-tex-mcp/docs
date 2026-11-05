---
translation: true
template: /templates/_template-net.md
title: システム要件| Aspose.TeX for .NET 入門
linktitle: システム要件
weight: 50
url: /net/system-requirements/
description: NuGet パッケージ Aspose.TeX と Aspose.TeX.Drawing がサポートするオペレーティング システム、.NET のバージョン、開発環境。
lastmod: "2026-11-02"
---

{{<section overview>}}

Aspose.TeX for .NET は、API が同じ 2 つの NuGet パッケージとして提供されています。使用するグラフィックス バックエンドが異なるため、システム要件も異なります。

| | `Aspose.TeX` | `Aspose.TeX.Drawing` |
|---|---|---|
| グラフィックス バックエンド | `System.Drawing.Common` (GDI+) | Aspose.Drawing (パッケージに組み込み) |
| オペレーティング システム | Windows | Windows、Linux、macOS |
| パッケージのターゲット フレームワーク | .NET Framework 4.0、.NET Standard 2.0、.NET 6.0、.NET 7.0 | .NET Standard 2.0、.NET 7.0 |

## サポートされているオペレーティング システム

### Aspose.TeX

* Microsoft Windows のデスクトップ エディションとサーバー エディション (x64、x86)
* Microsoft Azure (Windows ベースのサービス)

.NET 6 以降、Microsoft は、このパッケージが依存する `System.Drawing.Common` を Windows でのみサポートしています。

### Aspose.TeX.Drawing

* Microsoft Windows のデスクトップ エディションとサーバー エディション (x64、x86)
* Linux (x64、Arm64)、Docker コンテナーを含む
* macOS

`libgdiplus` や `fontconfig` などのネイティブ ライブラリやインストール済みフォントは必要ありません。Linux では、XPS と SVG の出力に ICU が必要ですが、一部のコンテナー イメージには含まれていません。[Linux、macOS、Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/)を参照してください。

## サポートされている .NET のバージョン

### Aspose.TeX

* .NET Framework 4.0 以降
* .NET 6 以降
* .NET Standard 2.0 のその他の実装 (.NET Core 2.0 以降など)

### Aspose.TeX.Drawing

* .NET 7 以降 (.NET 8、.NET 9、.NET 10 を含む)
* .NET Framework 4.7.2 以降 (.NET Standard 2.0 経由)
* .NET Standard 2.0 のその他の実装 (.NET Core 2.0 以降など)

## 開発環境

Aspose.TeX for .NET は、Microsoft Visual Studio、Visual Studio Code、JetBrains Rider など、.NET プラットフォームを対象とする任意の開発環境で使用できます。.NET CLI でも使用できます。
