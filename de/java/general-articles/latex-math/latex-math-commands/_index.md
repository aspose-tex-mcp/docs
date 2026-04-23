---
translation: true
template: /templates/_template-java.md
linktitle: LaTeX-Befehle
title: 3. LaTeX-Befehle 
weight: 30
url: /java/latex-math-commands/
keywords: Latex, Latex-Mathe-Formeln, Latex-Mathe, Latex-Mathe-Befehle, Latex-Quadratwurzel, Latex-Mathe-Unterstreichung, Latex-Mathe-Überstreichung
description: In diesem Artikel wird eine andere Möglichkeit zum Erstellen mathematischer Formeln beschrieben, bei der Makrobefehle von LaTeX zum Einsatz kommen.
lastmod: "2024-09-26"
---

{{<section overview>}}

Eine andere Möglichkeit, komplexe Formeln aus einfachen zu erstellen, ist die Verwendung der Befehle `\sqrt`, `\underline` oder `\overline`. Sie gelten auch für das Zeichen oder die Unterformel, die ihnen folgt:

![Einfachste Anwendung von LaTeX-Befehlen](/tex/images/java/tutorial/latex-math-3-1.png)

Sie können auch Kubikwurzeln und ähnliches erhalten:

![Wurzeln beliebigen Grades](/tex/images/java/tutorial/latex-math-3-2.png)

Diese drei Befehle platzieren Linien über und unter Unterformeln beliebiger Größe und Form; Die Taktstriche ändern ihre Größe und Position, sodass sie lang genug sind, um die Unterformel abzudecken, und hoch genug oder niedrig genug, um sie nicht zu überlappen. Insbesondere erscheinen Quadratwurzelzeichen an verschiedenen Positionen, abhängig von der Höhe und Tiefe dessen, was mit `\sqrt` versehen wird: ![Wurzeln beliebigen Grades](/tex/images/java/tutorial/latex-math-3-3.png) In einem solchen Fall möchten Sie möglicherweise nur Quadrate setzen Wurzeln einheitlich, wie folgt: ![Wurzeln beliebigen Grades](/tex/images/java/tutorial/latex-math-3-4.png) Der einfache Weg, dies zu tun, ist die Verwendung des Befehls `\mathstrut`:


```tex
$\sqrt{\mathstrut a} + \sqrt{\mathstrut d} + \sqrt{\mathstrut y}$.
```

Ein `\mathstrut` ist eine unsichtbare Box mit der Breite Null. Seine Höhe und Tiefe entsprechen der Höhe und Tiefe einer Klammer `(`. Daraus folgt, dass Unterformeln, die `\mathstrut` enthalten, immer die gleiche Höhe und Tiefe haben, es sei denn, sie beinhalten kompliziertere Konstruktionen wie tiefgestellte und hochgestellte Indizes.