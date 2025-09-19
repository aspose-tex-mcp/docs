---
translation: true
template: /templates/_template-python-net.md
linktitle: Licenciamento
title: Licenciamento | Aspose.TeX for Python via .NET
weight: 70
url: /python-net/licensing/
description: Se você estiver usando a versão licenciada da solução API Aspose.TeX para Python, poderá aprender aqui como aplicar a licença.
lastmod: "2025-06-16"
---

{{<section overview>}}

## Avalie Aspose.TeX

Para avaliar o Aspose.TeX para Python, você pode fazer o download facilmente do produto do [Aspose.TeX for python Download Page](https://pypi.org/project/aspose-tex-net/). A versão de avaliação é a mesma da versão adquirida. Ao adicionar algumas linhas de código para aplicar a licença, a versão de avaliação é licenciada. Consulte a página de download para obter a versão mais recente.

### Limitações da versão de avaliação

A versão de avaliação do Aspose.TeX fornece funcionalidade completa do produto, com a exceção de que apenas as quatro primeiras páginas podem ser obtidas no documento de saída. Além disso, essas páginas serão carimbadas com uma marca d'água no modo de avaliação.

Se você deseja tentar aspose.tex sem essas limitações de avaliação, você pode [solicitar uma licença temporária de 30 dias](https://purchase.aspose.com/temporary-license/) que você testará todos os aspectos de um produto antes de comprá-lo.

## Aplicando uma licença

Depois de concluir sua avaliação do Aspose.TeX para Python e ficar satisfeito com seu desempenho, você pode comprar uma licença no site da Aspose no [Portal de compra](http://www.aspose.com/purchase/default.aspx). Recomenda -se familiarizar -se com os diferentes tipos de licença disponíveis antes de fazer uma compra. Se você tiver alguma dúvida ou precisar de assistência, não hesite em [entrar em contato com a equipe de vendas Aspose](http://www.aspose.com/corporate/contact/default.aspx), pois eles ficarão mais do que felizes em ajudá -lo.

Cada licença Aspose inclui uma assinatura de um ano que o autoriza a liberar atualizações para novas versões ou correções divulgadas durante esse período. Também oferecemos suporte técnico gratuito e ilimitado aos usuários licenciados e de avaliação.

A licença para Aspose é um arquivo XML de texto simples que inclui informações como o nome do produto, o número de desenvolvedores licenciados e a data de vencimento da assinatura. É importante não modificar o arquivo à medida que é assinado digitalmente, e até adicionar uma quebra de linha extra o invalidará.

### Quando aplicar uma licença

Siga estas diretrizes:

- A licença precisa ser definida apenas uma vez por domínio do aplicativo.
- Defina a licença antes de usar outras classes Aspose.TeX.
- Chamar `setlicense` várias vezes não é prejudicial, mas resíduos de tempo do processador.

#### Carregando uma licença do arquivo

O snippet de código a seguir demonstra como inicializar uma licença armazenada em um arquivo.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-LoadLicenseFromFile.py" >}}

#### Carregando uma licença de um objeto de fluxo

O próximo código inicializa a licença de um fluxo.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-LoadLicenseFromStream.py" >}}

### Licença medida

A Aspose.TeX oferece um mecanismo de licenciamento alternativo chamado *Licenciamento medido *, que permite que os clientes sejam cobrados com base no uso dos recursos da API. A aplicação de uma * licença medida * é tão simples quanto aplicar um par de chaves criptográficas. Para obter mais informações, consulte a seção [FAQ de licenciamento medido](https://purchase.aspose.com/faqs/licensing/metered/).

Para definir as chaves públicas e privadas de uma licença medida, pode utilizar uma instância da classe [*Metered*](https://reference.aspose.com/tex/python-net/aspose.tex/metered/), como se mostra no exemplo seguinte:

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-SetMeteredLicense.py" >}}