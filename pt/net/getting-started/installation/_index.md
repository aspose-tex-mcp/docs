---
translation: true
template: /templates/_template-net.md
linktitle: Instalação
title: Instalação | Aspose.TeX para .NET
weight: 60
url: /net/installation/
description: A documentação da API do Aspose.TeX para .NET pode ser encontrada no pacote ZIP baixado ou obtido na Nuget Gallery, clicando no "Pacote de download".
lastmod: "2026-11-02"
---

{{<section overview>}}

## Escolher um pacote

O Aspose.TeX para .NET está disponível como dois pacotes NuGet com a mesma API:

- [Aspose.TeX](https://www.nuget.org/packages/Aspose.TeX) usa `System.Drawing.Common` e é executado no Windows.
- [Aspose.TeX.Drawing](https://www.nuget.org/packages/Aspose.TeX.Drawing) usa o back-end gráfico incorporado Aspose.Drawing e é executado no Windows, no Linux e no macOS, incluindo contêineres Docker.

Referencie apenas um deles. Para instalar um pacote com a CLI do .NET, execute um dos seguintes comandos na pasta do seu projeto:

```bash
dotnet add package Aspose.TeX
```

```bash
dotnet add package Aspose.TeX.Drawing
```

Consulte [Linux, macOS e Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/) para obter detalhes sobre `Aspose.TeX.Drawing`. O restante desta página descreve a instalação no Visual Studio e se aplica aos dois pacotes.

## Instalando Aspose.TeX para .Net através do NuGet

O NuGet é um sistema de gerenciamento de pacotes focado em desenvolvedores de código aberto e gratuito para a plataforma .NET que pretende simplificar o processo de incorporar bibliotecas de terceiros em um aplicativo .NET durante o desenvolvimento. É uma extensão do Visual Studio que facilita adicionar, remover e atualizar bibliotecas e ferramentas em projetos do Visual Studio que usam a estrutura .NET. Uma biblioteca ou ferramenta pode ser facilmente compartilhada com outros desenvolvedores, criando um pacote NuGet e armazenando -o dentro de um repositório NuGet. Quando você instala o pacote, o Nuget copia os arquivos para sua solução e automaticamente faz as alterações necessárias, como adicionar referências e alterar seus arquivos app.config ou web.config. Se você decidir remover a biblioteca, o NuGet remove os arquivos e reverte as alterações feitas em seu projeto para que não haja desordem.

### Referenciando aspose.tex para .NET

Tomando benefício desse recurso maravilhoso, nós incluímos as bibliotecas [Aspose.TeX para .NET](https://www.nuget.org/packages/Aspose.TeX) em um pacote NuGet e o carregamos em um repositório NuGet. Com esta opção, você se beneficia do uso do Aspose.TeX para .NET sem instalar este componente no seu sistema. O NuGet é executado no Visual Studio 2010 e na (s) versão (s) superior (s), o Visual Web Developer 2010 e o Windows Phone Developer Tools 7.1. Em nossos testes, testamos com o Visual Studio 2015 Ultimate.

Para começar:

1. Abra sua solução ou projeto no Visual Studio.
2. Adicione o Nuget Package Manager como uma extensão do Visual Studio:

    1. Selecione o menu **Ferramentas** e depois **Gestor de Extensões**.
    2. Selecione **Galeria Online** para obter uma lista completa dos pacotes disponíveis online.
    3. Selecione **Gestor de Pacotes NuGet**.
    4. Clique em **Descarregar**.
    5. Após a instalação do Gestor de Pacotes, reinicie o Visual Studio para que as alterações entrem em vigor.
   
      Após a instalação do Gestor de Pacotes NuGet, pode localizar, instalar, remover e atualizar pacotes na janela **Gerir Pacotes NuGet** ou utilizando os comandos de linha de comandos do PowerShell na janela dedicada da **Consola do Gestor de Pacotes** do Visual Studio. Ambas as opções podem ser encontradas se selecionar **Ferramentas** e depois **Gestor de Pacotes da Biblioteca**.

### Instale o pacote usando o Console do Gerenciador de Pacotes

Para fazer referência ao componente usando o console do gerenciador de pacotes:

1. Abra seu aplicativo .NET no Visual Studio.
2. No menu **Ferramentas**, selecione **Biblioteca Package Manager** e, em seguida, **Console do Gerenciador de Pacotes**.
3. Digite o comando “Install-Package Aspose.TeX” para instalar a versão completa mais recente ou digite o comando “Install-Package Aspose.TeX -prerelease” para instalar a versão mais recente, incluindo correções quentes.
4. Pressione **ENTER**.

### Pacote de atualização usando o console do gerenciador de pacotes

Se você já referenciou o componente através do NuGet, siga estas etapas para atualizar a referência à versão mais recente:

1. Abra seu aplicativo .NET no Visual Studio.
2. No menu **Ferramentas**, selecione **Biblioteca Package Manager**, seguido de **Console do gerenciador de pacotes** para abrir o console do gerenciador de pacotes.
3. Digite o comando “Update-Package Aspose.TeX” para fazer referência à versão completa mais recente ou digite o comando “Update-Package Aspose.TeX -prerelease” para instalar a versão mais recente, incluindo correções quentes.
4. Pressione **ENTER**.

### Instale o pacote usando a GUI do gerenciador de pacotes

Siga estas etapas para fazer referência ao componente usando a GUI do gerenciador de pacotes:

1. Abra você .NET APLICAÇÃO NO VISUAL ESTUDIO.
2. No menu **Ferramentas**, selecione **Biblioteca Package Manager** e **Gerencie pacotes NuGet** na opção **** **. 

    Também pode obter uma opção semelhante no Solution Explorer:
    1. Clique com o botão direito do rato no nome do projeto.
    2. Selecione **Gerir Pacotes NuGet**.

3. Selecione **online** no menu esquerdo.
4. TIPO **Aspose.TeX** Na caixa de pesquisa para encontrar aspose.tex para .NET.
5. Clique em **Instalar/atualizar** ao lado da versão mais recente do Aspose.TeX para .NET