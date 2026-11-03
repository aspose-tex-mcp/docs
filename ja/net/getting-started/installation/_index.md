---
translation: true
template: /templates/_template-net.md
linktitle: インストール
title: インストール| .NETのAspose.TeX
weight: 60
url: /net/installation/
description: .NETのAspose.TeX APIドキュメントは、「ダウンロードパッケージ」をクリックして、ダウンロードしたZIPパッケージにあるか、Nugetギャラリーから入手できます。
lastmod: "2026-11-02"
---

{{<section overview>}}

## パッケージを選択する

Aspose.TeX for .NET は、API が同じ 2 つの NuGet パッケージとして提供されています。

- [Aspose.TeX](https://www.nuget.org/packages/Aspose.TeX) は `System.Drawing.Common` を使用し、Windows で動作します。
- [Aspose.TeX.Drawing](https://www.nuget.org/packages/Aspose.TeX.Drawing) は組み込みのグラフィックス バックエンド Aspose.Drawing を使用し、Windows、Linux、macOS (Docker コンテナーを含む) で動作します。

どちらか一方だけを参照してください。.NET CLI でパッケージをインストールするには、プロジェクトのフォルダーで次のいずれかのコマンドを実行します。

```bash
dotnet add package Aspose.TeX
```

```bash
dotnet add package Aspose.TeX.Drawing
```

`Aspose.TeX.Drawing` の詳細については、[Linux、macOS、Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/)を参照してください。このページの以降の部分では Visual Studio でのインストールについて説明します。内容は両方のパッケージに共通です。

## NuGetを介して.net用のAspose.TeXをインストールします

NuGetは、開発中にサードパーティライブラリを.NETアプリケーションに組み込むプロセスを簡素化するための.NETプラットフォームのための無料のオープンソース開発者中心のパッケージ管理システムです。これは、.NETフレームワークを使用するVisual Studioプロジェクトのライブラリとツールを簡単に追加、削除、更新できるビジュアルスタジオ拡張機能です。ライブラリまたはツールは、NuGetパッケージを作成し、NuGetリポジトリ内に保存することにより、他の開発者と簡単に共有できます。パッケージをインストールすると、NuGetはファイルをソリューションにコピーし、参照の追加やapp.configまたはweb.configファイルの変更など、必要な変更を自動的に作成します。ライブラリを削除することに決めた場合、NuGetはファイルを削除し、プロジェクトに行った変更を逆転させて、クラッターが残されないようにします。

### .netのAspose.TeXを参照してください

この素晴らしい機能の利益を得て、[.NET用のAspose.TeX](https://www.NuGet.org/packages/Aspose.TeX)ライブラリをNuGetパッケージにバンドルし、NuGetリポジトリにアップロードしました。このオプションを使用すると、システムにこのコンポーネントをインストールせずに、.NETにAspose.TeXを使用することでメリットがあります。 NuGetは、Visual Studio 2010およびHigherバージョン、Visual Web Developer 2010、およびWindows Phone Developer Tools 7.1で実行されます。テストでは、Visual Studio 2015 Ultimateでテストしました。

開始するために：

1. Visual Studioでソリューションまたはプロジェクトを開きます。
2. ビジュアルスタジオ拡張機能としてNuGetパッケージマネージャーを追加します。

    1. **ツール** メニューを選択し、**拡張機能マネージャー** を選択します。
    2. **オンラインギャラリー** を選択して、オンラインで利用可能なパッケージの完全なリストを取得します。
    3. **NuGet パッケージ マネージャー** を選択します。
    4. **ダウンロード** をクリックします。
    5. パッケージ マネージャーがインストールされたら、Visual Studio を再起動して変更を有効にします。
        NuGet パッケージ マネージャーがインストールされている場合、**NuGet パッケージの管理** ウィンドウから、または Visual Studio 専用の **パッケージ マネージャー コンソール** ウィンドウから PowerShell コマンドライン コマンドを使用して、パッケージを検索、インストール、削除、更新できます。**ツール** を選択し、続いて **ライブラリ パッケージ マネージャー** を選択すると、両方のオプションが表示されます。

### パッケージマネージャーコンソールを使用してパッケージをインストールします

パッケージマネージャーコンソールを使用してコンポーネントを参照するには：

1. Visual Studioで.NETアプリケーションを開きます。
2. **ツール**メニューで、**ライブラリパッケージマネージャー**を選択し、**パッケージマネージャーコンソール**を選択します。
3. コマンド「Install-Package Aspose.TeX」を入力して最新のフルリリースをインストールするか、コマンド「Install-Package Aspose.TeX -prerelease」を入力して、Hot Fixを含む最新リリースをインストールします。
4. **Enter**を押します。

### パッケージマネージャーコンソールを使用してパッケージを更新します

NuGetを介してコンポーネントを既に参照している場合は、次の手順に従って最新バージョンへの参照を更新します。

1. Visual Studioで.NETアプリケーションを開きます。
2. **ツール**メニューから、**ライブラリパッケージマネージャー**を選択し、**パッケージマネージャーコンソール**が続き、パッケージマネージャーコンソールを開きます。
3. コマンド「Update-Package Aspose.TeX」を入力して最新のフルリリースを参照するか、コマンド「Update-Package Aspose.TeX -prerelease」を入力して、Hot Fixを含む最新リリースをインストールします。
4. **Enter**を押します。

### パッケージマネージャーGUIを使用してパッケージをインストールします

これらの手順に従って、パッケージマネージャーGUIを使用してコンポーネントを参照してください。

1. Visual Studioで.NETアプリケーションを開きます。
2. **ツール**メニューから、**ライブラリパッケージマネージャー**を選択します。 

    ソリューション エクスプローラーからも同様のオプションを利用できます。
    1. プロジェクト名を右クリックします。
    2. **NuGet パッケージの管理** を選択します。

3. 左メニューから**オンライン**を選択します。
4. タイプ**Aspose.TeX**検索ボックスに入り、.net for .netのAspose.TeXを見つけます。
5. [インストール/更新]をクリックします**。