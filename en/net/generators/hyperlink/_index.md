---
translation: true
title: HTML Hyperlink Generator - Online Tool and C# Code
template: /templates/_template-generators-child.md
description: HTML Hyperlink Generator creates HTML anchor tag and C# code for this element. You can generate code and use it in your own website or C# project.
url: /net/generators/hyperlink/
platformtag: net
generator: HTML Hyperlink Generator
element:    HTML anchor tag
tag: hyperlink
---

{{<section banner>}}
---
h1: HTML Hyperlink Generator
h2: Generate HTML and C# code for an HTML anchor tag and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate <a> Anchor Tag Easily!
---

The `<a>` tag (anchor tag) is one of the most used and well-known tags in HTML. With its href attribute, `<a>` element is used to create a hyperlink on the webpage, email addresses, files, locations on the same page, or anything else a URL can address.

{{<section plugin>}}

{{< app/generator name="hyperlink" >}}

<br>
<h2> Attributes </h2>

The `<a>` element's attributes include: *href*, *rel*, *target*, *download*, *form*, etc. 
 - The `href` attribute specifies the URL of the page the link points to.
 - The `download` attribute specifies that the target will be downloaded when a user clicks on the hyperlink. This causes the browser to treat the linked URL as a download. The attribute can be used with or without a value.
 - The `rel` attribute specifies the relationship between the current document and the linked document.
 - The `target` attribute specifies where to open the linked document.
<br><br>

<h2> Create HTML Hyperlink in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add an `<a>` tag, see the C# code example below. You can create a hyperlink with a few lines of C# code:

{{< /app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Hyperlink in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create an [HTMLAnchorElement.](https://reference.aspose.com/html/net/aspose.html/htmlanchorelement/)
2. Set values for the [Href](https://reference.aspose.com/html/net/aspose.html/htmlanchorelement/href/), [Target](https://reference.aspose.com/html/net/aspose.html/htmlanchorelement/target/) and other required attributes.
3. Create text content for the `<a>` ancor tag using [CreateTextNode()](https://reference.aspose.com/html/net/aspose.html.dom/document/createtextnode/) method and add it using AppendChild() method.
4. Copy C# code for the HTML hyperlink and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With HTML Generators, all the hard work has already been done for you. All you have to do is copy and paste. Clear, safe and simple!"
---