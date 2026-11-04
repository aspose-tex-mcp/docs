---
translation: true
template: /templates/_template-net.md
title: ¿Qué es LaTeX?
linktitle: ¿Qué es LaTeX?
weight: 16
url: /net/what-is-latex/
keywords: ¿Qué es el LaTeX? ¿Qué es el LaTeX?
description: Para responder a la pregunta “¿Qué es LaTeX?” recuerde que una de sus características más impresionantes es el Nuevo Esquema de Selección de Fuentes(NFSS).
lastmod: "2026-11-04"
---

{{<section overview>}}

Entonces, ¿qué es LaTeX?

LaTeX es el formato [TeX](/tex/{{lang.url-fragment}}net/what-is-tex/), en resumen.

LaTeX (*LAH-tekh o LAY-tekh*, a menudo estilizado como LATEX) es un sistema de software para la preparación de documentos que fue escrito originalmente a principios de la década de 1980 por <a href="https://en.wikipedia.org/wiki/Leslie_Lamport" target=_blank rel="nofollow">Leslie Lamport</a> en <a href="https://en.wikipedia.org/wiki/SRI_International" target=_blank rel="nofollow">SRI International</a>. Esto es lo que cuenta <a href="https://en.wikipedia.org/wiki/LaTeX" target=_blank rel="nofollow">Wikipedia</a>.

Respondiendo a la pregunta "¿Qué es LaTeX?" Nos gustaría mencionar algunas de sus características.

Una de las características más impresionantes de LaTeX es el nuevo esquema de selección de fuentes (NFSS). Es el subsistema de macros el que le permite cambiar las propiedades individuales de la fuente actual, en lugar de definir una nueva fuente como un todo, como funcionaba en el TeX original (Plain TeX tampoco ofrecía mucho para esto). Por ejemplo, tiene la fuente actual que es Computer Modern Roman cursiva y desea cambiar a una fuente en negrita del mismo tipo que se encuentra físicamente en un archivo de fuente diferente. En TeX original, necesitas controlar las secuencias asignadas a los nombres de los archivos de fuentes, por lo que para cambiar, solo necesitas llamar a otro comando. Pero el precio es demasiadas secuencias de control. En LaTeX solo necesitas pedirle al motor que cambie el tipo de letra. Seleccionará la fuente actual adecuada para usted.

Otra característica son las denominadas clases de documentos. Estos son archivos de entrada auxiliares que contienen los valores de los parámetros internos de TeX correspondientes a un tipo de documento específico, como un libro, artículo, carta o cualquier otra cosa.

LaTeX también incluye soporte para varias funciones que pueden resultar convenientes para el autor de un documento. Estas características generalmente se recopilan en archivos de entrada auxiliares llamados paquetes. En los paquetes puedes encontrar herramientas avanzadas para composición tipográfica matemática, dibujo de gráficos, soporte para fuentes que no forman parte de la distribución LaTeX, etc. Incluso para dibujar fórmulas químicas 2D.

Aquí hay un ejemplo relativamente pequeño:

```tex
\documentclass[]{article}
%%%%%%%%%%%%%%%%%%%
% Packages/Macros %
%%%%%%%%%%%%%%%%%%%
\usepackage{amssymb,latexsym,amsmath}     % Standard packages
%%%%%%%%%%%
% Margins %
%%%%%%%%%%%
\addtolength{\textwidth}{1.0in}
\addtolength{\textheight}{1.00in}
\addtolength{\evensidemargin}{-0.75in}
\addtolength{\oddsidemargin}{-0.75in}
\addtolength{\topmargin}{-.50in}
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
% Theorem/Proof Environments %
%%%%%%%%%%%%%%%%%%%%%%%%%%%%%%
\newtheorem{theorem}{Theorem}
\newenvironment{proof}{\noindent{\bf Proof:}}{$\hfill \Box$ \vspace{10pt}}  
%%%%%%%%%%%%
% Document %
%%%%%%%%%%%%
\begin{document}
\makeatletter
\def\@date{May 17, 2021}
\makeatother

\title{Sample \LaTeX ~File}
\author{David P. Little}
\maketitle
\begin{abstract}
This document represents the output from the file ``sample.tex" once compiled using your favorite \LaTeX compiler.  This file should serve as a good example of the basic structure of a ``.tex" file as well as many of the most basic commands needed for typesetting documents involving mathematical symbols and expressions.  For more of a description on how each command works, please consult the links found on our course webpage.
\end{abstract}
\section{Lists}
%%%%%%%%%%%%%%%
\begin{enumerate}
\item {\bf First Point (Bold Face)}
\item {\em Second Point (Italic)}
\item {\Large Third Point (Large Font)}
    \begin{enumerate}
        \item {\small First Subpoint (Small Font)} 
        \item {\tiny Second Subpoint (Tiny Font)} 
        \item {\Huge Third Subpoint (Huge Font)} 
    \end{enumerate}
\item[$\bullet$] {\sf Bullet Point (Sans Serif)}
\item[$\circ$] {\sc Circle Point (Small Caps)} 
\end{enumerate}
\section{Equations}
%%%%%%%%%%%%%%%%%%%
\subsection{Binomial Theorem}
\begin{theorem}[Binomial Theorem]
For any nonnegative integer $n$, we have
$$(1+x)^n = \sum_{i=0}^n {n \choose i} x^i$$
\end{theorem}
\subsection{Taylor Series}
The Taylor series expansion for the function $e^x$ is given by
\begin{equation}
e^x = 1 + x + \frac{x^2}{2} + \frac{x^3}{6} + \cdots = \sum_{n\geq 0} \frac{x^n}{n!}
\end{equation}
\subsection{Sets}
\begin{theorem}
For any sets $A$, $B$ and $C$, we have
$$ (A\cup B)-(C-A) = A \cup (B-C)$$
\end{theorem}
\begin{proof}
\begin{eqnarray*}
(A\cup B)-(C-A) &=& (A\cup B) \cap (C-A)^c\\
&=& (A\cup B) \cap (C \cap A^c)^c \\
&=& (A\cup B) \cap (C^c \cup A) \\
&=& A \cup (B\cap C^c) \\
&=& A \cup (B-C)
\end{eqnarray*}
\end{proof}
\section{Tables}
%%%%%%%%%%%%%%%%
\begin{center}
\begin{tabular}{l||c|r}
left justified & center & right justified \\ \hline
1 & 3.14159 & 5 \\
2.4678 & 3 &  1234 \\ \hline \hline
3.4678 & 6.14159 & 1239
\end{tabular}
\end{center}
\section{A Picture}
%%%%%%%%%%%%%%%%%%%
\begin{center}
\begin{picture}(100,100)(0,0)
\setlength{\unitlength}{1pt}
\put(20,70){\circle{30}}  \put(20,70){\circle*{10}}   % left eye
\put(80,70){\circle{30}}  \put(80,70){\circle*{10}}   % right eye
\put(40,40){\line(1,2){10}} \put(60,40){\line(-1,2){10}} \put(40,40){\line(1,0){20}} % nose
\put(50,20){\oval(80,10)[b]} % mouth
\multiput(0,90)(4,0){10}{\line(1,3){4}}  % left eyebrow
\multiput(100,90)(-4,0){10}{\line(-1,3){4}}  % right eyebrow
\end{picture}
\end{center}
\end{document}
```

