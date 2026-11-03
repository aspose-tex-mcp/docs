---
translation: true
template: /templates/_template-net.md
title: Requisitos do sistema | Aspose.TeX para .NET
linktitle: Requisitos do sistema
weight: 50
url: /net/system-requirements/
description: Sistemas operacionais, versões do .NET e ambientes de desenvolvimento suportados pelos pacotes NuGet Aspose.TeX e Aspose.TeX.Drawing.
lastmod: "2026-11-02"
---

{{<section overview>}}

O Aspose.TeX para .NET está disponível como dois pacotes NuGet com a mesma API. Os requisitos do sistema diferem porque eles usam back-ends gráficos diferentes.

| | `Aspose.TeX` | `Aspose.TeX.Drawing` |
|---|---|---|
| Back-end gráfico | `System.Drawing.Common` (GDI+) | Aspose.Drawing, incluído no pacote |
| Sistemas operacionais | Windows | Windows, Linux, macOS |
| Estruturas de destino do pacote | .NET Framework 4.0, .NET Standard 2.0, .NET 6.0, .NET 7.0 | .NET Standard 2.0, .NET 7.0 |

## Sistemas operacionais suportados

### Aspose.TeX

* Edições de desktop e servidor do Microsoft Windows (x64, x86)
* Microsoft Azure (serviços baseados em Windows)

A partir do .NET 6, a Microsoft oferece suporte a `System.Drawing.Common`, do qual este pacote depende, apenas no Windows.

### Aspose.TeX.Drawing

* Edições de desktop e servidor do Microsoft Windows (x64, x86)
* Linux (x64, Arm64), incluindo contêineres Docker
* macOS

Não são necessárias bibliotecas nativas como `libgdiplus` ou `fontconfig`, nem fontes instaladas. No Linux, a saída em XPS e SVG requer o ICU, que algumas imagens de contêiner não incluem. Consulte [Linux, macOS e Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/).

## Versões do .NET suportadas

### Aspose.TeX

* .NET Framework 4.0 ou posterior
* .NET 6 ou posterior
* Qualquer outra implementação do .NET Standard 2.0, como o .NET Core 2.0 ou posterior

### Aspose.TeX.Drawing

* .NET 7 ou posterior, incluindo .NET 8, .NET 9 e .NET 10
* .NET Framework 4.7.2 ou posterior (por meio do .NET Standard 2.0)
* Qualquer outra implementação do .NET Standard 2.0, como o .NET Core 2.0 ou posterior

## Ambientes de desenvolvimento

Você pode usar o Aspose.TeX para .NET em qualquer ambiente de desenvolvimento voltado para a plataforma .NET, como Microsoft Visual Studio, Visual Studio Code ou JetBrains Rider, e com a CLI do .NET.
