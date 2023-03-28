---
translation: true
title: Quote & Blockquote HTML Generator - Online Tool and C# Code
template: /templates/_template-generators-child.md
description: Generate Quote & Blockquote HTML tag, preview the result and copy the generated HTML and C# code to your website.
url: /net/generators/quote-blockquote/
platformtag: net
family: html
generator: Quote & Blockquote HTML Generator
element: Quote or Blockquote HTML tag
tag: quote-blockquote
---

{{<section banner>}}
---
h1: Quote & Blockquote HTML Generator
h2: Generate HTML and C# code for an HTML Quote & Blockquote tag and use it in your website or C# project.
---

{{<section overview>}}
---
h2: Generate Quote and Blockquote HTML Tags on the fly!
---

The `<q>` HTML tag is a standard quotation tag used for short quotations that don't require paragraph breaks. Most modern browsers implement this by surrounding the text in quotation marks. The `<blockquote>` HTML element indicates that the enclosed text is an extended quotation. Usually, this is rendered visually by indentation. A URL for the source of the quotation may be given using the `cite` attribute.


{{<section plugin>}}

{{<app/generator name="quote-blockquote" >}}

<br>
<h2> Attributes </h2>

The `cite` attribute specifies the source URL of the quote. This attribute is intended to point to information explaining the context or the reference for the quote.
<br><br>

<h2> Create HTML Quote and Blockquote HTML Tags in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add Quote and Blockquote HTML tags, see the C# example below:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create Quote HTML Tag in C#
---

1.  Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create an HTML `<q>` element. In an HTML document, the Document.CreateElement() method creates the [HTMLQuoteElement](https://reference.aspose.com/html/net/aspose.html/htmlquoteelement/) specified by tagName, in our case the tagName is "q".
2. Set value for the [Cite](https://reference.aspose.com/html/net/aspose.html/htmlquoteelement/cite/) attribute.
2. Create text content using [CreateTextNode()](https://reference.aspose.com/html/net/aspose.html.dom/document/createtextnode/) method.
3. Use [AppendChild()](https://reference.aspose.com/html/net/aspose.html.dom/node/appendchild/) method to add text content into the `<q>` element.
4. Copy C# code for the HTML `<q>` tag and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "Use HTML Generators to build highly customizable HTML elements with no coding! Clear, safe and simple!"
---