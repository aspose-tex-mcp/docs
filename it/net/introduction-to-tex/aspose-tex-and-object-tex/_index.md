---
translation: true
template: /templates/_template-net.md
linktitle: Object TeX
title: Aspose.TeX e Object TeX 
weight: 11
url: /net/aspose-tex-and-object-tex/
description: TeX è un formato di input e output di questa soluzione API, quindi qui andiamo a spiegare l'oggetto TeX e come si trasforma in un formato target.
lastmod: "2026-04-22"
---

{{<section overview>}}

## Object TeX

Ora consideriamo il formato di output.

Il TeX originale era in grado di produrre file in formato * DVI * (dispositivo indipendente). È successo che il formato DVI non definisca le metriche di un media su cui verrà stampato un file: la dimensione della pagina e la posizione dell'angolo in alto a sinistra dell'intero contenuto della pagina. Una volta che decidiamo di rendere il motore TeX in grado di produrre file, diciamo, in formato PDF, dobbiamo definire tali metriche. Pertanto, dobbiamo includere nuovi primitivi nel set originale del motore TeX. E questa sarebbe un'estensione del motore stesso.

Questo è ciò che * Object * TeX è. Ancora una volta, **da un lato, è un linguaggio di programmazione con l'insieme di primitive di VirTeX, ampliato con nuovi primitivi imposti da nuovi requisiti di uscita. D'altra parte, è un motore TeX esteso che comprende anche nuovi primitivi. E, in terza mano, Object TeX è un nuovo sistema di composizione in tutto.**

C'è la quarta mano. Il formato Object TeX è anche un formato basato su TeX semplice che contiene definizioni che coinvolgono nuovi primitivi, ad esempio, assegnano valori predefiniti alle metriche dei media.

## Aspose.TeX

E Aspose.TeX è solo un'API per il sistema Object TeX.

## Perché il nuovo TeX è Object?

Allora perché abbiamo usato "Object" nel nome del sistema? Il motivo è che l'output effettivo del motore Object TeX non è un file nel formato di output, ma un modello di oggetto *intermedio*, che viene quindi trasformato in un formato target.