---
translation: true
template: /templates/_template-net.md
title: Externe LaTeX-Pakete | Aspose.TeX für .NET
linktitle: Externe LaTeX-Pakete
weight: 20
url: /net/external-latex-packages/
description: Aspose.TeX für .NET ermöglicht die Verwendung externer Pakete, d. h. derjenigen, die nicht in der Bibliothek enthalten sind, wie etwa die Pakete pgfplots.
keywords: externe Latex-Pakete, Aspose Tex, .net Tex, Latex-Pakete, Fancybox, pgfplots, erforderliches Eingabeverzeichnis, Eingabe-Zip, benutzerdefiniertes Eingabeverzeichnis, Tex-Konvertierung
lastmod: "2024-09-26"
---

{{<section overview>}}

## Externe LaTeX-Pakete

Die **Aspose.TeX**-Bibliothek enthält eine Reihe [gängiger LaTeX-Pakete](/tex/{{lang.url-fragment}}net/embedded-packages/). Sie müssen sich also keine Gedanken darüber machen, wie Sie diese Pakete der TeX-Engine der Bibliothek bereitstellen. Aber manchmal (oder ziemlich oft) erfordert Ihre LaTeX-Datei möglicherweise ein Paket, das über das „nativ“ unterstützte „Paketpaket“ hinausgeht. Wenn dies der Fall ist, können Sie versuchen, die erforderliche Eingabe, d. h. die Quelldateien des erforderlichen Pakets, über die Option [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) der Klasseninstanz [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) bereitzustellen. Wir werden anhand von zwei Beispielen sehen, wie das funktioniert.

### Entpackte erforderliche Eingabe („fancybox“-Paket)

