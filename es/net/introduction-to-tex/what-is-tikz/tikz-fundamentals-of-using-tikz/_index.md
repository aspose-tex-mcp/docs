---
translation: true
template: /templates/_template-net.md
title: Fundamentos del uso de TikZ | Aspose.TeX .NET
linktitle: Fundamentos de TikZ
weight: 19
url: /net/tikz-fundamentals-of-using-tikz/
keywords: fundamentos de TikZ, fundamentos de TikZ, tutorial de TikZ
description: Explora los principios fundamentales y los comandos básicos de TikZ para crear gráficos para tus documentos TeX y LaTeX.
lastmod: "2026-04-22"
---

{{<section overview>}}

En este capítulo, exploramos los principios y comandos fundamentales de TikZ. Comprender estos conceptos básicos le permitirá crear gráficos claros y expresivos para sus documentos.

## Sistema de coordenadas en TikZ

Los gráficos de TikZ se crean mediante coordenadas. Las coordenadas definen posiciones dentro de sus dibujos y pueden especificarse de diferentes maneras:

- **Coordenadas cartesianas (x,y)**:

```tex
\draw (0,0) -- (2,2);
```

- **Coordenadas polares (ángulo:radio)**:

```tex
\draw (0,0) -- (45:2);
```

Las coordenadas se pueden combinar libremente en un dibujo para lograr el resultado gráfico deseado.

## Dibujar formas básicas

TikZ permite crear fácilmente formas geométricas básicas:

- **Líneas y polilíneas**:

```tex
\draw (0,0) -- (1,1) -- (2,0);
```

- **Rectángulos**:

```tex
\draw (0,0) rectangle (2,1);
```

- **Círculos y elipses**:

```tex
\draw (1,1) circle (0.5);
\draw (3,1) ellipse (1 and 0.5);
```

## Colores y patrones de relleno

Los colores y los rellenos mejoran significativamente la claridad visual. Puede especificar los colores directamente o usar nombres predefinidos:

```tex
\draw[red, thick] (0,0) rectangle (1,1);
\draw[fill=blue!20] (2,0) circle (0.5);
```

La sintaxis `blue!20` significa un color azul con una intensidad del 20 %.

## Estilos y grosor de línea

TikZ permite modificar los estilos y el grosor de línea para mejorar la presentación gráfica:

- **Grosor de línea**:

```tex
\draw[ultra thick] (0,0) -- (1,1);
\draw[thin] (1,0) -- (2,1);
```

- **Líneas discontinuas y punteadas**:

```tex
\draw[dashed] (0,0) -- (2,2);
\draw[dotted] (2,0) -- (4,2);
```

## Nodos y etiquetas

Los nodos permiten añadir fácilmente anotaciones textuales:

```tex
\draw (0,0) -- (1,1) node[midway, above] {label};
```

Puede colocar las etiquetas con precisión respecto a sus elementos gráficos, lo que mejora la legibilidad.

## Trazados y curvas

Los trazados de TikZ pueden ser líneas rectas o curvas. Las curvas se crean mediante una sintaxis sencilla:

```tex
\draw (0,0) .. controls (1,2) and (3,-1) .. (4,1);
```

Los puntos de control moldean la curvatura intuitivamente.

## Agrupación de elementos

Agrupar elementos gráficos simplifica las transformaciones (como el escalado y la rotación):

```tex
\begin{scope}[rotate=45, scale=1.5]
  \draw (0,0) rectangle (1,1);
  \draw (1,1) circle (0.5);
\end{scope}
```

Los elementos dentro del ámbito se rotan y escalan juntos, manteniendo la alineación.

---
Dominar estos conceptos y comandos fundamentales de TikZ sentará una base sólida para crear gráficos sofisticados para sus documentos.

**Además, explore nuestra [aplicación web](https://products.aspose.app/tex/conversion/latex/) gratuita basada en la [API de Aspose.TeX para .NET](https://products.aspose.com/tex/net/) para conversiones de TeX rápidas y sencillas.**
