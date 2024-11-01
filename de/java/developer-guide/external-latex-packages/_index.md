---
translation: true
template: /templates/_template-java.md
title: Externe LaTeX-Pakete | API für Java
linktitle: Externe LaTeX-Pakete
weight: 30
url: /java/external-latex-packages/
description: Die Aspose.TeX-API für Java ermöglicht die Verwendung externer Pakete, d. h. solcher, die nicht in der Bibliothek selbst enthalten sind.
lastmod: "2024-09-26"
---

{{<section overview>}}

## Externe LaTeX-Pakete

In der **Aspose.TeX**-Bibliothek für Java sind eine Reihe [gängiger LaTeX-Pakete](/tex/{{lang.url-fragment}}net/embedded-packages/) enthalten. Sie müssen sich also nicht darum kümmern, wie Sie diese Pakete der TeX-Engine der Bibliothek bereitstellen. Aber manchmal (vielleicht oft) erfordert Ihre LaTeX-Datei möglicherweise ein Paket, das über das „nativ“ unterstützte „Paketpaket“ hinausgeht. In diesem Fall können Sie versuchen, die erforderliche Eingabe, d. h. die Quelldateien des erforderlichen Pakets, mithilfe der Methode [setRequiredInputDirectory()](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#setRequiredInputDirectory-com.aspose.tex.IInputWorkingDirectory-) der Klasseninstanz [TeXOptions](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/) bereitzustellen. Wir werden anhand von zwei Beispielen sehen, wie das funktioniert.

### Entpackte erforderliche Eingabe („fancybox“-Paket)

Nehmen wir an, wir haben die folgende einfache LaTeX-Datei, die „required-input-fs.tex“ aus unserer [Beispiellösung](https://GitHub.com/aspose-tex/Aspose.TeX-for-Java) ist:

```tex
\documentclass{article}
\usepackage[a6paper,landscape]{geometry}
\usepackage{fancybox}
\begin{document}
Test: \fbox{
  \begin{Bitemize}[b]
  \item First item
  \item A second one\\ on two lines
  \item(2pt) A third with extra space
  \end{Bitemize}
}
\par\bigskip
Test: \fbox{
  \begin{Beqnarray}[t]
  y & = & x^2 \\
  a^2 + 2ab + b^2 & = & (a + b)^2 \\
  \int_0^\infty e^{-ax} dx & = & \frac{1}{a}
  \end{Beqnarray}
}
\end{document}
```

In der dritten Zeile sehen wir, dass die Datei das Paket „fancybox“ erfordert, das nicht „nativ“ unterstützt wird. Wir gehen außerdem davon aus, dass wir über die Quelldatei des Pakets „fancybox“ verfügen. Da es sich um ein einfaches Paket handelt, besteht es eigentlich nur aus einer Datei. Wir können diese Datei an einer beliebigen Stelle in unserem Dateisystem platzieren und den Verzeichnispfad einfach wie folgt angeben:

```Java
options.setRequiredInputDirectory(new InputFileSystemDirectory("path-to-directory-where-fancybox.sty-located"));
```

Nachdem wir einen TeX-Job mit dieser Option ausgeführt haben (vergessen Sie nicht, die anderen Optionen nach Bedarf anzupassen), erhalten wir das Ausgabedokument (d. h. ein PNG-Bild).

![Ausgabedokument](/tex/images/java/Conversion-RequiredInputFs.png)

Hier ist der vollständige Quellcode für das Beispiel:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.java" >}}

### Archivierte erforderliche Eingabe (Paket „pgfplots“)

Nehmen wir nun an, dass wir die folgende ebenfalls recht einfache LaTeX-Datei haben, nämlich „required-input-zip.tex“ aus unserer Beispiellösung:


```tex
\documentclass{article}
\usepackage[margin=0.25in]{geometry}
\usepackage{pgfplots}
\pgfplotsset{width=10cm,compat=1.18}
\begin{document}

First example is 2D and 3D math expressions plotted side-by-side.

%Here begins the 2D plot
\begin{tikzpicture}
\begin{axis}
\addplot[color=red]{exp(x)};
\end{axis}
\end{tikzpicture}
%Here ends the 2D plot
\hskip 5pt
%Here begins the 3D plot
\begin{tikzpicture}
\begin{axis}
\addplot3[
    surf,
]
{exp(-x^2-y^2)*x};
\end{axis}
\end{tikzpicture}
%Here ends the 3D plot

\end{document}
```

In der dritten Zeile sehen wir, dass die Datei das Paket „pgfplots“ erfordert, das ebenfalls nicht „nativ“ unterstützt wird. Auch hier gehen wir davon aus, dass wir über die Quelldateien des Pakets „pgfplots“ verfügen. Es handelt sich um eine ziemlich große Menge an Dateien, die auf zwei Speicherorte verteilt sind, wenn Sie sie im Installationsverzeichnis einer beliebigen LaTeX-Satzanwendung finden. Sie finden den Ordner „pgfplots“ sowohl im Ordner „\tex\generic“ als auch im Ordner „\tex\latex“. Und der Inhalt dieser beiden Ordner muss als erforderliche Eingabe für die Aspose.TeX-Bibliothek bereitgestellt werden. Wir möchten, dass diese Quelldateien in ein ZIP-Archiv gepackt werden. Hier ist das Layout des Archivs:

![Archivlayout](/tex/images/java/pgfplots-zip-layout.png)

Und so legen wir den Zugriff auf diese Quelldateien fest:

```Java
final Stream zipStream = File.Open("path-to-zip-with-pgfplots-sources"), FileMode.Open))
try {
    ...
    options.setRequiredInputDirectory(new InputZipDirectory(zipStream));
    ...
} finally {
    if (zipStream != null)
        zipStream.close();
}

```

Nachdem wir einen TeX-Job mit dieser Option ausgeführt haben, erhalten wir das Ausgabedokument:

![Ausgabedokument](/tex/images/java/Conversion-RequiredInputZip.png)

Hier ist der vollständige Quellcode für das Beispiel:

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-RequiredInput-Zip.java" >}}

> **_HINWEIS:_** Das Ergebnis wurde mit dem Paket `pgfplots`, Version 1.18.1, überprüft. Die Version des `pfg`-Pakets, das in der **Aspose.TeX**-Bibliothek enthalten ist, ist 3.1.9a.

### Verwendung externer Schriftartenpakete

In der Regel enthalten LaTeX-Distributionen eine Auswahl an Standardschriftarten, die für den Schriftsatz verwendet werden können. Zusätzlich zu diesen Schriftarten bietet **Aspose.TeX** mehrere nicht standardmäßige Schriftartenpakete wie „amsfonts“, `Eurosym` und „wasysym“. Wie bereits erwähnt, unterstützt **Aspose.TeX** auch die Verwendung externer Pakete, obwohl unser Fokus hauptsächlich auf Paketen lag, die keine Schriftarten enthalten.
Die *Object TeX*-Engine-Erweiterung in **Aspose.TeX** erfordert Schriftartenzuordnungen, bei denen es sich um Textdateien mit der Erweiterung „.map“ handelt, die die physischen Schriftarten angeben, die dem internen Schriftartennamen jedes TeX entsprechen. Diese Schriftartenzuordnungen müssen während der Initialisierungsphase in den Speicher von TeX geladen und in den Paketdateien enthalten sein. Da die Engine nicht die Namen aller Schriftartenkarten kennt, sucht sie nach Dateien mit der Erweiterung „.map“. Daher muss die Implementierung der Schnittstelle [IInputWorkingDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/iinputworkingdirectory/), die als Wert der Option [RequiredInputDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/texoptions/#getRequiredInputDirectory--) verwendet wird, eine Möglichkeit bieten, auf Sammlungen von Dateinamen basierend auf ihrer Erweiterung zuzugreifen. Insbesondere muss diese Implementierung auch die Schnittstelle [IFileCollector](https://reference.aspose.com/tex/java/com.aspose.tex/ifilecollector/) implementieren. Die Standardimplementierungen [InputFileSystemDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputfilesystemdirectory/) und [InputZipDirectory](https://reference.aspose.com/tex/java/com.aspose.tex/inputzipdirectory/) erfüllen diese Anforderung bereits.

Nachfolgend stellen wir ein Beispiel für ein benutzerdefiniertes erforderliches Eingabeverzeichnis vor, das auch die Schnittstelle [IFileCollector](https://reference.aspose.com/tex/java/com.aspose.tex/ifilecollector/) implementiert. Unser Hauptaugenmerk liegt auf der Erfassung von Dateinamen anhand ihrer Erweiterung, und wir lassen die Details zum Speichern und Abrufen von Dateien bewusst weg.

{{< gist "aspose-com-gists""67385c777283964d328086603f691ac9""Aspose.TeX.Examples-Conversion-RequiredInputDirectory.java" >}}

### Einschränkungen

Ein für Ihre LaTeX-Datei erforderliches Paket kann unter dem *LaTeX3e*-Kernel entwickelt werden. Ein solches Paket wird höchstwahrscheinlich nicht mit der **Aspose.TeX**-Bibliothek funktionieren, da letztere auf dem *LaTeX2e*-Kernel basiert.

Außerdem ruft ein von Ihrer LaTeX-Datei benötigtes Paket möglicherweise direkt geräteabhängige primitive Befehle auf, die von der *Object TeX*-Engine der **Aspose.TeX**-Bibliothek nicht unterstützt werden. Ein solches Paket wird leider nicht mit Sicherheit funktionieren.