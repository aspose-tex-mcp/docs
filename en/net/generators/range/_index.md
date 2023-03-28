---
translation: true
title: HTML Range Input Generator - Online tool and C# code
template: /templates/_template-generators-child.md
description: Сreate HTML Range Input for your website. Рreview the Range Input, copy and use generated HTML and C# code in your project!
url: /net/generators/range/
platformtag: net
family: html
generator: HTML Range Input Generator
element: HTML range input
tag: range
---

{{<section banner>}}
---
h1: HTML Range Input Generator
h2: Generate HTML and C# code for an HTML Range Input and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML Range Input Easily!
---

An [input](https://html.spec.whatwg.org/multipage/input.html#the-input-element) element with `type="range"` or range slider allows you to specify a numeric value that must be no less than or no more than the given value. The default range is 0 to 100. However, the exact value is not considered important. You can usually find the range slider when manipulating the volume or brightness controls on your computer.

{{<section plugin>}}

{{<app/generator name="range" >}}

<br>
<h2> Attributes </h2>

The range input usually contains a `name`, `value`, `min`, `max`, and `step` attributes.
- To show the range, use the `min` and `max` attributes with the range input type. 
- The `step` attribute is the allowed number of intervals in the range. The default value is 1.
- The `value` attribute contains a starting point of the range. This is the value that the slider is set to by default once the page is loaded. The default value is in most cases halfway between the minimum and maximum number, but you always have the option to change the value to whatever you want.
<br><br>

<h2> Create HTML Range Input in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API works as a headless browser that allows you to create or open existing HTML documents from various sources in order to perform editing operations such as removing, appending and replacing HTML nodes. If you want to use the HTML editing features in your product or programmatically add a range input, see the C# code example below:

{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Range Input in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create [HTMLInputElement.](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/) It creates the HTML element specified by tagName.
1. Set values for the [Type](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/type/) and [Name](https://reference.aspose.com/html/net/aspose.html/htmlinputelement/name/) attributes.
1. Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add `value`, `min`, `max`, and `step` attributes with their values.
1. Copy code for the HTML range input and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With these HTML Generators, all the hard work has already been done for you. All you have to do is copy and paste. Clear, safe and simple!"
---