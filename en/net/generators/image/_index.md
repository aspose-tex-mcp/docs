---
translation: true
title: HTML Image Tag Generator - Online Tool and C# Code
template: /templates/_template-generators-child.md
description: HTML Image Generator creates HTML and C# code for an HTML image element. You can generate code and use it in your own website or C# project.
url: /net/generators/image/
platformtag: net
family: html
generator: HTML Image Generator
element: HTML image
tag: image
---

{{<section banner>}}
---
h1: HTML Image Generator
h2: Generate HTML and C# code for an HTML image element and use it in your website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML <img> Tag Easily!
---

The `<img>` tag is used to embed an image in an HTML page. Using an HTML image element will certainly make your web page more interesting. Images are not technically inserted into a web page, but images are linked to web pages. The `<img>` tag creates a holding space for the referenced image.

{{<section plugin>}} 

{{<app/generator name="image" >}}

<br>
<h2> Attributes </h2>

 - The `src` attribute is required and includes the path of an image to a particular document. In other words, it is used to link images in HTML documents.
 - The `alt` attribute is optional but incredibly useful for accessibility. It contains a text description of the image that is displayed on the page if the image cannot be loaded for some reason.
 - It is recommended to always specify the `width` and `height` of the image. If these attributes are not specified, the page may flicker while the image is loading.  
<br><br>

<h2> Create HTML Image Element in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add an `<img>` element, see the C# code example below:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Image Element in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create an [HTMLImageElement.](https://reference.aspose.com/html/net/aspose.html/htmlimageelement/) In an HTML document, the Document.CreateElement() method creates the HTML element specified by tagName, in our case the tagName is "img".
2. Set value for the required `src` attribute.
3. Copy C# code for the HTML image element and use it in your project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "Use HTML Generators to build highly customizable HTML elements with no coding! Clear, safe and simple!"
---