Nehmen wir an, wir haben die folgende einfache LaTeX-Datei, die „required-input-fs.tex“ aus unserer [Beispiellösung](https://GitHub.com/aspose-tex/Aspose.TeX-for-.NET) ist:


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

In der dritten Zeile können wir sehen, dass die Datei das Paket „fancybox“ erfordert, das nicht „nativ“ unterstützt wird. Nehmen wir außerdem an, dass wir die Quelldatei des Pakets „fancybox“ haben. Da es sich um ein einfaches Paket handelt, besteht es eigentlich aus einer einzigen Datei. Wir können diese Datei an einer beliebigen Stelle in unserem Dateisystem platzieren und den Verzeichnispfad wie folgt angeben:


```C#
options.RequiredInputDirectory = new InputFileSystemDirectory("path-to-directory-where-fancybox.sty-located");
```

Nachdem wir einen TeX-Job mit dieser Option ausgeführt haben (vergessen Sie nicht, die anderen Optionen nach Bedarf anzupassen), erhalten wir das Ausgabedokument (d. h. ein PNG-Bild).

![Ausgabedokument](/tex/images/net/Conversion-RequiredInputFs.png)

Hier ist der vollständige Quellcode für das Beispiel:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.cs" >}}

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


In der dritten Zeile sehen wir, dass die Datei das Paket „pgfplots“ erfordert, das ebenfalls nicht „nativ“ unterstützt wird. Auch hier gehen wir davon aus, dass wir über die Quelldateien des Pakets „pgfplots“ verfügen. Es handelt sich um eine ziemlich große Anzahl von Dateien, die auf zwei Speicherorte verteilt sind, wenn Sie sie im Installationsverzeichnis einer beliebigen LaTeX-Satzanwendung finden. Sie finden den Ordner „pgfplots“ sowohl im Ordner „\tex\generic“ als auch im Ordner „\tex\latex“. Und der Inhalt dieser beiden Ordner muss als erforderliche Eingabe für die Aspose.TeX-Bibliothek bereitgestellt werden. Wir möchten, dass diese Quelldateien in ein ZIP-Archiv gepackt werden. Hier ist das Layout des Archivs:

![Layout des Archivs](/tex/images/net/pgfplots-zip-layout.png)

Und so legen wir den Zugriff auf diese Quelldateien fest:


```C#
using (Stream zipStream = File.Open("path-to-zip-with-pgfplots-sources"), FileMode.Open))
{
    ...
    options.RequiredInputDirectory = new InputZipDirectory(zipStream);
    ...
}
```

Nachdem wir einen TeX-Job mit dieser Option ausgeführt haben, erhalten wir das Ausgabedokument:

![Ausgabedokument](/tex/images/net/Conversion-RequiredInputZip.png)

Hier ist der vollständige Quellcode für das Beispiel:

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-RequiredInput-Zip.cs" >}}

> **_HINWEIS:_** Das Ergebnis wurde mit dem Paket `pgfplots`, Version 1.18.1, überprüft. Die Version des `pfg`-Pakets, das in der **Aspose.TeX**-Bibliothek enthalten ist, ist 3.1.9a.

### Verwendung externer Schriftartenpakete

In der Regel stellen LaTeX-Distributionen eine Reihe von Standardschriftarten für den Schriftsatz zur Verfügung. Außer diesen Schriftarten enthält **Aspose.TeX** eine Reihe nicht standardmäßiger Schriftartenpakete. Zum Beispiel „amsfonts“, `Eurosym` und „wasysym“. Wie wir oben gesehen haben, ermöglicht Aspose.TeX auch die Verwendung externer Pakete. Aber meistens haben wir über Pakete gesprochen, die keine Schriftarten enthalten.

Die *Object TeX*-Engine-Erweiterung von **Aspose.TeX** benötigt Schriftartenzuordnungen (bei denen es sich laut Konvention um Textdateien in einem bestimmten Format mit der Erweiterung „.map“ handelt), um zu bestimmen, welche physischen Schriftarten dem internen Schriftartennamen jedes TeX entsprechen . Diese Schriftartenzuordnungen müssen während der Initialisierungsphase in den Speicher von TeX geladen werden. Und natürlich müssen sie in den Dateien des Pakets vorhanden sein, das Sie einbinden. Da die Engine nicht die Namen aller Schriftartenzuordnungen kennt, sucht sie nach allen Dateien mit der Erweiterung „.map“. Daher muss eine Implementierung der Schnittstelle [IInputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/iinputworkingdirectory/), die als Wert der Option [RequiredInputDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/requiredinputdirectory/) verwendet wird, eine Möglichkeit bieten, über die Erweiterung auf Sammlungen von Dateinamen zuzugreifen. Genauer gesagt muss diese Implementierung auch die Schnittstelle [IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/) implementieren. Die Standardimplementierungen – [InputFileSystemDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) und [InputZipDirectory](https://reference.aspose.com/tex/net/aspose.tex.io/inputzipdirectory/) – tun dies bereits.

Nachfolgend stellen wir ein anschauliches Beispiel für ein benutzerdefiniertes erforderliches Eingabeverzeichnis bereit, das auch die Schnittstelle [IFileCollector](https://reference.aspose.com/tex/net/aspose.tex.io/ifilecollector/) implementiert. Während wir uns auf das Sammeln von Dateinamen nach Erweiterung konzentrieren, lassen wir die Details zum Speichern und Abrufen von Dateien bewusst weg.

{{< gist "aspose-com-gists""76c7e5770ac8b3f6d409f6ec60f02030""Aspose.TeX.Examples-Conversion-RequiredInputDirectory.cs" >}}

### Einschränkungen

Es kann vorkommen, dass ein für Ihre LaTeX-Datei erforderliches Paket unter dem *LaTeX3e*-Kernel entwickelt wird. Ein solches Paket wird höchstwahrscheinlich nicht mit der **Aspose.TeX**-Bibliothek funktionieren, da letztere auf dem *LaTeX2e*-Kernel basiert.

Es kann auch vorkommen, dass ein von Ihrer LaTeX-Datei benötigtes Paket direkt geräteabhängige primitive Befehle aufruft, die von der *Object TeX*-Engine der **Aspose.TeX**-Bibliothek nicht unterstützt werden. Ein solches Paket wird leider nicht mit Sicherheit funktionieren.