---
translation: true
title: Bi-Directional Override HTML Generator - Online Tool and C# Code
template: /templates/_template-generators-child.md
description: HTML BDO Generator creates HTML and C# code for an HTML bdo tag. You can generate code and use it in your own website or C# project.
url: /net/generators/bdo/
platformtag: net
generator: HTML BDO Generator
element: HTML bdo tag
tag: bdo
---

{{<section banner>}}
---
h1: Bi-Directional Override HTML Generator
h2: Generate HTML and C# code for an HTML bdo tag and use it in your website or C# project.
---

{{<section overview>}}
---
h2: Generate Bi-Directional Override HTML Tag Easily!
---

The [bdo](https://html.spec.whatwg.org/multipage/text-level-semantics.html#the-bdo-element) HTML element overrides the current direction of the text so that the text inside is rendered in a different direction. BDO stands for Bi-Directional Override. The HTML `<bdo>` tag specifies the direction of the content within it to be displayed in the browser from left-to-right or right-to-left. The `<bdo>` tag is useful for right-to-left languages such as Arabic, Persian and Hebrew.

{{<section plugin>}}

{{<app/generator name="bi-directional-override" >}}

<br>
<h2> Attributes </h2>

HTML BDO Generator helps to generate an HTML bdo tag by selecting attribute like `dir`, `spellcheck`, etc. The `dir` attribute is required. It defines the direction in which text should be rendered in this element's contents. Possible values are: *rtl* and *ltr*. 
<br><br>

<h2> Create HTML BDO Tag in C#</h2>

If you want to use the HTML editing features in your product or programmatically add an HTML `<bdo>` tag, see the C# example below. You can create the desired element with a few lines of code:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML BDO Tag in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create a `<bdo>` element. In an HTML document, the Document.CreateElement() method creates the HTML element specified by tagName, in our case the tagName is "bdo".
2. Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add `dir` and other required attributes.
3. Create text content using [CreateTextNode()](https://reference.aspose.com/html/net/aspose.html.dom/document/createtextnode/) method.
4. Use [AppendChild()](https://reference.aspose.com/html/net/aspose.html.dom/node/appendchild/) method to add text content into the `<bdo>` element. 
5. Copy C# code for the HTML bdo tag and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "Use HTML Generators to build highly customizable HTML elements with no coding! Clear, safe and simple!"
---