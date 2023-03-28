---
translation: true
title: HTML Meter Tag Generator - online tool and C# code
template: /templates/_template-generators-child.md
description: HTML Meter Tag Generator creates HTML meter element and C# code for it. Generate code, copy and use it in your own website or C# project.
url: /net/generators/meter/
platformtag: net
generator: HTML Meter Tag Generator
element: HTML meter tag 
tag: meter
---

{{<section banner>}}
---
h1: HTML Meter Tag Generator
h2: Generate HTML and C# code for an HTML meter element and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML <meter> Tag Easily!
---

The HTML `<meter>` tag is used for indicating a scalar measurement in a known range or graphic representation of a fractional number. The tag is also known as a gauge, it can be used when it is necessary to display, for example, the level of disk usage, battery charge, the relevance of a search query result, etc. You need to know the maximum value to use the `<meter>` tag. **Note:** The `<meter>` tag isn’t used to [create a progress bar.](/html/{{lang.url-fragment}}net/generators/progress/) For that purpose, use the `<progress>` tag.

{{<section plugin>}}

{{< app/generator name="meter" >}}

<br>
<h2> Attributes </h2>

The `<meter>` tag accepts the following attributes: *max*, *min*, *value*, *form*, *low*, *optimum*, *high*, etc. 
 - The `max` attribute specifies the maximum value of the range.
 - The `mim` attribute specifies the minimum value of the range. The default value is 0.
 - The `value` attribute specifies the current numeric value. It must be between the `min` and `max` values if they are set. If the `value` is unspecified or malformed, it is 0. If specified but not within the range given by the `min` and `max` attributes, the value equals the nearest end of the range.
 - The `optimum` attribute indicates which value is optimal for the gauge. This can be a desired number, such as a passing mark for a test.
 - The `low` attribute specifies the range that is considered to be a low value.
 - The `high` attribute specifies the range that is considered to be a high value.
<br><br>

<h2> Create HTML Meter Tag in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add a `<meter>` element, see the C# code example below:

{{< /app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Meter Tag in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create a `<meter>` element. The CreateElement() method creates an HTML element specified by tagName, in our case the tagName is "meter".
1. Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add `min`, `max`, `low`, `value` and other required attributes and their values.
1. Copy C# code for the HTML `<meter>` tag and use it in your C# project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "With these HTML Generators, all the hard work has already been done for you. All you have to do is copy and paste. Clear, safe and simple!"
---