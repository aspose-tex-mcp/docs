---
translation: true
template: /templates/_template-cpp.md
title: Licenciamento | Aspose.TeX para C++
linktitle: Licenciamento
weight: 70
url: /cpp/licensing/
description: Quando você parou na versão licenciada da solução API Aspose.TeX para C ++ aqui, você descobre como aplicar a licença.
lastmod: "2025-06-16"
---

{{<section overview>}}

## Avalie Aspose.TeX

Você pode baixar facilmente o produto Aspose.TeX para C ++ para fins de avaliação. Consulte a página [Aspose.TeX para C ++](https://www.nuget.org/packages/Aspose.TeX.Cpp/) para descobrir a versão mais recente. O download da avaliação é o mesmo que o download adquirido. A versão de avaliação simplesmente fica licenciada quando você adiciona algumas linhas de código para aplicar a licença.

### Limitações da versão de avaliação

A versão de avaliação do Aspose.TeX (sem uma licença especificada) fornece funcionalidade completa do produto, exceto que apenas até quatro primeiras páginas podem ser obtidas no documento de saída. Além disso, essas páginas serão carimbadas com uma marca d'água no modo de avaliação.

Se você deseja tentar o Aspose.TeX sem limitações de avaliação, solicite uma licença temporária de 30 dias. Consulte [como obter uma licença temporária?](https://purchase.aspose.com/temporary-license/) para obter mais informações.

## Aplicando uma licença

Quando estiver satisfeito com a sua avaliação do Aspose.TeX para C++, compre uma licença no site da Aspose: [Portal de Compras](http://www.aspose.com/purchase/default.aspx). Familiarize-se com os diferentes tipos de licença disponíveis. Em caso de dúvidas, [contacte a equipa de vendas da Aspose](http://www.aspose.com/corporate/contact/default.aspx) e eles terão todo o gosto em ajudar.

Cada licença Aspose possui uma assinatura de um ano para atualizações gratuitas para novas versões ou correções que serão lançadas durante esse período. Fornecemos suporte técnico gratuito e ilimitado aos usuários licenciados e de avaliação.

A licença é um arquivo XML de texto sem formatação que contém detalhes como o nome do produto, o número de desenvolvedores licenciados, a data de expiração da assinatura e assim por diante. O arquivo é assinado digitalmente, portanto, não modifique o arquivo: mesmo adicionar uma quebra de linha extra ao arquivo o invalida.

### Quando aplicar uma licença

Siga estas regras simples:

- A licença precisa ser definida apenas uma vez por domínio do aplicativo.
- Você precisa definir a licença antes de usar qualquer outra aula de Aspose :: Tex.
- Chamar Setlicense várias vezes não é prejudicial, mas resíduos de tempo do processador.
- Se você estiver desenvolvendo um aplicativo, ligue para o Setlicense no código de inicialização, antes de usar as classes Aspose :: Tex.
- Se você estiver desenvolvendo uma biblioteca de classes, poderá chamar o Setlicense de um construtor estático da classe que usa Aspose :: tex. O construtor estático é executado antes que uma instância da sua classe seja criada, certificando -se de que o Aspose :: Tex License esteja definido corretamente.

### Aplique a licença usando o arquivo ou o objeto de fluxo

Use o método [License :: setLicense](https://reference.aspose.com/tex/cpp/class/aspose.te_x.license) para licenciar o componente. A maneira mais fácil de definir uma licença é colocar o arquivo de licença na mesma pasta que o Aspose.TeX.dll e especificar o nome do arquivo, sem um caminho, como mostrado abaixo.

#### Carregando uma licença do arquivo

Este snippet de código inicializa uma licença armazenada em um arquivo ou em um recurso incorporado.

{{< gist "aspose-com-gists" "d3eef38ac5b929503e8edee25e0873ce" "Aspose.TeX.Examples-LoadLicenseFromFile.cpp" >}}

#### Carregando uma licença de um objeto de fluxo

Esses trechos de código inicializam a licença do fluxo.

{{< gist "aspose-com-gists" "d3eef38ac5b929503e8edee25e0873ce" "Aspose.TeX.Examples-LoadLicenseFromStream.cpp" >}}