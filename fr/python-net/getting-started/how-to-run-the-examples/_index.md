---
translation: true
template: /templates/_template-python-net.md
linktitle: Comment exécuter les exemples
title: Comment exécuter les exemples | Aspose.TeX pour Python
weight: 80
url: /python-net/how-to-run-the-examples/
description: Cette page fournit toutes les exigences et étapes nécessaires pour exécuter les exemples de la solution Aspose.TeX pour Python.
lastmod: "2024-09-27"
---

{{<section overview>}}

## Conditions préalables

Avant de continuer, veuillez vous assurer que le dossier `Aspose.TeX-...` apparaît dans le dossier `[PYTHON_PATH]\Lib\site-packages\` après l'[installation du package Aspose.TeX](). Si Python 3.11 est installé, Aspose.TeX peut être installé dans le dossier `[PYTHON_PATH]\site-packages\`. Dans ce cas, vous devez copier le dossier Aspose.TeX dans le dossier `[PYTHON_PATH]\Lib\site-packages\`, car **PyCharm** (au moins la version 23.1) recherche les packages installés exactement à cet emplacement.

## Télécharger depuis GitHub

Tous les exemples d'Aspose.TeX pour Python sont disponibles sur [GitHub](https://GitHub.com/aspose-TeX/Aspose.TeX-for-Python-.NET). Vous avez deux options pour accéder aux exemples : vous pouvez soit cloner le référentiel à l'aide de votre client GitHub préféré, soit télécharger le fichier ZIP depuis [ici](https://GitHub.com/aspose-TeX/Aspose.TeX-for-Python-.NET/archive/master.zip). Extrayez le contenu du fichier ZIP dans n'importe quel dossier de votre ordinateur. Vous trouverez tous les exemples situés dans le dossier `Aspose.TeX.Examples`. Ci-dessous, nous montrerons comment créer et exécuter les exemples à l’aide d’IDE populaires.

Si vous rencontrez des problèmes lors de la configuration ou de l'exécution des exemples, n'hésitez pas à nous contacter via nos forums.

## PyCharm

Allez dans le menu ***Fichier*** et choisissez ***Ouvrir***. Sélectionnez le dossier de projet exemple et cliquez sur le bouton ***OK***. Le projet sera ouvert. Ensuite, allez dans le menu ***Exécuter*** et choisissez ***Modifier les configurations***. Dans le panneau de gauche, ajoutez une nouvelle configuration Python. Dans le panneau de droite, définissez le nom de la configuration (par exemple, "run_examples"). Spécifiez le chemin absolu vers `run_examples.py` dans le champ ***Chemin du script*** et le chemin absolu vers le dossier du projet dans le champ ***Répertoire de travail***.

Pour exécuter un exemple, allez simplement dans le menu ***Exécuter*** et choisissez ***Exécuter 'run_examples'***, ou utilisez le raccourci clavier `Shift+F10`. L'exemple sera exécuté et le résultat sera affiché dans la fenêtre de la console de PyCharm. Les fichiers de sortie générés lors de l'exécution des exemples se trouvent dans le dossier `output`.

## Microsoft Visual Studio

Assurez-vous que la fonctionnalité **Développement Python** est installée dans Visual Studio. Ouvrez Visual Studio et cliquez sur le côté droit de l'élément ***Ouvrir un dossier local***. Ensuite, accédez au dossier de projet des exemples Aspose.TeX. Visual Studio le reconnaîtra comme un projet Python et ouvrira l'IDE Python. Une fois le dossier ouvert, faites un clic droit sur "run_examples" dans l'Explorateur de solutions et sélectionnez ***Définir comme élément de démarrage***

Pour exécuter des exemples, cliquez simplement sur le bouton ***run_examples.py*** avec la flèche verte dans la barre d'outils de la fenêtre Visual Studio.

## Contribuer à Aspose.TeX pour Python

Si vous souhaitez contribuer au projet en ajoutant ou en améliorant un exemple, nous vous encourageons vivement à le faire. Tous les exemples et projets vitrines de ce référentiel sont open source et peuvent être librement utilisés dans vos applications.

Si vous souhaitez contribuer, vous pouvez créer un fork sur le référentiel, apporter des modifications au code source et créer une pull request. Nous examinerons les modifications et les inclurons dans le référentiel si elles sont jugées utiles.