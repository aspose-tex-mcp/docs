---
translation: true
title: HTML Progress Generator - online tool and C# code
template: /templates/_template-generators-child.md
description: HTML Progress Generator creates HTML progress bar and C# code for this element. Generate code and use it in your own website or C# project.
url: /net/generators/progress/
platformtag: net
generator: HTML Progress Generator
element: HTML progress tag
tag: progress
---

{{<section banner>}}
---
h1: HTML Progress Generator
h2: Generate HTML and C# code for an HTML progress bar and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML <progress> Tag on the fly!
---

The `<progress>` HTML element displays an indicator showing the completion progress of a task, typically displayed as a progress bar. It is not used to indicate disk space or device charge. So, the `<progress>` tag should not be confused with the `<meter>` tag, which is used to [display a gauge.](/html/{{lang.url-fragment}}net/generators/meter/)

{{<section plugin>}}

{{< app/generator name="progress" >}}

<br>
<h2> Attributes </h2>

 - The `max` attribute specifies how much work the task requires in total. If not specified the default value is 1.0.
 - The `value` attribute indicates how much of the task was completed. By removing the `value` attribute, you create an indeterminate progress bar showing progress is being made, but it's unclear how much more work is left before the task completes.
<br><br>

<h2> Create HTML Progress Tag in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add a `<progress>` element, see the C# code example below. You can create a progress bar with a few lines of C# code:

{{< /app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML progress bar in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create a `<progress>` element. The CreateElement() method creates an HTML element specified by tagName, in our case the tagName is "progress".
1. Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add  `max`, `value` and other required attributes and their values.
1. Copy C# code for the HTML `<progress>` tag and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With these HTML Generators, all the hard work has already been done for you. All you have to do is copy and paste. Clear, safe and simple!"
---