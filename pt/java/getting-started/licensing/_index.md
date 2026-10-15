---
translation: true
template: /templates/_template-java.md
linktitle: Licenciamento
title: Licenciamento | Aspose.TeX para Java
weight: 70
url: /java/licensing/
description: Quando você parou na versão licenciada da solução da API Aspose.TeX para Java, aqui, você descobre como aplicar a licença.
lastmod: "2026-04-21"
---

{{<section overview>}}


### Limitações da versão de avaliação

A versão de avaliação do Aspose.TeX (sem uma licença especificada) fornece funcionalidade completa do produto, exceto que apenas até quatro primeiras páginas podem ser obtidas no documento de saída. Além disso, essas páginas serão carimbadas com uma marca d'água no modo de avaliação.

Se você deseja tentar o Aspose.TeX sem limitações de avaliação, solicite uma licença temporária de 30 dias. Consulte [como obter uma licença temporária?](https://purchase.aspose.com/temporary-license/) para obter mais informações.

### Aplique a licença usando o arquivo ou o objeto de fluxo

Use o método [License.setLicense](https://reference.aspose.com/tex/java/com.aspose.tex/license/#setLicense-java.lang.String-) para licenciar o componente. Nos exemplos abaixo, defina `licenseFilePath` como o caminho completo do arquivo de licença. O método que faz a chamada deve tratar ou declarar `Exception`.

#### Carregando uma licença do arquivo

Este trecho de código aplica uma licença armazenada em um arquivo.

{{< gist "aspose-com-gists" "2a6bdc66eff2968d36c7580d02721b14" "Example-SetLicenseFromFile.java" >}}

#### Carregando uma licença de um objeto de fluxo

Esses trechos de código inicializam a licença do fluxo.

{{< gist "aspose-com-gists" "2a6bdc66eff2968d36c7580d02721b14" "Example-SetLicenseFromStream.java" >}}

### Licença medida

Aspose.TeX possui um mecanismo de licenciamento alternativo chamado *licenciamento medido*. Se um cliente deseja ser cobrado com base no uso dos recursos da API, ele pode aplicar uma *licença medida *, que é realmente tão simples quanto aplicar um par de chaves criptográficas. Para mais detalhes, consulte a [seção de perguntas frequentes de licenciamento medido](https://purchase.aspose.com/faqs/licensing/metered/).

As chaves públicas e privadas de uma licença medida podem ser definidas usando uma instância da classe [*medida*](https://reference.aspose.com/tex/java/com.aspose.tex/metered/), como mostrado abaixo:

{{< gist "aspose-com-gists" "2a6bdc66eff2968d36c7580d02721b14" "Example-SetMeteredLicense.java" >}}