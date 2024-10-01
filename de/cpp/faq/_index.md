---
translation: true
template: /templates/_template-cpp.md
title: Häufig gestellte Fragen | Aspose.TeX für С++
linktitle: FAQ
weight: 80
url: /cpp/faq/
description: Erhalten Sie Antworten auf die häufigsten Fragen zu Aspose.TeX für C++, einer umfassenden API für den Satz und die Bearbeitung von TeX und LaTeX.
lastmod: "2024-09-26"
---

{{<section overview>}}

<br><br>

**F: Was ist die Hauptfunktionalität der Aspose.TeX API Solution für C++?**

**A:** Die Hauptfunktionalität von Aspose.TeX ist die programmgesteuerte Erstellung, Bearbeitung und Konvertierung von TeX- und LaTeX-Dokumenten. Damit können Sie vorhandene TeX/LaTeX-Dateien laden, deren Inhalt ändern und Aktionen wie das Hinzufügen oder Entfernen von Elementen ausführen.
<br><br>

**F: Welche Formate unterstützt Aspose.TeX für C++?**

**A:** Aspose.TeX unterstützt TeX und LaTeX als Eingabe und die Formate XPS, PDF, PNG, JPEG, TIFF, SVG und BMP als Ausgabe.
<br><br>

**F: Wie konvertiert man TeX?**

**A:** Es ist ganz einfach. Sie müssen nur wenige Schritte unternehmen! 

1. Erstellen Sie ein Objekt der TeXOptions-Klasse.
2. Geben Sie die Ausgabe an, indem Sie die Methode set_OutputWorkingDirectory() aufrufen.
3. Initialisieren Sie die Speicheroptionen für das Ausgabeformat und instanziieren Sie die TeXJob-Klasse.
4. Führen Sie die Konvertierung aus.

Weitere Beispiele finden Sie in den Anleitungen zur [Konvertierung](/tex/{{lang.url-fragment}}cpp/conversion/).
<br><br>

**F: Kann ich mit Aspose.TeX für C++ ein benutzerdefiniertes Format erstellen?**

