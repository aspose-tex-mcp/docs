---
translation: true
template: /templates/_template-python-net.md
title: Alternatives pour fournir le fichier d'entrée TeX | Python
linktitle: Autres façons de fournir le fichier d'entrée TeX principal
weight: 14
url: /python-net/other-ways-of-main-input/
description: La solution API Aspose.TeX pour Python inclut un constructeur qui accepte un flux comme premier argument, fournissant une fonctionnalité de conversion.
lastmod: "2026-04-20"
---

{{<section overview>}}

## Fournir le fichier d'entrée principal au moteur TeX à l'aide d'un flux

Jusqu'à présent, nous avons seulement appris comment fournir le [fichier d'entrée principal](/tex/{{lang.url-fragment}}net/tex-io/#tex-input) au moteur TeX sous forme de nom de fichier, que ce soit sous sa forme complète ou sous une forme abrégée, avec ou sans extension. Cependant, il existe un [autre constructeur](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#io.RawIOBase-aspose.tex.presentation.Device-aspose.tex.TeXOptions) disponible dans la classe [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) qui accepte un flux comme premier argument. Ceci est utile si, pour une raison quelconque, le fichier d'entrée principal ne se présente pas sous la forme d'un fichier sur le système de fichiers du disque. Voici un exemple de la façon dont cela peut être mis en œuvre :

Définissez `ASPOSE_TEX_OUTPUT_DIR` sur le répertoire de sortie (par défaut : `output`). Appliquez d’abord une licence. [Licensing](/tex/fr/python-net/licensing/).

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-InputStream.py" >}}

Encodez un document LaTeX complet dans un flux binaire `BytesIO` et transmettez-le à `TeXJob` avec `TeXConfig.object_latex`. Gardez le flux ouvert pendant le travail. Résultat : `texput.xps` et `texput.log`.

Notez que tous les fichiers de sortie seront nommés « textut ». En effet, le moteur n’a accès à aucun autre nom. `texput` est le nom de travail par défaut. Vous pouvez trouver des informations plus détaillées sur les noms de tâches [Sortie TeX](/tex/{{lang.url-fragment}}net/tex-io/#tex-output) et [Comment définir le nom de la tâche](/tex/{{lang.url-fragment}}net/other-options/#how-to-set-the-job-name).

## Saisie du fichier d'entrée TeX principal via le terminal

Il y a [un constructeur supplémentaire](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/__init__/#aspose.tex.presentation.Device-aspose.tex.TeXOptions) disponible dans la classe [TeXJob](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/) qui ne nous permet pas du tout de spécifier l'entrée. Vous vous demandez peut-être ce que traiterait un tel travail TeX. Dans ce cas, nous aurions besoin d’utiliser un terminal d’entrée. Le moteur TeX nous demandera de saisir le nom du fichier depuis le terminal.

Voici le code :

{{< gist "aspose-com-gists" "edcfdfad622f09d57fa03bedd01e0e38" "Aspose.TeX.Examples-Conversion-MainInputTerminal.py" >}}

Enregistrez le texte plain TeX suivant dans `hello-world.tex`, sous `ASPOSE_TEX_INPUT_DIR` (par défaut : `input`). L’exemple utilise `TeXConfig.object_tex()`. À l’invite, saisissez `hello-world.tex` puis Entrée, ou fournissez ce nom via l’entrée standard. Résultat : `hello-world.xps` et `hello-world.log`.

```tex
Hello, World!
\end
```
