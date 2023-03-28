---
translation: true
title: HTML Table Generator - online tool and C# code
template: /templates/_template-generators-child.md
description: HTML Table Generator creates HTML and C# code for a table element. You can generate code and use it in your own website or C# project.
url: /net/generators/table/
platformtag: net
family: html
generator: HTML Table Generator
element: HTML table
tag: table
---

{{<section banner>}}
---
h1: HTML Table Generator
h2: Generate HTML and C# code for an HTML table element and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML Table Easily!
---

The [HTML table element](https://html.spec.whatwg.org/multipage/tables.html#the-table-element) defines an HTML table. It represents the information presented in a two-dimensional table consisting of rows and columns of cells containing data. An HTML table consists of one `<table>` element and one or more `<tr>`, `<th>`, and `<td>` elements that  define a table row, table header, and table cell.

{{<section plugin>}}

{{<app/generator name="table" >}}

<br>
<h2> Attributes </h2>

The `<table>` element can include global attributes such as `style`, `border`, `align`, `width`, etc.

 - The `border` attribute specifies the border width. A value of "0" means no border.
 - The `align` attribute indicates how the table must be aligned inside the containing document. It may have the following values: left, center, right.
 - The `width` attribute specifies the width of the table. 
 <br><br>

<h2> Create HTML Table in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add an `<table>` element, see the C# code example below:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Table in C#
---

1.  Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of the Document class to create an [HTMLTableElement.](https://reference.aspose.com/html/net/aspose.html/htmltableelement/)
2. Set values for the [Style](https://reference.aspose.com/html/net/aspose.html/htmlelement/style/), [Align](https://reference.aspose.com/html/net/aspose.html/htmltableelement/align/), [Border](https://reference.aspose.com/html/net/aspose.html/htmltableelement/border/) attributes, etc.
3. Use the [InsertRow()](https://reference.aspose.com/html/net/aspose.html/htmltableelement/insertrow/) and [InsertCell()](https://reference.aspose.com/html/net/aspose.html/htmltablerowelement/insertcell/) methods to add rows and columns for the HTML table.
3. Copy C# code for the HTML table and use it in your project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "Use HTML Generators to build highly customizable HTML elements with no coding! Clear, safe and simple!"
---