---
translation: true
template: /templates/_template-java.md
linktitle: AMS-LÁTEX
title: 1. Introducción a AMS-LATEX | manual de látex
weight: 10
url: /java/introduction-to-ams-latex/
keywords: ams-latex, amsmath, opciones de amsmath, amsopn, amstext, amscd, amsthm, amsxtra, upref
description: Este artículo es una breve introducción al paquete amsmath y cubre brevemente sus opciones, así como los subpaquetes y extensiones disponibles.
lastmod: "2024-10-30"
---

{{<section overview>}}


*AMS*-LATEX versión 1.0 fue lanzada en 1990 y presentó la conversión original a LaTeX de las capacidades matemáticas en *AMS*-TEX de Michael Spivak por Frank Mittelbach y Rainer Schopf, quienes trabajaron como consultores de *AMS*, con la ayuda de Michael Downes del personal técnico de *AMS*. En 1994, se realizó el trabajo adicional con David M. Jones.

El paquete *Amsmath* acepta algunas opciones que afectan principalmente el posicionamiento de *límites* en varios operadores matemáticos o el posicionamiento de etiquetas de ecuaciones.

## Opciones de paquete *amsmath* disponibles

Las siguientes tres opciones se pueden usar como opciones de documento global (especificadas en el comando `\documentclass`) o como opciones de paquete *amsmath* cuando se carga con el comando `\usepackage`.

|||
|---|---|
| `reqno` **(predeterminado)** | Coloca los números de ecuación (etiquetas) a la derecha. |
| `leqno` | Coloca los números de ecuación (etiquetas) a la izquierda (predeterminado, cuando se utilizan las clases de documento *AMS*-LATEX). |
| `fleqn` | Coloca las ecuaciones con una sangría fija desde el margen izquierdo en lugar de centradas en la columna de texto. |

## Subpaquetes disponibles

En la distribución *AMS*-LATEX, también puede encontrar componentes que se pueden cargar de forma independiente mediante el comando `\usepackage`. Los siguientes paquetes más pequeños proporcionan algunas características del paquete *amsmath*:

|||
|---|---|
| `amsopn` | Proporciona `\DeclareMathOperator` para definir nuevos nombres de operadores como `\Ker` y `\esssup`. |
| `amstext` | Proporciona el comando `\text` para componer un fragmento de texto en el tamaño de letra correcto. |

## Paquetes de extensión

Los paquetes que se enumeran a continuación proporcionan funciones adicionales y deben cargarse explícitamente.
|||
|---|---|
| `amscd` | Define algunos comandos para facilitar la generación de diagramas conmutativos. |
| `amsthm` | Proporciona un método para declarar estructuras similares a teoremas y ofrece un entorno de ``prueba`. |
| `amsxtra` | Proporciona algunos elementos adicionales necesarios para la compatibilidad histórica, como `\fracwithdelims`, `\accentedsymbol` y comandos para colocar acentos como superíndices. |
| `upref` | Hace que `\ref` imprima números de referencia cruzada en una fuente vertical/romana independientemente del contexto. |