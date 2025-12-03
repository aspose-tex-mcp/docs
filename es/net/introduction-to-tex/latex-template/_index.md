---
translation: true
template: /templates/_template-net.md
title: 'Plantillas LaTeX - guía de inicio rápido'
linktitle: Plantillas de látex
type: docs
weight: 100
url: /net/latex-templates/
description: Aprenda qué son las plantillas LaTeX, cómo usarlas y crearlas, dónde descargar las más populares y un flujo de trabajo rápido con fragmentos listos para copiar.
keywords: LaTeX, plantilla, clase, estilo, Al dorso, CTAN, bibliografía, Beamer, tesis, CV
lastmod: "2025-12-03"
---

{{<section overview>}}

# Guía de plantillas LaTeX

## ¿Qué es una plantilla LaTeX?

Una plantilla LaTeX incluye una **clase** (`.cls`), un **estilo** (`.sty`), archivos de ejemplo `.tex` y recursos de soporte (logotipos, archivos de bibliografía, etc.) que definen el diseño, la tipografía y la estructura de un tipo de documento específico: artículo de revista, tesis, CV, póster, presentación de diapositivas y más.

## Cómo utilizar plantillas LaTeX

1. **Descarga** el zip o clona el repositorio.  
2. Abra el archivo principal `.tex` (a menudo llamado `main.tex` o `article.tex`).  
3. Cargue la clase o estilo proporcionado por la plantilla y siga la “estructura” del README (página de título, resumen, secciones, bibliografía).

```latex
\documentclass[options]{mytemplate}   % class supplied by the template
\usepackage{mytemplate}               % sometimes a .sty instead of .cls
\begin{document}
  \title{My Title}
  \author{Me}
  \maketitle
  % <content>
\end{document}
```

Compile con `pdflatex`, `latexmk -pdf` o el botón “Recompilar” al dorso.

## Cómo crear tu propia plantilla

| **Objetivo** | **Archivo recomendado** | **Esqueleto mínimo** |
|------|------------------|------------------|
| Control total sobre la estructura del documento | **Clase** (`.cls`) | Ver bloque de código a continuación |
| Solo macros o formato adicionales | **Estilo** (`.sty`) | – |
| Distribución | Archivo zip o repositorio de GitHub (incluye clase/estilo, `.bib` opcional, logotipos, README) | – |

### Esqueleto de clase mínima (`mytemplate.cls`)

```latex
% mytemplate.cls – a very simple article‑style class
\NeedsTeXFormat{LaTeX2e}
\ProvidesClass{mytemplate}[2025/12/03 v1.0 My custom class]
\LoadClass[12pt]{article}   % inherit from article

% ---- custom settings ----
\RequirePackage{geometry}
\geometry{margin=2cm}
\RequirePackage{fontspec}
\setmainfont{Latin Modern Roman}

% ---- user‑level commands ----
\newcommand\mytitle[1]{\centerline{\LARGE\bfseries #1}}
\endinput
```

Úselo con `\documentclass{mytemplate}` en su documento.

## Dónde descargar plantillas LaTeX

- **Galería al dorso**: la colección pública más grande (≈4000 plantillas gratuitas).  
  <https://www.overleaf.com/gallery>
- **CTAN (ComprehensiveTeXArchive Network)**: repositorio oficial para clases específicas de revistas.  
  <https://ctan.org/>
- **GitHub/GitLab**: muchos autores publican plantillas de conferencias o tesis de código abierto.  
- Páginas web de universidades/institutos: la mayoría de las escuelas albergan una plantilla de tesis/disertación “oficial”.

## Plantillas más utilizadas/mejor valoradas

| **#** | **Plantilla** | **Uso típico** |
|---|----------|-------------|
| 1 | **IEEEtran** (`ieeetran.cls`) | Artículos de conferencias y revistas del IEEE |
| 2 | **SpringerLNCS** (`llncs.cls`) | Apuntes de informática |
| 3 | **Artículo de Elsevier** (`elsarticle.cls`) | Revistas de Elsevier |
| 4 | **CV moderno y sencillo** | Currículum vitae de una página |
| 5 | **Tesis clásica** (`classicthesis.sty`) | Libro/tesis con tipografía elegante |
| 6 | **Beamer** (`beamer.cls`) | Presentaciones de diapositivas |
| 7 | **a0poster / tikzposter** | Pósteres científicos grandes |
| 8 | **Tesis universitarias** (p. ej., `cambridgephd.cls`) | Tesis institucionales de doctorado/máster |
| 9 | **Astronomía y Astrofísica** (`aa.cls`) | Artículos de revistas de Astronomía y Astrofísica |
| 10 | **Artículo básico de revista académica** | Introducción sencilla para artículos (al dorso) |

## Flujo de trabajo rápido para usuarios nuevos

1. **Elija una plantilla** → haga clic en “Abrir al dorso” **o** descargue el ZIP.  
2. **Editar campos de marcador de posición** (`\title{}`, `\author{}`, etc.).  
3. **Compilar** → Aparece PDF.  
4. Si trabaja localmente: descomprima → ejecute `latexmk -pdf main.tex` (o `pdflatex` + `biber` según sea necesario).  
5. **Exporte** el PDF o envíe el código fuente a un repositorio Git para controlar la versión.

## Errores y consejos comunes

- **Paquetes faltantes**: instálelo con el administrador de su distribución (`tlmgr install <pkg>` o consola MiKTeX).  
- **Clases obsoletas**: al dorso se utiliza la última versión de TeXLive; actualice su instalación local de TeX con regularidad.  
- **Motor de bibliografía**: muchas plantillas modernas esperan "biber". Ejecute `biber <basename>` después del primer pase de LaTeX.  
- **Activos de marca**: reemplace logotipos, archivos PDF en color o archivos ".sty" que definen los colores institucionales.  
- **Comandos personalizados**: manténgalos en un archivo `.sty` separado; luego podrá reutilizar el mismo diseño en varios documentos.


## ¿Qué pasa con Aspose?

Cuando necesita manipular los archivos PDF generados a partir de LaTeX (fusionarlos, marcarlos o convertirlos a otros formatos) en una aplicación .NET, Java o Python, bibliotecas como **Aspose.TeX** proporcionan una API independiente del idioma para trabajar con archivos PDF sin necesidad de una cadena de herramientas LaTeX completa.

---

### TL;DR Hoja de trucos

```text
¿Qué?                → Diseño prediseñado (clase+estilo+recursos)
¿Usar?               → \documentclass{mytemplate} + seguir el README
¿Crear?              → Escribir .cls o .sty → empaquetar recursos → zip/GitHub
¿Obtener?            → Galería Overleaf, CTAN, GitHub, sitios universitarios
Los 10 más populares → IEEEtran, llncs, elsarticle, modern-simple-cv,
                      classicthesis, beamer, a0poster, tesis UNICAMP,
                      aa.cls, artículo básico de revista académica
```

¡Feliz tipografía!