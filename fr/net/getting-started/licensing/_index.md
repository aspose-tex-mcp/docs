---
translation: true
template: /templates/_template-net.md
linktitle: Licence
title: Licences | Aspose.TeX pour .NET
weight: 70
url: /net/licensing/
description: Lorsque vous vous êtes arrêté sur la version sous licence de la solution API Aspose.TeX pour .NET, vous découvrez ici comment appliquer la licence.
lastmod: "2026-04-22"
---

{{<section overview>}}

## Évaluer Aspose.TeX

Vous pouvez facilement télécharger le produit Aspose.TeX pour .NET à des fins d’évaluation. Veuillez vous référer à la [page de téléchargement Aspose.TeX pour .NET](https://www.nuget.org/packages/Aspose.TeX/) pour connaître la dernière version. Le téléchargement d'évaluation est le même que le téléchargement acheté. La version d'évaluation devient simplement sous licence lorsque vous ajoutez quelques lignes de code pour appliquer la licence.

### Limites de la version d'évaluation

La version d'évaluation d'Aspose.TeX (sans licence spécifiée) fournit toutes les fonctionnalités du produit, sauf que seules quatre premières pages peuvent être obtenues dans le document de sortie. De plus, ces pages seront estampillées d’un filigrane en mode évaluation.

Si vous souhaitez essayer Aspose.TeX sans limitations d'évaluation, demandez une licence temporaire de 30 jours. Veuillez vous référer à [Comment obtenir une licence temporaire ?](https://purchase.aspose.com/temporary-license/) pour plus d'informations.

## Demander une licence

Une fois que vous êtes satisfait de votre évaluation d'Aspose.TeX pour .NET, achetez une licence sur le site Web d'Aspose : [Purchase Portal](https://purchase.aspose.com/pricing?). Familiarisez-vous avec les différents types de licences disponibles. Si vous avez des questions, [contactez l'équipe commerciale Aspose](https://consulting.aspose.com/) et ils se feront un plaisir de vous aider.

Chaque licence Aspose comporte un abonnement d'un an pour des mises à niveau gratuites vers toute nouvelle version ou correctif publié pendant cette période. Nous fournissons une assistance technique gratuite et illimitée aux utilisateurs sous licence et en évaluation.

La licence est un fichier XML en texte brut qui contient des détails tels que le nom du produit, le nombre de développeurs sous licence, la date d'expiration de l'abonnement, etc. Le fichier est signé numériquement, ne modifiez donc pas le fichier : même l'ajout d'un saut de ligne supplémentaire au fichier l'invalide.

### Quand demander une licence

Suivez ces règles simples :

- La licence ne doit être définie qu'une seule fois par domaine d'application.
- Vous devez définir la licence avant d'utiliser d'autres classes Aspose.TeX.
- Appeler SetLicense plusieurs fois n'est pas dangereux, mais fait perdre du temps au processeur.
- Si vous développez une application Windows Forms ou console, appelez SetLicense dans le code de démarrage, avant d'utiliser les classes Aspose.TeX.
- Lors du développement d'une application ASP.NET, appelez SetLicense depuis le fichier Global.asax.cs, dans la méthode protégée Application_Start. Il est appelé une fois au démarrage de l'application.
- N'appelez pas SetLicense depuis les méthodes Page_Load car cela signifie que la licence sera chargée à chaque fois qu'une page Web est chargée.
- Si vous développez une bibliothèque de classes, vous pouvez appeler SetLicense depuis un constructeur statique de la classe qui utilise Aspose.TeX. Le constructeur statique s'exécute avant la création d'une instance de votre classe en s'assurant que la licence Aspose.TeX est correctement définie.

### Appliquer la licence à l'aide d'un objet fichier ou flux

Utilisez la méthode [License.SetLicense](https://reference.aspose.com/tex/net/aspose.tex/license/) pour obtenir une licence pour le composant. Le moyen le plus simple de définir une licence consiste à placer le fichier de licence dans le même dossier que *Aspose.TeX.dll* et à spécifier le nom du fichier, sans chemin, comme indiqué ci-dessous.

#### Chargement d'une licence à partir d'un fichier

Cet extrait de code initialise une licence stockée dans un fichier ou dans une ressource embarquée.

{{< gist "aspose-com-gists" "366cba3dc08d43c99c22bb33ecb5d555" "Example-SetLicenseFromFile.cs" >}}

#### Chargement d'une licence à partir d'un objet Stream

Ces extraits de code initialisent la licence à partir du flux.

{{< gist "aspose-com-gists" "366cba3dc08d43c99c22bb33ecb5d555" "Example-SetLicenseFromStream.cs" >}}

### Licence mesurée

Aspose.TeX dispose d'un mécanisme de licence alternatif. Les clients qui souhaitent être facturés en fonction de l'utilisation des fonctionnalités de l'API peuvent utiliser *Metered Licensing*. Appliquer une *Licence mesurée* est en fait aussi simple que d'appliquer une paire de clés cryptographiques. Pour plus de détails, veuillez vous référer à la [Section FAQ sur les licences mesurées](https://purchase.aspose.com/faqs/licensing/metered/).

Les clés publiques et privées d'une licence mesurée sont définies à l'aide d'une instance de la classe [*Metered*](https://reference.aspose.com/tex/net/aspose.tex/metered/), comme indiqué dans l'exemple suivant : 

{{< gist "aspose-com-gists" "366cba3dc08d43c99c22bb33ecb5d555" "Example-SetMeteredLicense.cs" >}}
