---
translation: true
template: /templates/_template-net.md
linktitle: Objeto de texto
title: Aspose.TeX y Objeto TeX | Aspose.TeX para .NET
weight: 11
url: /net/aspose-tex-and-object-tex/
description: TeX es un formato de entrada y salida de esta solución API, por lo que aquí vamos a explicar el Object TeX y cómo se transforma en un formato de destino.
lastmod: "2024-10-30"
---

{{<section overview>}}

## Objeto de texto

Ahora consideremos el formato de salida.

El TeX original era capaz de generar archivos en formato *DVI* (DeVice Independent) únicamente. Sucedió que el formato DVI no define las métricas del medio en el que se va a imprimir un archivo: el tamaño de la página y la posición de la esquina superior izquierda de todo el contenido de la página. Una vez que decidimos hacer que el motor TeX sea capaz de generar archivos, digamos, en formato PDF, necesitamos definir dichas métricas. Por lo tanto, necesitamos incluir nuevas primitivas en el conjunto del motor TeX original. Y esto sería una extensión del propio motor.

Eso es lo que es *Object* TeX. Nuevamente, **por un lado, es un lenguaje de programación con el conjunto de primitivas de VirTeX, ampliado con nuevas primitivas impuestas por nuevos requisitos de salida. Por otro lado, es un motor TeX extendido que también comprende nuevas primitivas. Y, por otro lado, Object TeX es un sistema tipográfico completamente nuevo.**

Ahí está la cuarta mano. El formato Object TeX también es un formato basado en Plain TeX que contiene definiciones que involucran nuevas primitivas, por ejemplo, asignar valores predeterminados a métricas de medios.

## Aspose.TeX

Y Aspose.TeX es solo una API para el sistema Object TeX.

## ¿Por qué el nuevo TeX es Object?

Entonces, ¿por qué utilizamos "Objeto" en el nombre del sistema? La razón es que la salida real del motor Object TeX no es un archivo en el formato de salida, sino algún modelo *objeto* intermedio, que luego se transforma en un formato de destino.