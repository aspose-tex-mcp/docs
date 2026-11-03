---
translation: true
template: /templates/_template-net.md
linktitle: Licenciamento
title: Licenciamento | Aspose.TeX para .NET
weight: 70
url: /net/licensing/
description: Quando você parou na versão licenciada da solução API Aspose.TeX para .NET aqui, você descobre como aplicar a licença.
lastmod: "2026-11-02"
---

{{<section overview>}}

## Avalie Aspose.TeX

Você pode fazer o download facilmente do Aspose.TeX para o .NET Product para fins de avaliação. Consulte a página [Aspose.TeX para .NET Download](https://www.nuget.org/packages/Aspose.TeX/) para descobrir a versão mais recente. O download da avaliação é o mesmo que o download adquirido. A versão de avaliação simplesmente fica licenciada quando você adiciona algumas linhas de código para aplicar a licença.

### Limitações da versão de avaliação

A versão de avaliação do Aspose.TeX (sem uma licença especificada) fornece funcionalidade completa do produto, exceto que apenas até quatro primeiras páginas podem ser obtidas no documento de saída. Além disso, essas páginas serão carimbadas com uma marca d'água no modo de avaliação.

Se você usar o pacote `Aspose.TeX.Drawing`, a saída rasterizada (PNG, JPEG, BMP, TIFF) no modo de avaliação também traz uma marca d'água "Evaluation only Aspose.Drawing" do back-end gráfico incorporado. A licença do Aspose.TeX remove as duas marcas d'água; não é necessária uma licença separada do Aspose.Drawing. Consulte [Linux, macOS e Docker](/tex/{{lang.url-fragment}}net/linux-and-containers/#licensing).

Se você deseja tentar o Aspose.TeX sem limitações de avaliação, solicite uma licença temporária de 30 dias. Consulte [como obter uma licença temporária?](https://purchase.aspose.com/temporary-license/) para obter mais informações.

## Aplicando uma licença

Quando estiver satisfeito com a sua avaliação do Aspose.TeX para .NET, adquira uma licença no site da Aspose: [Portal de Compras](https://purchase.aspose.com/pricing?). Familiarize-se com os diferentes tipos de licença disponíveis. Em caso de dúvidas, [contacte a equipa de vendas da Aspose](https://consulting.aspose.com/) e eles terão todo o gosto em ajudar.

Cada licença Aspose possui uma assinatura de um ano para atualizações gratuitas para novas versões ou correções que serão lançadas durante esse período. Fornecemos suporte técnico gratuito e ilimitado aos usuários licenciados e de avaliação.

A licença é um arquivo XML de texto sem formatação que contém detalhes como o nome do produto, o número de desenvolvedores licenciados, a data de expiração da assinatura e assim por diante. O arquivo é assinado digitalmente, portanto, não modifique o arquivo: mesmo adicionar uma quebra de linha extra ao arquivo o invalida.

### Quando aplicar uma licença

Siga estas regras simples:

- A licença precisa ser definida apenas uma vez por domínio do aplicativo.
- Você precisa definir a licença antes de usar outras classes Aspose.TeX.
- Chamar SetLicense várias vezes não é prejudicial, mas resíduos de tempo do processador.
- Se você estiver desenvolvendo um formulário do Windows ou um aplicativo de console, ligue para o SetLicense no código de inicialização, antes de usar as classes Aspose.TeX.
- Ao desenvolver um aplicativo ASP.NET, chame o SetLicense do arquivo global.asax.cs, no método protegido da Application_Start. É chamado uma vez quando o aplicativo é iniciado.
- Não ligue para os métodos Page_Load, pois significa que a licença será carregada sempre que uma página da web for carregada.
- Se você estiver desenvolvendo uma biblioteca de classes, poderá chamar SetLicense de um construtor estático da classe que utiliza Aspose.TeX. O construtor estático é executado antes que uma instância da sua classe seja criada, certificando-se de que a licença Aspose.TeX seja definida corretamente.

### Aplique a licença usando o arquivo ou o objeto de fluxo

Use o método [Licença.SetLicense](https://reference.aspose.com/tex/net/aspose.tex/license/) para licenciar o componente. A maneira mais fácil de definir uma licença é colocar o arquivo de licença na mesma pasta que o *Aspose.TeX.dll* e especificar o nome do arquivo, sem um caminho, como mostrado abaixo.

#### Carregando uma licença do arquivo

Este snippet de código inicializa uma licença armazenada em um arquivo ou em um recurso incorporado.

{{< gist "aspose-com-gists" "366cba3dc08d43c99c22bb33ecb5d555" "Example-SetLicenseFromFile.cs" >}}

#### Carregando uma licença de um objeto de fluxo

Esses trechos de código inicializam a licença do fluxo.

{{< gist "aspose-com-gists" "366cba3dc08d43c99c22bb33ecb5d555" "Example-SetLicenseFromStream.cs" >}}

### Licença medida
Aspose.TeX possui um mecanismo de licenciamento alternativo. Os clientes que desejam ser cobrados com base no uso dos recursos da API podem usar *licenciamento medido *. A aplicação de uma * licença medida * é realmente tão simples quanto aplicar um par de chaves criptográficas. Para mais detalhes, consulte [Seção de perguntas frequentes de licenciamento medido](https://purchase.aspose.com/faqs/licensing/metered/).

As chaves públicas e privadas de uma licença medida são definidas usando uma instância da classe [*medida*](https://reference.aspose.com/tex/net/aspose.tex/metered/), como mostrado no exemplo a seguir: 

{{< gist "aspose-com-gists" "366cba3dc08d43c99c22bb33ecb5d555" "Example-SetMeteredLicense.cs" >}}
