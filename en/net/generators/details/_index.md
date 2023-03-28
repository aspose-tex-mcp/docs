---
translation: true
title: HTML Details Generator - Online Tool and C# Code
template: /templates/_template-generators-child.md
description: HTML Details Generator lets you create HTML details tag for your website. You can preview, copy and use generated HTML and C# code.
url: /net/generators/details/
platformtag: net
generator: HTML Details Generator
element: HTML details tag
tag: details
---

{{<section banner>}}
---
h1: HTML Details Tag Generator
h2: Generate HTML and C# code for an HTML details element and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML <details> Tag Easily!
---

The `<details>` element in HTML creates a widget containing additional information only visible when the widget is in the "open" state. By default, the widget is in the "closed" state. However, you can click on the widget to switch between open and closed states to show or hide additional information contained in the tag. 
To use the `<details>` element, you must include a `<summary>` element to provide a visible heading for additional details. You can put any content in the `<details>` tag.

{{<section plugin>}}

{{< app/generator name="details" >}}

<br>
<h2> Create HTML Details Tag in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add a `<details>` tag, see the C# code example below:

{{< /app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Details Tag in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create a `<details>` element. The CreateElement() method creates the HTML element specified by tagName, in our case the tagName is "details".
2. In the same way, create a `<summary>` element and set [TextContent](https://reference.aspose.com/html/net/aspose.html.dom/element/textcontent/) property for it.
3. Use [AppendChild()](https://reference.aspose.com/html/net/aspose.html.dom/node/appendchild/) method to add text content into the `<summary>` element. 
4. Create text content for the `<details>` element using [CreateTextNode()](https://reference.aspose.com/html/net/aspose.html.dom/document/createtextnode/) method and add it using AppendChild() method.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With HTML Generators, all the hard work has already been done for you. All you have to do is copy and paste. Clear, safe and simple!"
---