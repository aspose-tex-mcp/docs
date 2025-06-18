---
translation: true
template: /templates/_template-net.md
title: Converter da linha de comando Tex | Aspose.Tex CLI Tools
linktitle: Aspose.TeX converte
weight: 80
url: /net/cli-tools/tex-convert/
description: Ferramenta de conversor de linha de comando poderosa do Aspose.TeX para converter documentos Tex/Latex com facilidade e eficiência. ASPO CLI TEX conversor.
keywords: Conversor Tex para PDF CLI, LATEX para PDF CLI Converter, CLI Tex Converter
lastmod: "2025-06-16"
---

{{<section overview>}}

## Visão geral

A ferramenta [Aspose.TeX convert](https://www.nuget.org/packages/Aspose.TeX.Convert) é um poderoso aplicativo da CLI que facilita a conversão de documentos Tex e LaTeX em vários formatos. Essa ferramenta permite que desenvolvedores e designers criem documentos que funcionam perfeitamente em diferentes plataformas e dispositivos.

## Principais recursos

- **Formatos de entrada suportados**: tex, LaTeX.
- **Formatos de saída suportados**: PDF, XPS, PNG, JPEG, BMP, TIFF, SVG.
- **Uso flexível**: Pode ser usado por comandos simples da linha de comando e programaticamente no seu código C#, compatível com .NET 6.0/7.0.

## Benefícios

Usando a ferramenta Aspose.TeX Convert fornece várias vantagens:

- **Eficiência**: Converte rapidamente documentos Tex/Latex em vários formatos sem a necessidade de software complexo.
- **Automação**: Integre a conversão de documentos em seus fluxos de trabalho e scripts automatizados.
- **Flexibilidade**: Lidar com vários formatos de documentos para garantir a compatibilidade com diferentes sistemas e aplicativos.

## Licenciamento

Enquanto o aplicativo ASPOPE.TEX Convert em si é gratuito para uso, a conversão de documentos requer um Aspose.TeX [License](/tex/{{lang.url-fragment}}net/licensing/) válido. Você pode comprar uma licença ou usar aspose.tex no modo de teste para fins de avaliação.

## Como instalar o conversor de linha de comando tex?

A ferramenta ASPPE.TEX Convert pode ser instalada globalmente ou localmente, dependendo das necessidades do seu projeto. Recomenda-se usar a instalação local para uso específico do projeto para evitar conflitos de versão.

### Instalação global

Para instalar o Aspose.TeX converte globalmente em sua máquina, use o seguinte comando:


```bash
dotnet tool install --global Aspose.TeX.Convert
```

Especifique a opção `--version` se você precisar de uma versão específica da ferramenta.

### Instalação local

Para a instalação local em um projeto específico, primeiro, navegue até o diretório raiz do seu projeto. Em seguida, execute os seguintes comandos:


1. Crie um manifesto de ferramentas, se ainda não estiver presente:

   ```bash
   dotnet new tool-manifest
   ```

2. Instale Aspose.TeX converta localmente:

   ```bash
   dotnet tool install Aspose.TeX.Convert --local
   ```

Novamente, você pode especificar a opção `--version` para uma versão específica.

### Atualizando o conversor Tex CLI

Para atualizar a ferramenta ASPPE.TEX Convert para a versão mais recente, use o comando `DotNet Tool Update` com `--global` ou `--local`, correspondendo ao seu tipo de instalação.

### Desinstalando o conversor da CLI Tex

Se você precisar desinstalar a ferramenta, use o comando `Dotnet Tool Uninstall` com `--global` ou `--local`, dependendo de como a ferramenta foi instalada.

## Uso

### Linha de comando

Converta seus documentos usando argumentos de linha de comando. Aqui estão os parâmetros disponíveis:


- `-i,--input [requerido]`: caminho para o documento de entrada tex ou LaTeX.
  - Example: `--input input.tex`
- `-o,--output [requerido]`: caminho para o documento convertido.
  - Example: `--output output.pdf`
- `-f,--format [Opcional]`: Formato do documento de saída.
  - Supported formats: PDF, XPS, PNG, JPEG, BMP, TIFF, SVG.
  - Example: `--format pdf`
- `-l, --license [opcional]`: caminho para o arquivo de licença Aspose.TeX .NET.
  - Example: `--license path_to_license.lic`
- `-V, --verbose [Opcional]`: Ativar saída detalhada.
  - Example: `--verbose`

Exemplo de uso da linha de comando:


```bash
Aspose.TeX.Convert --input input.tex --output output.pdf --format pdf
```

### Como integrar o conversor de LATEX da CLI em projetos C#?

O aplicativo Aspose.Tex Convert também pode ser integrado diretamente aos seus projetos .NET usando a linha de comando, permitindo o acesso programático aos recursos de conversão de TEX dentro do seu código C#.

**Adicionando o conversor da linha de comando do LATEX ao seu projeto:**

Para adicionar a ferramenta Aspose.TeX Converter ao seu projeto Visual Studio, acesse o diretório raiz do seu projeto e execute o seguinte comando:

```bash
dotnet Aspose.TeX.Convert add
```

Este comando adiciona a funcionalidade Aspose.TeX converte diretamente em seu projeto, permitindo que você use os métodos e propriedades da biblioteca através do seu código. Isso é particularmente útil para desenvolvedores que desejam implementar processos de conversão Tex personalizados diretamente em seus aplicativos.

### Use do código

Aqui está um exemplo de uso das ferramentas de CLI Aspose.TeX programaticamente no seu código C#:


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

Para obter mais informações e exemplos de uso, visite o [Aspose.TeX para documentação .NET](/tex/{{lang.url-fragment}}net/).