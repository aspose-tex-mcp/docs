---
translation: true
title: Underline Text HTML Generator - Online Tool and C# Code
template: /templates/_template-generators-child.md
description: Generate Underline HTML tag, preview the result and copy the generated HTML and C# code to your website. 
url: /net/generators/underline/
platformtag: net
family: html
generator: Underline Text HTML Generator
element: Underline HTML tag
tag: underline
---

{{<section banner>}}
---
h1: Underline Text HTML Generator
h2: Generate HTML and C# code for an underline HTML tag and use it in your website or C# project.
---

{{<section overview>}}
---
h2: Generate Underline HTML Tag on the fly!
---

The `<u>` HTML tag represents some text that is styled differently from normal text, such as misspelt words. The content inside the `<u>` tag is typically displayed with a simple solid underline. <br>
Avoid using the `<u>` element where it could be confused with a hyperlink! So, it is not recommended to underline text unless you really need it. If you need to [emphasize text](/html/{{lang.url-fragment}}net/generators/emphasize/), use the `<em>` tag. Use the `<strong>` tag to give [strong importance](/html/{{lang.url-fragment}}net/generators/strong/) to the text. These elements were created specifically for those purpose, and browsers usually render this text accordingly.

{{<section plugin>}}

{{<app/generator name="unarticulated" >}}

<br>
<h2> Create Underline HTML Tag in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add an underline HTML tag, see the C# example below. You can create the desired element with a few lines of code:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create Underline HTML Tag in C#
---

1.  Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create an `<u>` element. The Document.CreateElement() method creates the HTML element specified by tagName, in our case the tagName is "u".
2. Create text content using [CreateTextNode()](https://reference.aspose.com/html/net/aspose.html.dom/document/createtextnode/) method.
3. Use [AppendChild()](https://reference.aspose.com/html/net/aspose.html.dom/node/appendchild/) method to add the text content into the HTML `<u>` element.
4. Copy code for the underline HTML tag and use it in your C# project. 

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "Use HTML Generators to build highly customizable HTML elements with no coding! Clear, safe and simple!"
---