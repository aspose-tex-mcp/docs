---
translation: true
title: HTML List Tag Generator - online tool and C# code
template: /templates/_template-generators-child.md
description: HTML List Tag Generator creates HTML ordered and unordered lists and C# code for these elements. Generate and use it in your project.
url: /net/generators/list/
platformtag: net
generator: HTML List Tag Generator
element: HTML list tag
tag: list
---

{{<section banner>}}
---
h1: HTML List Tag Generator
h2: Generate HTML and C# code for an HTML ordered and unordered lists and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: HTML Ordered & Unordered Lists Generator
---

The `<ol>` and `<ul>` elements are a list of elements. The `<ol>` and `<ul>` HTML elements represent ordered and unordered lists, respectively—usually displayed as numbered or bulleted lists. They differ in that with the `<ol>` element, the order makes sense, while the `<ul>` element is for grouping a set of elements that do not have a numeric order, and their order in the list does not matter.

{{<section plugin>}}

{{< app/generator name="list" >}}

<br><br>

<h2> Create HTML Ordered List in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add the `<ol>` element, see the C# code example below. You can create an ordered list with a few lines of C# code:

{{< /app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Ordered List in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create create an `<ol>` element. The CreateElement() method creates an HTML element specified by tagName, in our case the tagName is "ol".
2. Then, in the same way, use the CreateElement() method to create `<li>` list-item elements. 
3. Create text content for the `<li>` item tags using [CreateTextNode()](https://reference.aspose.com/html/net/aspose.html.dom/document/createtextnode/) method.
4. Use [AppendChild()](https://reference.aspose.com/html/net/aspose.html.dom/node/appendchild/) method to add text content into the `<li>` elements. 
5. Copy C# code for the HTML ordered list and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With HTML Generators, all the hard work has already been done for you. All you have to do is copy and paste. Clear, safe and simple!"
---