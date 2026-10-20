---
translation: true
template: /templates/_template-java.md
title: Andere TeX-Konvertierungsausgabeformate | Java
linktitle: Andere TeX-Formate
weight: 18
url: /java/other-tex-formats/
description: Die Konvertierungsfunktion der Aspose.TeX-API für Java ermöglicht die Konvertierung von LaTeX-Dateien und Ihren eigenen benutzerdefinierten TeX-Dateien.
lastmod: "2026-04-21"
---

{{<section overview>}}

Es ist höchst unwahrscheinlich, dass Sie derzeit eine TeX-Datei konvertieren möchten, die in einem anderen Format als LaTeX geschrieben ist. Dies ist jedoch aus irgendeinem Grund möglich, wenn Sie die TeX-Sprache und/oder Interna studieren. Wie auch immer, **Aspose.TeX für Java** ermöglicht Ihnen die Konvertierung von Dateien, die im einfachen TeX-Format geschrieben wurden. Sie können damit auch benutzerdefinierte Formate erstellen und in diesen Formaten gestaltete Dokumente setzen.

Wir beginnen mit der Erstellung eines benutzerdefinierten Formats.

## Erstellen eines benutzerdefinierten Formats

Denken Sie daran, dass die Formatdatei ein binärer Speicherauszug des internen Zustands der TeX-Engine ist.

Setzen Sie `inputDirectory` auf einen Ordner mit `customtex.tex` und dessen Abhängigkeiten und `outputDirectory` auf einen vorhandenen Ausgabeordner. Die Formatquelle muss mit `\dump` enden; dieses Beispiel erstellt dort `customtex.fmt`. Importieren Sie die in den Beispielen verwendeten Aspose.TeX-Klassen sowie für den Textsatz `com.aspose.tex.rendering.XpsDevice`, `java.io.ByteArrayInputStream` und `java.nio.charset.StandardCharsets`. Die aufrufende Methode muss Ausnahmen behandeln oder deklarieren. Wenden Sie eine Lizenz gemäß dem [Lizenzleitfaden](/tex/{{lang.url-fragment}}java/licensing/) an, um Einschränkungen der Evaluierung zu vermeiden.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-CreateCustomTeXFormat.java" >}}

Wie Sie sehen, ähnelt der Code dem Code zum Konvertieren einer TeX-Datei. Aber es gibt ein paar Unterschiede.

Zunächst verwenden wir hier die Jobkonfiguration [TeXConfig.objectIniTeX()](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectIniTeX--) . Dies ist eine spezielle Konfiguration, die den Zustand der Engine „unberührt“ belässt, d. h. die internen Parameter haben ihre Standardwerte und der Satz von Steuersequenzen stimmt mit dem Satz von Grundelementen überein. In unserem Beispiel wird die Menge der Grundelemente in dem [hier](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) erwähnten Sinne erweitert.

Als nächstes richten wir wie gewohnt die Eingabe- und Ausgabearbeitsverzeichnisse ein. Das Eingabearbeitsverzeichnis muss die Hauptformatquelldatei und alle ihre Abhängigkeiten enthalten.

Und der zweite wesentliche Unterschied ist die Art und Weise, wie wir den Job ausführen. Dieses Mal verwenden wir die statische Methode [createFormat()](https://reference.aspose.com/tex/java/com.aspose.tex/texjob/#createFormat-java.lang.String-com.aspose.tex.TeXOptions-) , die zusammen mit den Optionen den Namen der Hauptquelldatei übernimmt, der mit dem Formatnamen identisch sein muss.

## Textsatz einer TeX-Datei in Ihrem benutzerdefinierten Format

Da wir nun über unser eigenes TeX-Format verfügen, möchten wir eine in diesem Format geschriebene TeX-Datei setzen. Hier ist der Code:

Setzen Sie `formatDirectory` auf den Ordner mit der zuvor erstellten Datei `customtex.fmt` und `outputDirectory` auf einen vorhandenen Ausgabeordner. Das Beispiel setzt einen eigenständigen Textstrom in `typeset-with-custom-format.xps`, daher ist kein Eingabearbeitsverzeichnis erforderlich. Legen Sie ein Eingabearbeitsverzeichnis fest, wenn die Haupteingabe Abhängigkeiten wie Bilder hat.

{{< gist "aspose-com-gists" "68af8199308bda28d9e6fa4670c0ba12" "Example-TypesetWithCustomTeXFormat.java" >}}

Natürlich müssen wir das Format irgendwie festlegen. Zunächst müssen wir eine Instanz der Klasse [FormatProvider](https://reference.aspose.com/tex/java/com.aspose.tex/formatprovider/) erstellen. Dann verwenden wir im Optionskonstruktor die Konfiguration [TeXConfig.objectTeX(FormatProvider)](https://reference.aspose.com/tex/java/com.aspose.tex/texconfig/#objectTeX-com.aspose.tex.FormatProvider-), die unseren Formatanbieter als Argument verwendet und das Format über den „jungfräulichen“ Zustand der Engine lädt.

Beide Beispiele werden ohne Benutzerinteraktion ausgeführt und erfassen die Terminalausgabe im Speicher. Das Textsatzbeispiel schließt nach dem Auftrag den Eingabestrom, gibt das XPS-Gerät frei und schließt das Arbeitsverzeichnis und den Formatanbieter. Diese Funktionen werden zuvor in diesem [Leitfaden](/tex/{{lang.url-fragment}}java/conversion/) erläutert.

## Textsatz einer TeX-Datei im Plain-TeX-Format

Wenn wir `TeXConfig.objectTeX()` ohne Formatanbieter verwenden, lädt die Engine das Standardformat, das im vierten Sinne [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) ist. Wenn Sie also eine TeX-Datei im einfachen TeX-Format geschrieben haben, können Sie sie auf diese Weise in jedes unterstützte Zielformat konvertieren.