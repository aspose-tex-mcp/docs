---
translation: true
template: /templates/_template-python-net.md
title: Andere TeX-Konvertierungsausgabeformate | Python
linktitle: Andere TeX-Formate
weight: 18
url: /python-net/other-tex-formats/
description: Aspose.TeX für Python bietet Funktionen, mit denen Sie LaTeX-Dateien und benutzerdefinierte TeX-Dateien konvertieren können. Hier sind Codebeispiele.
lastmod: "2024-09-26"
---

{{<section overview>}}

Es ist unwahrscheinlich, dass Sie derzeit eine TeX-Datei konvertieren müssen, die in einem anderen Format als LaTeX geschrieben ist. Wenn Sie jedoch aus irgendeinem Grund die TeX-Sprache oder die Interna von TeX studieren, ist dies immer noch möglich. In jedem Fall können Sie mit **Aspose.TeX für Python** Dateien konvertieren, die im *Plain TeX*-Format geschrieben wurden, und außerdem benutzerdefinierte Formate erstellen und Dokumente setzen, die in diesen Formaten entworfen wurden.

Zunächst erstellen wir ein benutzerdefiniertes Format.

## Erstellen eines benutzerdefinierten Formats

Bedenken Sie, dass die Formatdatei eine binäre Darstellung des internen Zustands der TeX-Engine ist.

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-CreateCustomTeXFormatFile.py" >}}

Wie Sie sehen, ähnelt der Code dem Code zum Konvertieren einer TeX-Datei. Es gibt jedoch einige Unterschiede.

In diesem Fall verwenden wir zunächst die Jobkonfiguration [TeXConfig.object_ini_tex](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_ini_tex/). Diese Konfiguration stellt sicher, dass der Zustand der Engine „jungfräulich“ ist, was bedeutet, dass die internen Parameter ihre Standardwerte haben und der Satz von Steuersequenzen mit dem Satz von Grundelementen übereinstimmt. In unserem Beispiel wird der Satz von Grundelementen erweitert [im Aspose.TeX- und Object TeX-Artikel](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex).

Anschließend richten wir wie gewohnt die Eingabe- und Ausgabearbeitsverzeichnisse ein. Das Eingabearbeitsverzeichnis sollte die Quelldatei des Hauptformats und alle ihre Abhängigkeiten enthalten.

Und der zweite große Unterschied ist die Methode, mit der wir den Job ausführen. In diesem Fall verwenden wir die statische Methode [create_format()](https://reference.aspose.com/tex/python-net/aspose.tex/texjob/create_format/#str-aspose.tex.TeXOptions), die in Verbindung mit den Optionen erfordert, dass der Name der Hauptquelldatei mit dem Formatnamen identisch ist.

## Textsatz einer TeX-Datei in Ihrem benutzerdefinierten Format

Nachdem wir nun unser eigenes TeX-Format erstellt haben, können wir mit dem Satz einer in diesem Format geschriebenen TeX-Datei fortfahren. Hier ist der Code:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-TypesetWithCustomTeXFormat.py" >}}

Um das Format anzugeben, müssen wir eine Instanz der Klasse [FormatProvider](https://reference.aspose.com/tex/python-net/aspose.tex.resourceproviders/formatprovider/) erstellen. Im Optionskonstruktor verwenden wir die Konfiguration [TeXConfig.object_tex()](https://reference.aspose.com/tex/python-net/aspose.tex/texconfig/object_tex/#aspose.tex.resourceproviders.FormatProvider), die unseren Formatanbieter als Argument benötigt und das Format über den „jungfräulichen“ Zustand der Engine lädt.

Der verbleibende Code sollte Ihnen bekannt sein, da er die Funktionen nutzt, die zuvor in diesem [Leitfaden](/tex/{{lang.url-fragment}}net/conversion/) besprochen wurden.

## Textsatz einer TeX-Datei im Plain-TeX-Format

Wenn wir den Formatanbieter aus dem oben gezeigten Code entfernen, lädt die Engine das Standardformat, das im vierten Sinne [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) ist. Wenn Sie also eine TeX-Datei im Plain-TeX-Format geschrieben haben, können Sie sie mit diesem Ansatz in jedes unterstützte Zielformat konvertieren.