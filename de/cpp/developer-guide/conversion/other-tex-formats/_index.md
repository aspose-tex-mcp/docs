---
translation: true
template: /templates/_template-cpp.md
title: Andere TeX-Konvertierungsausgabeformate | C++
linktitle: Andere TeX-Formate
weight: 18
url: /cpp/other-tex-formats/
description: Die Konvertierungsfunktion der Aspose.TeX-Lösung für C++ ermöglicht die Konvertierung von LaTeX-Dateien und Ihren eigenen benutzerdefinierten TeX-Dateien. Hier sind einige Codebeispiele.
lastmod: "2026-04-20"
---

{{<section overview>}}

Es ist höchst unwahrscheinlich, dass Sie derzeit eine TeX-Datei konvertieren möchten, die in einem anderen Format als LaTeX geschrieben ist. Dies ist jedoch aus irgendeinem Grund möglich, wenn Sie die TeX-Sprache und/oder Interna studieren. Wie auch immer, **Aspose.TeX für C++** ermöglicht Ihnen die Konvertierung von Dateien, die im einfachen TeX-Format geschrieben wurden. Sie können damit auch benutzerdefinierte Formate erstellen und in diesen Formaten gestaltete Dokumente setzen.

Wir beginnen mit der Erstellung eines benutzerdefinierten Formats.

## Erstellen eines benutzerdefinierten Formats

Denken Sie daran, dass die Formatdatei ein binärer Speicherauszug des internen Zustands der TeX-Engine ist.

```C++
// Create typesetting options for no format on ObjectTeX engine extension.
System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::get_ObjectIniTeX());
// Specify a file system working directory for input.
options->set_InputWorkingDirectory(System::MakeObject<InputFileSystemDirectory>(RunExamples::InputDirectory));
// Specify a file system working directory for output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
    
// Run format creation.
Aspose::TeX::TeXJob::CreateFormat(u"customtex", options);
    
// For further output to look write.
options->get_TerminalOut()->get_Writer()->WriteLine();
```

Wie Sie sehen, ähnelt der Code dem Code zum Konvertieren einer TeX-Datei. Aber es gibt ein paar Unterschiede.

Zunächst verwenden wir hier die Jobkonfiguration [TeXConfig.ObjectIniTeX](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e). Dies ist eine spezielle Konfiguration, die den Zustand der Engine „unberührt“ belässt, d. h. die internen Parameter haben ihre Standardwerte und der Satz von Steuersequenzen stimmt mit dem Satz von Grundelementen überein. In unserem Beispiel wird die Menge der Grundelemente in dem [hier](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/#object-tex) erwähnten Sinne erweitert.

Als nächstes richten wir wie gewohnt die Eingabe- und Ausgabearbeitsverzeichnisse ein. Das Eingabearbeitsverzeichnis muss die Hauptformatquelldatei und alle ihre Abhängigkeiten enthalten.

Und der zweite wesentliche Unterschied ist die Art und Weise, wie wir den Job ausführen. Dieses Mal verwenden wir die statische Methode [CreateFormat()](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/), die zusammen mit den Optionen den Namen der Hauptquelldatei übernimmt, der mit dem Formatnamen identisch sein muss.

## Textsatz einer TeX-Datei in Ihrem benutzerdefinierten Format

Da wir nun über unser eigenes TeX-Format verfügen, möchten wir eine in diesem Format geschriebene TeX-Datei setzen. Hier ist der Code:

```C++
// Create typesetting options for a custom format on ObjectTeX engine extension.
System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::ObjectTeX(formatProvider));
options->set_JobName(u"typeset-with-custom-format");
// Specify the input working directory.
options->set_InputWorkingDirectory(wd);
// Specify a file system working directory for output.
options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
            
// Run typesetting.
System::MakeObject<Aspose::TeX::TeXJob>(System::MakeObject<System::IO::MemoryStream>(System::Text::Encoding::get_ASCII()->GetBytes(u"Congratulations! You have successfully typeset this text with your own TeX format!\\end")), System::MakeObject<XpsDevice>(), options)->Run();
            
// For further output to look write.
options->get_TerminalOut()->get_Writer()->WriteLine();
```

Natürlich müssen wir das Format irgendwie festlegen. Zunächst müssen wir eine Instanz der Klasse [FormatProvider](https://reference.aspose.com/tex/cpp/aspose.tex.resourceproviders/formatprovider/) erstellen. Dann verwenden wir im Optionskonstruktor die Konfiguration [TeXConfig.ObjectTeX()](https://reference.aspose.com/tex/cpp/aspose.tex/texconfig/#aefa7bbdf2ed28d6499f2dc5d5ad2ca3e), die unseren Formatanbieter als Argument verwendet und das Format über den „jungfräulichen“ Zustand der Engine lädt.

Der Rest des Codes sollte Ihnen bekannt sein. Es nutzt die zuvor in diesem [Leitfaden](/tex/{{lang.url-fragment}}cpp/conversion/) besprochenen Funktionen.

## Textsatz einer TeX-Datei im Plain-TeX-Format

Wenn wir den Formatanbieter aus dem gerade gezeigten Code weglassen, lädt die Engine das Standardformat, das im vierten Sinne [Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/) ist. Wenn Sie also eine TeX-Datei im einfachen TeX-Format geschrieben haben, können Sie sie auf diese Weise in jedes unterstützte Zielformat konvertieren.