---
translation: true
template: /templates/_template-cpp.md
title: Andere TeX-Verwaltungsoptionen | C++
linktitle: Andere Optionen
weight: 17
url: /cpp/other-options/
description: Mit der Konvertierungsfunktion der Aspose.TeX-API-Lösung für C++ können Sie den anfänglichen Interaktionsmodus festlegen, in dem die Engine startet. 
lastmod: "2024-09-26"
---

{{<section overview>}}

## So legen Sie den Interaktionsmodus fest

Wie wir [hier](/tex/{{lang.url-fragment}}net/tex-io/#tex-interaction-modes) erwähnt haben, können wir mit **Aspose.TeX für C++** den anfänglichen Interaktionsmodus festlegen, in dem die Engine startet. So machen wir es:

```C++
// Create conversion options instance.
...
// Set the interaction mode.
options->set_Interaction(Interaction::NonstopMode);
```

## So legen Sie den Jobnamen fest

Wenn wir die Haupteingabedatei als Dateinamen übergeben, erhalten wir Ausgabedateien mit demselben Namen, allerdings mit anderen Erweiterungen. Die TeX-Engine nennt den Namen der Eingabedatei den *Jobnamen* und verwendet ihn für Ausgabedateien, außer in Fällen, in denen Hilfsdateien mit explizit angegebenen anderen Namen geschrieben werden. Wenn wir die Haupteingabedatei als [stream](/tex/{{lang.url-fragment}}cpp/other-ways-of-main-input/#providing-the-main-input-file-as-a-stream) übergeben, verwendet die TeX-Engine den Standard-Jobnamen, der *texput* ist.
In beiden Fällen können wir den Jobnamen überschreiben, indem wir die entsprechende Konvertierungsoption zuweisen.

```C++
// Create conversion options instance.
...
// Set the job name.
options->set_JobName(u"my-job-name");
```
## So wiederholen Sie den Job

Wie wir [oben](/tex/{{lang.url-fragment}}net/latex-io/#latex-input) in Bezug auf Etiketten und Referenzen erwähnt haben, gibt es Fälle, in denen wir denselben Job gerne zweimal ausführen möchten. So kann es gemacht werden:
```C++
// Create conversion options instance.
...
// Set the job name.
options->set_Repeat(true);
```