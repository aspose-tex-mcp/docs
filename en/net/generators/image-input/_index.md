---
translation: true
title: HTML Image Input Generator - online tool and C# code
template: /templates/_template-generators-child.md
description: Generate HTML Image Button, preview the result and copy the generated HTML and C# code to your website.
url: /net/generators/image-input/
platformtag: net
family: html
generator: HTML Image Input Generator
element: HTML image input
tag: image-input
---

{{<section banner>}}
---
h1: HTML Image Input Generator
h2: Generate HTML and C# code for an HTML Image Input and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML Image Button 
---

An [input](https://html.spec.whatwg.org/multipage/input.html#the-input-element) element with `type='image'` is used to create graphical submit button that takes the form of an image rather than text. HTML Image Input Generator helps to generate HTML code for an image submit button by selecting attributes like `name`, `src`, `alt`, `width`, `height`, and `autofocus`. Easily generate image button tag with HTML syntax! 

{{<section plugin>}}

{{<app/generator name="image-input" >}}

- The `src` attribute specifies the URL of the image file to be displayed to represent the graphical submit button.
- The `width` and `height` attributes specify numbers that indicate the width and height to draw the image in CSS pixels.
- The `alt` attribute provides alternative text to use as the button's label if the image cannot be displayed.
- The `autofocus` boolean attribute, if present, specifies that the `<input>` element should automatically get focus when the page loads.
<br>

<h2> Create Image Button in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add an image button, see the C# code example below:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Image Input in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create [HTMLInputElement.](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/) It creates the HTML element specified by tagName.
1. Set values for the [Type](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/type/), [Name](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/name/) and [Src](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/src/) attributes.
1. Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add `alt`, `width`, `height`, and `autofocus` attributes.
1. Copy C# code for the image button and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With these HTML Generators, all the hard work has already been done for you. All you have to do is copy and paste. Clear, safe and simple!"
---