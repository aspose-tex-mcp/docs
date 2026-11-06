---
translation: true
template: /templates/_template-python-net.md
linktitle: Licence
title: Licences | Aspose.TeX pour Python
weight: 70
url: /python-net/licensing/
description: Si vous utilisez la version sous licence de la solution API Aspose.TeX pour Python, vous pouvez apprendre ici comment appliquer la licence.
lastmod: "2024-09-27"
---

{{<section overview>}}

## Évaluer Aspose.TeX

Pour évaluer Aspose.TeX pour Python, vous pouvez facilement télécharger le produit à partir de la [Page de téléchargement d'Aspose.TeX pour Python](https://pypi.org/project/aspose-tex-net/). La version d'évaluation est la même que la version achetée. En ajoutant quelques lignes de code pour appliquer la licence, la version d'évaluation devient sous licence. Veuillez vous référer à la page de téléchargement pour la dernière version.

### Limites de la version d'évaluation

La version d'évaluation d'Aspose.TeX fournit toutes les fonctionnalités du produit, à l'exception du fait que seules les quatre premières pages peuvent être obtenues dans le document de sortie. De plus, ces pages seront estampillées d’un filigrane en mode évaluation.

Si vous souhaitez essayer Aspose.TeX sans ces limitations d'évaluation, vous pouvez [demander une licence temporaire de 30 jours](https://purchase.aspose.com/temporary-license/) qui vous permettra de tester tous les aspects d'un produit avant de l'acheter.

## Demander une licence

Une fois que vous avez terminé votre évaluation d'Aspose.TeX pour Python et que vous êtes satisfait de ses performances, vous pouvez acheter une licence via le site Web Aspose sur le [Portail d'achat](https://purchase.aspose.com/pricing?). Il est recommandé de vous familiariser avec les différents types de licences disponibles avant de procéder à un achat. Si vous avez des questions ou avez besoin d'aide, n'hésitez pas à [contacter l'équipe commerciale Aspose](https://consulting.aspose.com/), car ils se feront un plaisir de vous aider.

Chaque licence Aspose comprend un abonnement d'un an qui vous donne droit à des mises à niveau gratuites vers toute nouvelle version ou correctif publié au cours de cette période. Nous offrons également une assistance technique gratuite et illimitée aux utilisateurs sous licence et en évaluation.

La licence pour Aspose est un fichier XML en texte brut qui comprend des informations telles que le nom du produit, le nombre de développeurs sous licence et la date d'expiration de l'abonnement. Il est important de ne pas modifier le fichier car il est signé numériquement, et même l'ajout d'un saut de ligne supplémentaire l'invalidera.

### Quand demander une licence

Veuillez suivre ces directives :

- La licence ne doit être définie qu'une seule fois par domaine d'application.
- Définissez la licence avant d'utiliser d'autres classes Aspose.TeX.
- Appeler `set_license` plusieurs fois n'est pas dangereux mais fait perdre du temps au processeur.

#### Chargement d'une licence à partir d'un fichier

Appliquez la licence avant d’utiliser les autres classes Aspose.TeX. Définissez `ASPOSE_TEX_PYTHON_NET_LICENSE_PATH` sur le chemin de la licence ou placez `Aspose.TeX.Python-net.lic` dans le répertoire de travail.

{{< gist "aspose-com-gists" "593d1652856be08ad2ec145fbe3796a2" "Aspose.TeX.Examples-LoadLicenseFromFile.py" >}}

#### Chargement d'une licence à partir d'un objet Stream

L’exemple suivant ouvre le fichier de licence sous forme de flux binaire et le ferme après l’application de la licence. Il utilise le même paramètre de chemin que l’exemple avec un fichier.

{{< gist "aspose-com-gists" "593d1652856be08ad2ec145fbe3796a2" "Aspose.TeX.Examples-LoadLicenseFromStream.py" >}}

### Licence mesurée

Aspose.TeX propose un mécanisme de licence alternatif appelé *Metered Licensing*, qui permet aux clients d'être facturés en fonction de leur utilisation des fonctionnalités de l'API. Appliquer une *Licence mesurée* est aussi simple que d'appliquer une paire de clés cryptographiques. Pour plus d'informations, veuillez vous référer à la [Section FAQ sur les licences mesurées](https://purchase.aspose.com/faqs/licensing/metered/).

Pour définir les clés publiques et privées d'une licence limitée, vous pouvez utiliser une instance de la classe [*Metered*](https://reference.aspose.com/tex/python-net/aspose.tex/metered/), comme indiqué dans l'exemple suivant : Fournissez vos clés via `ASPOSE_TEX_METERED_PUBLIC_KEY` et `ASPOSE_TEX_METERED_PRIVATE_KEY`.

{{< gist "aspose-com-gists" "593d1652856be08ad2ec145fbe3796a2" "Aspose.TeX.Examples-SetMeteredLicense.py" >}}