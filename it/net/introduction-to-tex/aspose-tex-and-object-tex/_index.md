---
translation: true
template: /templates/_template-net.md
linktitle: Oggetto tex
title: Aspose.TeX e oggetto tex 
weight: 11
url: /net/aspose-tex-and-object-tex/
description: Tex è un formato di input e output di questa soluzione API, quindi qui andiamo a spiegare l'oggetto Tex e come si trasforma in un formato target.
lastmod: "2025-06-13"
---

{{<section overview>}}

## Oggetto tex

Ora consideriamo il formato di output.

Il Tex originale era in grado di produrre file in formato * DVI * (dispositivo indipendente). È successo che il formato DVI non definisca le metriche di un media su cui verrà stampato un file: la dimensione della pagina e la posizione dell'angolo in alto a sinistra dell'intero contenuto della pagina. Una volta che decidiamo di rendere il motore TEX in grado di produrre file, diciamo, in formato PDF, dobbiamo definire tali metriche. Pertanto, dobbiamo includere nuovi primitivi nel set originale del motore Tex. E questa sarebbe un'estensione del motore stesso.

Questo è ciò che * Object * Tex è. Ancora una volta, **da un lato, è un linguaggio di programmazione con l'insieme di primitive di Virtex, ampliato con nuovi primitivi imposti da nuovi requisiti di uscita. D'altra parte, è un motore TEX esteso che comprende anche nuovi primitivi. E, in terza mano, Object Tex è un nuovo sistema di composizione in tutto.**

C'è la quarta mano. Il formato Object Tex è anche un formato basato su TEX semplice che contiene definizioni che coinvolgono nuovi primitivi, ad esempio, assegnano valori predefiniti alle metriche dei media.

## Aspose.TeX

E Aspose.Tex è solo un'API per il sistema Object Tex.

## Perché il nuovo tex è oggetto?

Allora perché abbiamo usato "oggetto" nel nome del sistema? Il motivo è che l'output effettivo del motore Object TEX non è un file nel formato di output, ma un modello di oggetto *intermedio*, che viene quindi trasformato in un formato target.