---
translation: true
title: HTML File Input Generator - online tool and C# code
template: /templates/_template-generators-child.md
description: Generate HTML file input, preview the result and copy the generated HTML and C# code to your website.
url: /net/generators/file/
platformtag: net
family: html
generator: HTML File Input Generator
element: HTML file input
tag: file
---

{{<section banner>}}
---
h1: HTML File Input Generator
h2: Generate HTML and C# code for an HTML file input and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML File Input Easily!
---

An [input](https://html.spec.whatwg.org/multipage/input.html#the-input-element) element with `type="file"` allows the user to select one or more files from their device's storage. Once chosen, the files can be uploaded to a server using form submission, or manipulated using JavaScript code and the File API. Easily generate file input tag with HTML syntax! 

{{<section plugin>}}

{{<app/generator name="file" >}}

<br>
<h2> Attributes </h2>

HTML File Input Generator helps to generate HTML code for input tag with `type='file'` by selecting attributes like `name`, `accept`, and `multiple`. 
 - The value of the `accept` attribute is a string containing one or more unique file type specifiers separated by commas. These can be file extensions including a dot, such as .jpg, .png, .pdf, or MIME type strings without extensions, such as audio/* - any audio file is accepted. If the attribute value is left empty, all file types are accepted. 
 - When the `multiple` boolean attribute is set, the file input allows the user to choose more than one file.
<br><br>

<h2> Create HTML File Input in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add an HTML file input, see the C# example below. You can create the desired element with a few lines of code:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML File Input in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create [HTMLInputElement.](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/) It creates the HTML element specified by tagName.
1. Set values for the [Type](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/type/), [Name](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/name/) and [Accept](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/accept/) attributes.
1. Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add `multiple` attribute.
1. Copy C# code for the HTML file input and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With these HTML Generators, all the hard work has already been done for you. All you have to do is copy and paste. Clear, safe and simple!"
---