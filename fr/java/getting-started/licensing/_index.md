---
translation: true
template: /templates/_template-java.md
linktitle: Licence
title: Licences - Aspose.TeX pour Java
weight: 70
url: /java/licensing/
description: Lorsque vous vous êtes arrêté sur la version sous licence de la solution API Aspose.TeX pour Java, vous découvrez ici comment appliquer la licence.
lastmod: "2024-09-27"
---

{{<section overview>}}


### Limites de la version d'évaluation

La version d'évaluation d'Aspose.TeX (sans licence spécifiée) fournit toutes les fonctionnalités du produit, sauf que seules quatre premières pages peuvent être obtenues dans le document de sortie. De plus, ces pages seront estampillées d’un filigrane en mode évaluation.

Si vous souhaitez essayer Aspose.TeX sans limitations d'évaluation, demandez une licence temporaire de 30 jours. Veuillez vous référer à [Comment obtenir une licence temporaire ?](https://purchase.aspose.com/temporary-license/) pour plus d'informations.

### Appliquer la licence à l'aide d'un objet fichier ou flux

Utilisez la méthode [License.setLicense](https://reference.aspose.com/tex/java/com.aspose.tex/License#setLicense-java.lang.String-) pour obtenir une licence pour le composant. Le moyen le plus simple de définir une licence consiste à placer le fichier de licence dans le même dossier que *aspose.tex.jar* et à spécifier le nom du fichier, sans chemin, comme indiqué ci-dessous.

#### Chargement d'une licence à partir d'un fichier

Cet extrait de code initialise une licence stockée dans un fichier ou dans une ressource embarquée.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-LoadLicenseFromFile.java" >}}

#### Chargement d'une licence à partir d'un objet Stream

Ces extraits de code initialisent la licence à partir du flux.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-LoadLicenseFromStream.java" >}}

### Licence mesurée

Aspose.TeX dispose d'un mécanisme de licence alternatif appelé *Metered Licensing*. Si un client souhaite être facturé en fonction de l'utilisation des fonctionnalités de l'API, il peut appliquer une *Licence mesurée*, ce qui est en fait aussi simple que d'appliquer une paire de clés cryptographiques. Pour plus de détails, veuillez vous référer à la [Section FAQ sur les licences mesurées](https://purchase.aspose.com/faqs/licensing/metered/).

Les clés publiques et privées d'une licence mesurée peuvent être définies à l'aide d'une instance de la classe [*Metered*](https://reference.aspose.com/tex/net/aspose.tex/metered/), comme indiqué ci-dessous : 

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-SetMeteredLicense.java" >}}