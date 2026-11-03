---
translation: true
template: /templates/_template-net.md
title: Linux, macOS e Docker | Aspose.TeX para .NET
linktitle: Linux, macOS e Docker
weight: 55
url: /net/linux-and-containers/
description: Execute o Aspose.TeX para .NET no Linux, no macOS e em contêineres Docker com o pacote Aspose.TeX.Drawing. Escolha do pacote, migração do Aspose.TeX, Dockerfiles e limitações conhecidas.
keywords: aspose.tex linux, aspose.tex docker, aspose.tex macos, aspose.tex.drawing, latex para pdf linux .NET, latex para png docker .NET, System.Drawing.Common is not supported on this platform
lastmod: "2026-11-02"
---

{{<section overview>}}

## Escolher o pacote certo {#choose-the-right-package}

O Aspose.TeX para .NET é publicado como dois pacotes NuGet com a mesma API e o mesmo número de versão:

| Pacote | Back-end gráfico | Windows | Linux, macOS | Estruturas de destino |
|---|---|---|---|---|
| [`Aspose.TeX`](https://www.nuget.org/packages/Aspose.TeX) | `System.Drawing.Common` (GDI+) | Sim | Não | .NET Framework 4.0, .NET Standard 2.0, .NET 6.0, .NET 7.0 |
| **[`Aspose.TeX.Drawing`](https://www.nuget.org/packages/Aspose.TeX.Drawing)** | Aspose.Drawing (gerenciado, incluído no pacote) | **Sim** | **Sim** | .NET Standard 2.0, .NET 7.0 |

A partir do .NET 6, a Microsoft oferece suporte a `System.Drawing.Common` apenas no Windows. Se o seu aplicativo usar o pacote `Aspose.TeX` no Linux ou no macOS, ele falhará assim que renderizar algo:

```
System.PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.
```

Use `Aspose.TeX.Drawing` quando o aplicativo for executado no Linux, no macOS, em contêineres Docker ou em outros ambientes que não sejam Windows. O pacote também funciona no Windows, portanto você pode usá-lo em todos os lugares se criar um único aplicativo para várias plataformas.

`Aspose.TeX.Drawing` não depende de `System.Drawing.Common` nem de `libgdiplus`. O back-end gráfico Aspose.Drawing está incorporado em `Aspose.TeX.dll`, então o pacote adiciona um único assembly ao seu aplicativo. A compilação para .NET 7.0 é usada pelo .NET 7, 8, 9, 10 e versões posteriores; a compilação para .NET Standard 2.0, pelo .NET Framework 4.7.2 e versões posteriores.

## Instalar o pacote {#install-the-package}

Execute um dos seguintes comandos na pasta do seu projeto:

```bash
dotnet add package Aspose.TeX.Drawing
```

```powershell
Install-Package Aspose.TeX.Drawing
```

Consulte [Instalação](/tex/{{lang.url-fragment}}net/installation/) para outras formas de referenciar o pacote.

{{% alert color="primary" %}}
Referencie apenas um dos dois pacotes. Se um projeto referenciar tanto `Aspose.TeX` quanto `Aspose.TeX.Drawing`, ele será compilado sem avisos, mas apenas um `Aspose.TeX.dll` será copiado para a pasta de saída, e o aplicativo falhará em tempo de execução, por exemplo com `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.SizeF' from assembly 'Aspose.TeX'`. Ao mudar para `Aspose.TeX.Drawing`, remova primeiro o pacote `Aspose.TeX`:

```bash
dotnet remove package Aspose.TeX
dotnet add package Aspose.TeX.Drawing
```
{{% /alert %}}

## Mudar do Aspose.TeX para o Aspose.TeX.Drawing {#switch-from-asposetex-to-asposetexdrawing}

Namespaces, classes e membros são os mesmos nos dois pacotes, portanto a maior parte do código não precisa de alterações após a substituição do pacote.

### Cores e tamanhos {#colors-and-sizes}

As opções e os resultados de renderização usam cores e tamanhos, por exemplo `MathRendererOptions.TextColor`, `FigureRendererOptions.BackgroundColor` e o valor retornado por `MathRenderer.Render`. Em `Aspose.TeX.Drawing`, esses membros têm os tipos `Aspose.TeX.Drawing.Color` e `Aspose.TeX.Drawing.SizeF`. Os dois tipos são convertidos implicitamente de e para `System.Drawing.Color` e `System.Drawing.SizeF`. Esses são tipos padrão do .NET disponíveis em todas as plataformas sem `System.Drawing.Common`, portanto um código como o seguinte é compilado e executado com qualquer um dos pacotes:

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

### Modos de suavização e interpolação {#smoothing-and-interpolation-modes}

A única alteração diz respeito às propriedades `SmoothingMode` e `InterpolationMode` das opções de salvamento de imagens (`PngSaveOptions`, `JpegSaveOptions`, `BmpSaveOptions`, `TiffSaveOptions`). No pacote `Aspose.TeX`, elas usam enumerações do namespace `System.Drawing.Drawing2D`, que pertence a `System.Drawing.Common` (o compilador as marca como exclusivas do Windows com o aviso CA1416). Em `Aspose.TeX.Drawing`, elas usam as enumerações `Aspose.TeX.Drawing.SmoothingMode` e `Aspose.TeX.Drawing.InterpolationMode`, que têm os mesmos membros. Substitua a diretiva `using` e mantenha o restante do código.

Com `Aspose.TeX`:

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

Com `Aspose.TeX.Drawing`:

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

Importe esses dois tipos com aliases, como mostrado acima, e não com `using Aspose.TeX.Drawing;`. O namespace `Aspose.TeX.Drawing` também contém `Color` e `SizeF`, portanto importá-lo junto com `System.Drawing` causa o erro de compilação `CS0104: 'Color' is an ambiguous reference`.

### Tipos do namespace Aspose.TeX.Drawing {#types-of-the-asposetexdrawing-namespace}

O namespace `Aspose.TeX.Drawing` existe apenas no pacote `Aspose.TeX.Drawing`:

| Tipo | Usado por | Compatibilidade com System.Drawing |
|---|---|---|
| `Color` | `MathRendererOptions.TextColor`, `FigureRendererOptions.BackgroundColor` | Conversão implícita de e para `System.Drawing.Color` |
| `SizeF` | Valor retornado por `MathRenderer.Render` e `FigureRenderer.Render`; `Size` de `MathRendererPluginResult` e `FigureRendererPluginResult` | Conversão implícita de e para `System.Drawing.SizeF` |
| `SmoothingMode` | `ImageSaveOptions.SmoothingMode` | Mesmos membros e valores que `System.Drawing.Drawing2D.SmoothingMode` |
| `InterpolationMode` | `ImageSaveOptions.InterpolationMode` | Mesmos membros e valores que `System.Drawing.Drawing2D.InterpolationMode` |

## Executar no Docker {#run-in-docker}

O Aspose.TeX compõe documentos com suas próprias fontes TeX incorporadas, e `Aspose.TeX.Drawing` contém seu back-end gráfico. O seu contêiner não precisa de `libgdiplus`, `fontconfig` nem de fontes instaladas. O único componente do sistema que importa é o ICU, necessário para a saída em XPS e SVG (consulte [Modo invariável de globalização](#globalization-invariant-mode)).

As imagens oficiais do .NET baseadas em Debian e Ubuntu funcionam sem configuração adicional:

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

Substitua `MyApp.dll` pelo nome do seu aplicativo. Para aplicativos ASP.NET Core, use `mcr.microsoft.com/dotnet/aspnet` em vez de `mcr.microsoft.com/dotnet/runtime`; as mesmas regras se aplicam.

A tabela a seguir mostra o que cada tipo de imagem precisa:

| Imagem base | Configuração adicional |
|---|---|
| `runtime:8.0`, `aspnet:8.0` (Debian) | Nenhuma |
| `runtime:8.0-noble`, `aspnet:8.0-noble` (Ubuntu) | Nenhuma |
| `runtime:8.0-alpine`, `aspnet:8.0-alpine` | Instalar o ICU e desativar o modo invariável (veja abaixo) |
| `runtime:8.0-noble-chiseled`, `aspnet:8.0-noble-chiseled` | Usar a variante `-noble-chiseled-extra`, que inclui o ICU |
| `runtime:8.0-noble-chiseled-extra`, `aspnet:8.0-noble-chiseled-extra` | Nenhuma |

O mesmo vale para as imagens do .NET 9 e do .NET 10. As imagens `linux/amd64` e `linux/arm64` são suportadas.

### Alpine {#alpine}

As imagens Alpine executam o .NET no modo invariável de globalização e não contêm o ICU. Instale o pacote `icu-libs` e desative o modo invariável:

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

### Imagens chiseled (distroless) {#chiseled-distroless-images}

As imagens chiseled não contêm shell nem gerenciador de pacotes, portanto não é possível instalar o ICU nelas. Use a variante `-chiseled-extra`, que já inclui o ICU:

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

As imagens chiseled executam o aplicativo como um usuário sem privilégios de root. Grave os arquivos de saída em um local com permissão de gravação, como um volume montado ou `/tmp`, e não na pasta do aplicativo.

## Modo invariável de globalização {#globalization-invariant-mode}

A saída em XPS e SVG requer o ICU. Se o .NET for executado no [modo invariável de globalização](https://aka.ms/GlobalizationInvariantMode), a conversão para XPS ou SVG falhará com uma exceção como esta:

```
System.Globalization.CultureNotFoundException: Only the invariant culture is supported in globalization-invariant mode. See https://aka.ms/GlobalizationInvariantMode for more information. (Parameter 'name')
en-US is an invalid culture identifier.
```

O modo invariável fica ativado por padrão nas imagens Alpine e chiseled e também é ativado pela propriedade de projeto `<InvariantGlobalization>true</InvariantGlobalization>`. A saída em PDF, PNG, JPEG, BMP e TIFF funciona no modo invariável. Se você precisar de saída em XPS ou SVG, instale o ICU como mostrado em [Executar no Docker](#run-in-docker) e não ative o modo invariável no projeto.

## Licenciamento {#licensing}

`Aspose.TeX.Drawing` usa a mesma licença que `Aspose.TeX`, e você a aplica da mesma forma (consulte [Licenciamento](/tex/{{lang.url-fragment}}net/licensing/)). A licença também cobre o back-end gráfico Aspose.Drawing incorporado; não é necessária uma licença separada do Aspose.Drawing.

No modo de avaliação, a saída rasterizada (PNG, JPEG, BMP, TIFF) de `Aspose.TeX.Drawing` traz duas marcas d'água: a marca d'água de avaliação do Aspose.TeX e uma marca d'água "Evaluation only Aspose.Drawing". Ambas desaparecem quando você aplica a licença do Aspose.TeX.

## Limitações conhecidas {#known-limitations}

`Aspose.TeX.Drawing` ainda não consegue salvar arquivos TIFF de várias páginas. Se você definir `TiffSaveOptions.Multipage` como `true`, o arquivo TIFF resultante conterá apenas a primeira página do documento, e nenhuma exceção será lançada. Para obter todas as páginas, defina `Multipage` como `false` para obter uma imagem TIFF separada para cada página, ou converta o documento para PDF ou XPS.

## Solução de problemas {#troubleshooting}

| Erro | Causa | Solução |
|---|---|---|
| `PlatformNotSupportedException: System.Drawing.Common is not supported on this platform.` | O aplicativo usa o pacote `Aspose.TeX` no Linux ou no macOS. | Use o pacote `Aspose.TeX.Drawing`. |
| `TypeLoadException: Could not load type 'Aspose.TeX.Drawing.…' from assembly 'Aspose.TeX'` | O projeto referencia tanto `Aspose.TeX` quanto `Aspose.TeX.Drawing`. | Remova o pacote `Aspose.TeX`. |
| `CultureNotFoundException: … en-US is an invalid culture identifier.` ao salvar em XPS ou SVG | O .NET é executado no modo invariável de globalização. | Instale o ICU e desative o modo invariável; consulte [Modo invariável de globalização](#globalization-invariant-mode). |
| `error CS0104: 'Color' is an ambiguous reference between 'System.Drawing.Color' and 'Aspose.TeX.Drawing.Color'` | O código importa tanto `System.Drawing` quanto `Aspose.TeX.Drawing`. | Importe os tipos de `Aspose.TeX.Drawing` com aliases; consulte [Modos de suavização e interpolação](#smoothing-and-interpolation-modes). |
| Um arquivo TIFF de várias páginas contém apenas uma página. | Limitação conhecida de `Aspose.TeX.Drawing`. | Consulte [Limitações conhecidas](#known-limitations). |

## Lista de verificação para implantação no Linux e em contêineres {#checklist-for-linux-and-container-deployment}

- [ ] Referencie `Aspose.TeX.Drawing` em vez de `Aspose.TeX`, e apenas um dos dois pacotes.
- [ ] Se o seu código importar tanto `System.Drawing` quanto `Aspose.TeX.Drawing`, importe os tipos de `Aspose.TeX.Drawing` com aliases.
- [ ] Se precisar de saída em XPS ou SVG, verifique se o ICU está disponível e se o modo invariável está desativado: instale `icu-libs` no Alpine, use a variante `-chiseled-extra` das imagens chiseled e não defina `InvariantGlobalization` no projeto.
- [ ] Grave os arquivos de saída em um local com permissão de gravação, especialmente nas imagens chiseled, que executam o aplicativo sem privilégios de root.
- [ ] Aplique a licença uma única vez na inicialização do aplicativo, antes da primeira conversão.
- [ ] Se precisar de todas as páginas no formato TIFF, defina `TiffSaveOptions.Multipage` como `false` ou use a saída em PDF ou XPS.
