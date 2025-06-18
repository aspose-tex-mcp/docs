---
translation: true
template: /templates/_template-java.md
linktitle: Licenciamento
title: Licenciamento - Aspose.TeX para java
weight: 70
url: /java/licensing/
description: Quando você parou na versão licenciada da solução da API Aspose.TeX para Java, aqui, você descobre como aplicar a licença.
lastmod: "2025-06-16"
---

{{<section overview>}}


### Limitações da versão de avaliação

A versão de avaliação do Aspose.TeX (sem uma licença especificada) fornece funcionalidade completa do produto, exceto que apenas até quatro primeiras páginas podem ser obtidas no documento de saída. Além disso, essas páginas serão carimbadas com uma marca d'água no modo de avaliação.

Se você deseja tentar o Aspose.TeX sem limitações de avaliação, solicite uma licença temporária de 30 dias. Consulte [como obter uma licença temporária?](https://purchase.aspose.com/temporary-license/) para obter mais informações.

### Aplique a licença usando o arquivo ou o objeto de fluxo

Use o método [Licença.Setlicense](https://reference.aspose.com/tex/java/com.aspose.tex/License#setLicense-java.lang.String-) para licenciar o componente. A maneira mais fácil de definir uma licença é colocar o arquivo de licença na mesma pasta que o * aspose.tex.jar * e especificar o nome do arquivo, sem um caminho, como mostrado abaixo.

#### Carregando uma licença do arquivo

Este snippet de código inicializa uma licença armazenada em um arquivo ou em um recurso incorporado.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-LoadLicenseFromFile.java" >}}

#### Carregando uma licença de um objeto de fluxo

Esses trechos de código inicializam a licença do fluxo.

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-LoadLicenseFromStream.java" >}}

### Licença medida

Aspose.TeX possui um mecanismo de licenciamento alternativo chamado *licenciamento medido*. Se um cliente deseja ser cobrado com base no uso dos recursos da API, ele pode aplicar uma *licença medida *, que é realmente tão simples quanto aplicar um par de chaves criptográficas. Para mais detalhes, consulte a [seção de perguntas frequentes de licenciamento medido](https://purchase.aspose.com/faqs/licensing/metered/).

As chaves públicas e privadas de uma licença medida podem ser definidas usando uma instância da classe [*medida*](https://reference.aspose.com/tex/net/aspose.tex/metered/), como mostrado abaixo: 

{{< gist "aspose-com-gists" "67385c777283964d328086603f691ac9" "Aspose.TeX.Examples-SetMeteredLicense.java" >}}