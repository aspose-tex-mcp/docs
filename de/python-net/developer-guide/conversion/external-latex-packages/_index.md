---
translation: true
template: /templates/_template-python-net.md
title: Externe LaTeX-Pakete | Python
linktitle: Externe LaTeX-Pakete
weight: 19
url: /python-net/external-latex-packages/
description: Die Aspose.TeX-API für Python unterstützt die Verwendung externer Pakete, die nicht in der Bibliothek selbst enthalten sind, wie z. B. die Pakete fancybox und pgfplots
lastmod: "2024-09-26"
---

{{<section overview>}}

## Externe LaTeX-Pakete

Die **Aspose.TeX**-Bibliothek enthält eine Vielzahl [gängiger LaTeX-Pakete](/tex/{{lang.url-fragment}}net/embedded-packages/), sodass diese Pakete nicht manuell für die TeX-Engine bereitgestellt werden müssen. Es kann jedoch Situationen geben, in denen Ihre LaTeX-Datei ein Paket erfordert, das nicht im „Paketpaket“ der Bibliothek enthalten ist. In solchen Fällen können Sie versuchen, die erforderliche Eingabe, beispielsweise die Quelldateien des erforderlichen Pakets, über die Option [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) der Klasseninstanz [TeXOptions](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/) bereitzustellen. Wir werden anhand von zwei Beispielen untersuchen, wie das funktioniert.

### Erforderliche Eingaben in entpackter Form (das „fancybox“-Paket).