Y aquí hay dos páginas de resultados:

<a href="/tex/net/what-is-latex/example-page-1.png" style="display:inline-block;width:49%;" aria-label="Página de ejemplo 1">![Página de ejemplo 1](/tex/images/net/tutorial/example-page-1.png)</a>

<a href="/tex/net/what-is-latex/example-page-2.png" style="display:inline-block;width:49%;" aria-label="Página de ejemplo 2">![Página de ejemplo 2](/tex/images/net/tutorial/example-page-2.png)</a>


Naturalmente, no pretendemos tener una respuesta completa a la pregunta "¿Qué es LaTeX?", ya que se trata de una cantidad de información bastante grande. Dado que escribir un archivo LaTeX sigue siendo programación, tendrás que dedicar algo de tiempo si quieres familiarizarte mejor con él. ¿Lo quieres o no?

**También puede consultar la [aplicación web](https://products.aspose.app/tex/conversion/latex/) gratuita creada en base a [Aspose.TeX para .NET API](https://products.aspose.com/tex/net/).**


## Marcado lógico frente a formato directo

A diferencia de los programas de autoedición tradicionales de tipo WYSIWYG («lo que ves es lo que obtienes»), en los que la creación de contenido y el estilo visual ocurren simultáneamente, LaTeX impone una separación estricta entre el contenido y la presentación.

Al escribir en LaTeX, los autores utilizan un marcado semántico para definir qué son los elementos (`\section{Introduction}`, `\begin{equation}`), en lugar de preocuparse por su apariencia. El motor de composición subyacente gestiona automáticamente reglas complejas de diseño, espaciado entre caracteres (*kerning*), saltos de línea, numeración de páginas y alineación de fórmulas matemáticas. Esto garantiza una coherencia tipográfica absoluta en documentos técnicos extensos y complejos o en artículos científicos, liberando a desarrolladores e investigadores de la tediosa tarea de dar formato manualmente.

## Características principales

A continuación, se presenta una tabla comparativa que detalla cómo se gestionan mediante programación las funciones estándar de LaTeX dentro de Aspose.TeX:

| **Característica/Sistema** | **Distribución TeX estándar (CLI)** | **Motor Aspose.TeX para .NET** |
| :- | :- | :- |
| **Composición matemática** | Gestionada mediante `amsmath`/`amssymb` | Analizada y renderizada de forma nativa en formatos vectoriales o de mapa de bits (*raster*) |
| **Clases de documento** | Requiere archivos `.cls` locales en el disco | Se cargan mediante una interfaz personalizada/virtual `IInputWorkingDirectory` |
| **Referencias cruzadas e índice (TOC)** | Requiere múltiples pasadas desde la línea de comandos | Una segunda pasada se activa con la opción `TeXOptions.Repeat` |
| **Formatos de salida** | Genera DVI, PS o PDF mediante herramientas independientes | Conversión directa en un solo paso a PDF, XPS, SVG, PNG, JPEG, BMP o TIFF |

**Para profundizar más:**

- [Entrada/Salida en TeX (tex-io)](/tex/{{lang.url-fragment}}net/tex-io/): Descubre cómo `IInputWorkingDirectory` e `IOutputWorkingDirectory` gestionan los recursos en flujos de datos (*streams*) y en el disco.
- [Gráficos en LaTeX (latex-graphics)](/tex/{{lang.url-fragment}}net/latex-graphics/): Inclusión de imágenes externas mediante `\includegraphics` utilizando el paquete `graphicx`. - [Aspose.TeX y Object TeX](/tex/{{lang.url-fragment}}net/aspose-tex-and-object-tex/): Comprensión del modelo de objetos gestionados subyacente.