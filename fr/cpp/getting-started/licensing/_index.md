---
translation: true
template: /templates/_template-cpp.md
title: Licences | Aspose.TeX pour C++
linktitle: Licence
weight: 70
url: /cpp/licensing/
description: Lorsque vous vous êtes arrêté sur la version sous licence de la solution API Aspose.TeX pour C++, vous découvrez ici comment appliquer la licence.
lastmod: "2026-04-20"
---

{{<section overview>}}

## Évaluer Aspose.TeX

Vous pouvez facilement télécharger le produit Aspose.TeX pour C++ à des fins d’évaluation. Veuillez vous référer à la [Page de téléchargement d'Aspose.TeX pour C++](https://www.nuget.org/packages/Aspose.TeX.Cpp/) pour connaître la dernière version. Le téléchargement d'évaluation est le même que le téléchargement acheté. La version d'évaluation devient simplement sous licence lorsque vous ajoutez quelques lignes de code pour appliquer la licence.

### Limites de la version d'évaluation

La version d'évaluation d'Aspose.TeX (sans licence spécifiée) fournit toutes les fonctionnalités du produit, sauf que seules quatre premières pages peuvent être obtenues dans le document de sortie. De plus, ces pages seront estampillées d’un filigrane en mode évaluation.

Si vous souhaitez essayer Aspose.TeX sans limitations d'évaluation, demandez une licence temporaire de 30 jours. Veuillez vous référer à [Comment obtenir une licence temporaire ?](https://purchase.aspose.com/temporary-license/) pour plus d'informations.

## Demander une licence

Une fois que vous êtes satisfait de votre évaluation d'Aspose.TeX pour C++, achetez une licence sur le site Web d'Aspose : [Purchase Portal](https://purchase.aspose.com/pricing?). Familiarisez-vous avec les différents types de licences disponibles. Si vous avez des questions, [contactez l'équipe commerciale Aspose](https://consulting.aspose.com/) et ils se feront un plaisir de vous aider.

Chaque licence Aspose comporte un abonnement d'un an pour des mises à niveau gratuites vers toute nouvelle version ou correctif publié pendant cette période. Nous fournissons une assistance technique gratuite et illimitée aux utilisateurs sous licence et en évaluation.

La licence est un fichier XML en texte brut qui contient des détails tels que le nom du produit, le nombre de développeurs sous licence, la date d'expiration de l'abonnement, etc. Le fichier est signé numériquement, ne modifiez donc pas le fichier : même l'ajout d'un saut de ligne supplémentaire au fichier l'invalide.

### Quand demander une licence

Suivez ces règles simples :

- La licence ne doit être définie qu'une seule fois par domaine d'application.
- Vous devez définir la licence avant d'utiliser d'autres classes Aspose :: TeX.
- Appeler SetLicense plusieurs fois n'est pas dangereux, mais fait perdre du temps au processeur.
- Si vous développez une application, appelez SetLicense dans le code de démarrage, avant d'utiliser les classes Aspose::TeX.
- Si vous développez une bibliothèque de classes, vous pouvez appeler SetLicense depuis un constructeur statique de la classe qui utilise Aspose::TeX. Le constructeur statique s'exécute avant la création d'une instance de votre classe en s'assurant que la licence Aspose::TeX est correctement définie.

### Appliquer la licence à l'aide d'un objet fichier ou flux

Utilisez la méthode [License::SetLicense](https://reference.aspose.com/tex/cpp/aspose.tex/license/) pour obtenir une licence pour le composant. Le moyen le plus simple de définir une licence consiste à placer le fichier de licence dans le même dossier que Aspose.TeX.dll et à spécifier le nom du fichier, sans chemin, comme indiqué ci-dessous.

#### Chargement d'une licence à partir d'un fichier

Cet extrait de code initialise une licence stockée dans un fichier ou dans une ressource embarquée.

{{< gist "aspose-com-gists" "d3eef38ac5b929503e8edee25e0873ce" "Aspose.TeX.Examples-LoadLicenseFromFile.cpp" >}}

#### Chargement d'une licence à partir d'un objet Stream

Ces extraits de code initialisent la licence à partir du flux.

{{< gist "aspose-com-gists" "d3eef38ac5b929503e8edee25e0873ce" "Aspose.TeX.Examples-LoadLicenseFromStream.cpp" >}}