**A:** Ja, die Bibliothek verfügt über diese Funktionalität. Es wird im Artikel [Andere TeX-Konvertierungsausgabeformate](/tex/cpp/other-tex-formats/#creating-a-custom-format) kurz beschrieben.
<br><br>

**F: Welche Pakete sind in die Aspose.TeX-API-Lösung eingebettet?**

**A:** Mittlerweile sind [in Aspose.TeX eingebettete LaTeX-Pakete](/tex/{{lang.url-fragment}}net/embedded-packages/) enthalten: 

- eurosym
- geometry
- graphics
- hyperref
- multirow
- pgf
- pict2e
- setspace
- setspace
- Latex-Tools-Bundle: Afterpage, Array, BM, Calc, Dcolumn, Delarray, Enumerate, Fileerr, Fontsmpl, Ftnright, Hhline, Indentfirst, Layout, Longtable, Multicol, Rawfonts, Showkeys, Somedefs, Tabularx, Theorem, Trace, Varioref, wörtlich, xr und xspace.
- URL
- wasysym
- xcolor 
<br><br>

**F: Wie setze ich TeX-Dateien?**

**A:** Es ist wirklich einfach. Schauen Sie sich das Beispiel unten an! 

```C++
    // Create conversion options for the Object TeX/Object LaTeX format upon the Object TeX engine extension.
    System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::ObjectTeX()); // TeXConfig::get_ObjectLaTeX()
    // Specify a file system working directory for the output.
    options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
    // Run the job.
    System::MakeObject<Aspose::TeX::TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world"),
        System::MakeObject<XpsDevice>(), options)->Run();
```
<br><br>

**F: Wie installiere ich das Aspose.TeX für C++-Paket von Nuget?**

**A:** Öffnen Sie den NuGet-Paketmanager, suchen Sie nach Aspose.TeX.Cpp und installieren Sie es. Sie können auch den folgenden Befehl über die Package Manager-Konsole verwenden:

```C++
    PM> Install-Package Aspose.TeX.Cpp
```

**F: Kann ich LaTeX-Formeln mit Aspose.TeX für C++ rendern?**

**A:** Ja, mit der Mathe-Rendering-Bibliothek Aspose.TeX können Sie ganz einfach ein SVG- oder PNG-Bild mit einer mathematischen Formel erstellen. 

1. Erstellen Sie Rendering-Optionen.
2. Geben Sie Hintergrundfarbe, Präambel, Auflösung, Vordergrundfarbe und Skalierungsfaktor an.
3. Geben Sie den Ausgabestream für die Protokolldatei an.
4. Erstellen Sie einen Dateistream, um das Ausgabebild zu speichern.
5. Erstellen Sie ein Objekt der Klasse *(Dateiformat)MathRenderer* und führen Sie das Rendern der Formel aus, indem Sie die Methode *Render()* aufrufen. 

Weitere Beispiele finden Sie in den Leitfäden [LaTeX-Rendering mathematischer Formeln](/tex/{{lang.url-fragment}}cpp/latex-math-formula-rendering/).
<br><br>

**F: Wo kann ich mehr über TeX erfahren?**

**A:** Es gibt eine [Wissensdatenbank für TeX und LaTeX](/tex/{{lang.url-fragment}}net/introduction-to-tex/), damit Sie das Thema tiefer verstehen können. Schauen Sie sich auch die [Allgemeinen Artikel zu LaTeX](/tex/{{lang.url-fragment}}java/general-articles-latex/) an, in denen Sie Regeln erfahren, die jeder Dokumentautor befolgen muss. Es definiert auch die Struktur der Quelldatei, bei der es sich im Wesentlichen um ein Satzprogramm handelt.
<br><br>

**F: Kann Aspose.TeX für C++ mit Archiven arbeiten und sie als Ausgabe verwenden, ohne die Dateien vorher zu entpacken oder das Ergebnis direkt im Archiv zu speichern?**

**A:** Ja, öffnen Sie einfach einen Stream, der ein ZIP-Archiv enthält, das als Eingabearbeitsverzeichnis dient. Optional können Sie ein Unterverzeichnis im Archiv angeben. Andernfalls wird die Datei im gesamten Archiv durchsucht. Um ZIP-Archiv-Arbeitsverzeichnisse für die Eingabe und Ausgabe anzugeben, verwenden Sie die Klassen InputZipDirectory und OutputZipDirectory.
<br><br>

**F: Kann ich die Lösung testen, bevor ich sie kaufe?**

**A:** Ja, Sie können Aspose.TeX für C++-Produkte zu Evaluierungszwecken problemlos herunterladen. Die Evaluierungsversion von Aspose.TeX (ohne Angabe einer Lizenz) bietet die volle Produktfunktionalität mit Ausnahme einiger [Evaluierungseinschränkungen](/tex/{{lang.url-fragment}}cpp/licensing/#evaluation-version-limitations).

Wenn Sie Aspose.TeX ohne Evaluierungseinschränkungen ausprobieren möchten, fordern Sie eine 30-tägige [temporäre Lizenz](https://purchase.aspose.com/temporary-license/) an.
<br><br>

**F: Wo kann ich Hilfe bekommen, wenn ich Probleme mit der Bibliothek habe?**

**A:** Suchen Sie im [Aspose-Forum](https://forum.aspose.com/c/tex/47) nach Antworten oder fügen Sie ein neues Thema mit Ihrem Problem hinzu, wenn Sie kein passendes Thema für Ihr Problem gefunden haben. 
<br><br>

**F: Wie kann ich eine Lizenz für Aspose.TeX für C++ beantragen?**

**A:** Verwenden Sie die Methode „License::SetLicense“, um die Komponente zu lizenzieren. Der einfachste Weg, eine Lizenz festzulegen (9), besteht darin, die Lizenzdatei im selben Ordner wie die Aspose.TeX.dll abzulegen und den Dateinamen ohne Pfad anzugeben.
<br><br>

**F: Kann ich die Funktionalität dieser API-Lösung sehen, die in Webanwendungen implementiert ist?**

**A:** Schauen Sie sich unsere [Weblösungen](https://products.aspose.app/tex/applications) an, um TeX- und LaTeX-Dateien zu konvertieren, anzuzeigen, zusammenzuführen und zu bearbeiten, mathematische Gleichungen zu erstellen und vieles mehr.
<br><br>