Angenommen, wir haben die folgende grundlegende LaTeX-Datei mit dem Namen „required-input-fs.tex“, die Teil unserer [Beispiellösung](https://GitHub.com/aspose-tex/Aspose.TeX-for-Python-.NET) ist:

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

Die 3. Zeile der Datei weist darauf hin, dass das Paket „fancybox“ erforderlich ist, das nicht in der „nativen“ Unterstützung enthalten ist. Nehmen wir an, wir haben die Quelldatei für das Paket „fancybox“. Da es sich um ein einfaches Paket handelt, das aus einer einzelnen Datei besteht, können wir diese Datei an einer beliebigen Stelle in unserem Dateisystem platzieren und den Verzeichnispfad wie folgt angeben:


```Python
options.required_input_directory = InputFileSystemDirectory('path-to-directory-where-fancybox.sty-located')
```

Sobald wir einen TeX-Job mit dieser Option ausführen (denken Sie daran, die anderen Optionen nach Bedarf anzupassen), erhalten wir das Ausgabedokument, in diesem Fall ein PNG-Bild.

![Ausgabedokument](/tex/images/python-net/Conversion-RequiredInputFs.png)

Hier ist der vollständige Quellcode für das Beispiel:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-RequiredInput-FileSystem.py" >}}

### Bereitstellung erforderlicher Eingaben in archivierter Form (Paket „pgfplots“)

Angenommen, wir haben die folgende LaTeX-Datei mit dem Namen „required-input-zip.tex“, bei der es sich ebenfalls um eine einfache Datei aus unserer Beispiellösung handelt:


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

In der dritten Zeile ist zu erkennen, dass die Datei das Paket „pgfplots“ erfordert, das nicht „nativ“ unterstützt wird. Auch hier gilt: Vorausgesetzt, dass wir über die Quelldateien für das Paket „pgfplots“ verfügen, sind diese Dateien recht zahlreich und befinden sich in zwei verschiedenen Verzeichnissen im Installationsverzeichnis jeder LaTeX-Satzanwendung. Der Ordner „pgfplots“ befindet sich sowohl im Verzeichnis „\tex\generic“ als auch im Verzeichnis „\tex\latex“. Damit die Aspose.TeX-Bibliothek ordnungsgemäß funktioniert, ist es notwendig, den Inhalt dieser beiden Ordner als Eingabe bereitzustellen. Um dies zu erreichen, möchten wir diese Quelldateien in ein ZIP-Archiv packen. Nachfolgend finden Sie das gewünschte Layout des Archivs:

![Layout des Archivs](/tex/images/python-net/pgfplots-zip-layout.png)

Und hier ist die Methode, mit der wir den Zugriff auf diese Quelldateien definieren:

```Python
with open("path-to-zip-with-pgfplots-sources") as zipStream:
    ...
    options.required_input_directory = InputZipDirectory(zipStream)
    ...
```

Nachdem wir einen TeX-Job mit dieser Option ausgeführt haben, erhalten wir das Ausgabedokument:

![Ausgabedokument](/tex/images/python-net/Conversion-RequiredInputZip.png)

Hier ist der vollständige Quellcode für das Beispiel:

{{< gist "aspose-com-gists""68d217858f0be40062562ce2bb2cd908""Aspose.TeX.Examples-Conversion-RequiredInput-Zip.py" >}}

> **_HINWEIS:_** Das Ergebnis wurde mit dem Paket `pgfplots`, Version 1.18.1, überprüft. Die Version des `pfg`-Pakets, das in der **Aspose.TeX**-Bibliothek enthalten ist, ist 3.1.9a.

<!--
### Externe Schriftartpakete verwenden

Normalerweise enthalten LaTeX-Distributionen einen vordefinierten Satz von Schriftarten, die für den Schriftsatz verwendet werden können. Zusätzlich zu diesen Standardschriftarten enthält **Aspose.TeX** jedoch auch mehrere nicht standardmäßige Schriftartpakete wie `amsfonts`, `eurosym` und `wasysym`. Wie bereits erwähnt, unterstützt Aspose.TeX auch die Verwendung externer Pakete, obwohl sich unsere bisherige Diskussion größtenteils auf Pakete konzentrierte, die keine Schriftarten enthalten.

Die *Object TeX*-Engine-Erweiterung von **Aspose.TeX** erfordert Fontmaps, also Textdateien in einem bestimmten Format mit der Erweiterung `.map`, um die entsprechenden physischen Schriftarten für den internen Schriftartnamen jedes TeX zu bestimmen. Diese Fontmaps müssen während der Initialisierungsphase in den Speicher von TeX geladen werden und sollten in dem von Ihnen verwendeten Paket enthalten sein. Da die Engine nicht die Namen aller Fontmaps kennt, sucht sie nach Dateien mit der Erweiterung `.map`. Wenn daher ein Wert für die Option [required_input_directory](https://reference.aspose.com/tex/python-net/aspose.tex/texoptions/required_input_directory/) angegeben wird, sollte die Implementierung der Schnittstelle [IInputWorkingDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/iinputworkingdirectory/) den Zugriff auf Sammlungen von Dateinamen nach Erweiterung ermöglichen. Darüber hinaus sollte diese Implementierung auch die Schnittstelle [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/) implementieren. Die Standardimplementierungen wie [InputFileSystemDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputfilesystemdirectory/) und [InputZipDirectory](https://reference.aspose.com/tex/python-net/aspose.tex.io/inputzipdirectory/) erfüllen diese Anforderungen bereits.

Unten sehen Sie ein Beispiel für ein benutzerdefiniertes erforderliches Eingabeverzeichnis, das zeigt, wie die Schnittstelle [IFileCollector](https://reference.aspose.com/tex/python-net/aspose.tex.io/ifilecollector/) implementiert wird. Dieses Beispiel konzentriert sich auf das Sammeln von Dateinamen nach Erweiterung und lässt absichtlich die Details der Dateispeicherung und des Dateiabrufs aus.

{{< gist "aspose-com-gists" "68d217858f0be40062562ce2bb2cd908" "Aspose.TeX.Examples-Conversion-RequiredInputDirectory.py" >}}
-->

### Einschränkungen

Wenn Sie auf ein Paket stoßen, das unter dem *LaTeX3e*-Kernel entwickelt wurde und von Ihrer LaTeX-Datei benötigt wird, ist es unwahrscheinlich, dass es mit der **Aspose.TeX**-Bibliothek funktioniert. Dies liegt daran, dass die Bibliothek auf dem *LaTeX2e*-Kernel basiert.

Darüber hinaus kann es Fälle geben, in denen ein von Ihrer LaTeX-Datei benötigtes Paket direkt geräteabhängige primitive Befehle verwendet, die von der *Object TeX*-Engine der **Aspose.TeX**-Bibliothek nicht unterstützt werden. In solchen Fällen funktioniert das Paket nicht mit der Bibliothek.