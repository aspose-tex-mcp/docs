---
translation: true
title: HTML Video Generator - Online Tool and C# Code
template: /templates/_template-generators-child.md
description: HTML Video Generator creates HTML and C# code for a video element. You can generate code and use it in your own website or C# project.
url: /net/generators/video/
platformtag: net
family: html
generator: HTML Video Generator
element: HTML video
tag: video
---

{{<section banner>}}
---
h1: HTML Video Generator
h2: Generate HTML and C# code for an HTML video element and use it in your own website or C# project.
---

{{<section overview>}}
---
h2: Generate HTML Video Tag Easily!
---

The [video](https://html.spec.whatwg.org/multipage/media.html#the-video-element) HTML element is used to embed a media player that supports video playback in a document. The `<video>` tag can contain one or more `<source>` tags with different video sources. The browser will choose the first source it supports. You can enable or disable various attributes to specify information such as the width and height of the video, whether you want it to autoplay and loop, whether you want to display video controls by default in the browser, and more.


{{<section plugin>}}

{{<app/generator name="video" >}}
<br>
<h2> Attributes </h2>

There are many options available in HTML Video Generator that you can use to generate HTML video tag code and then copy & paste it into your own website. You can enable or disable various options such as video controls, autoplay, looping, preloading, etc.
 - The video `preload` attribute specifies the video file should be loaded when the page loads.
 - The `src` attribute specifies the URL of the video to embed. But this is optional. Instead, you can use the `<source>` element in the video block to specify the video to embed.
 - The `height` and `width` attributes define the height and width of the video display area in CSS pixels.
 - The `autoplay` boolean attribute, if specified, will automatically start playing.
 - The video `controls` attribute specifies whether controls should be displayed or not in your browser. For example, if you disabled video controls and your autoplay setting is enabled, video will play but will not be visible in the browser. 
 - The `loop` boolean attribute, if specified, will automatically seek back to the start upon reaching the end of the video.
 - The `muted` boolean attribute, if specified, indicates whether the video will be initially silenced. Its default value is false. 
<br><br>

<h2> Create HTML Video Element in C#</h2>

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) API supports a set of HTML elements that are defined in HTML Standard, along with rules about how the elements can be nested. You can modify the document by appending new elements, removing, or editing the content of existing nodes. If you want to use the HTML editing features in your product or programmatically add a `<video>` element, see the C# code example below:
{{</app/generator >}}

{{<section steps>}}
---
h2: Steps to Create HTML Video Element in C#
---

1. Use the [CreateElement()](https://reference.aspose.com/html/net/aspose.html.dom/document/createelement/) method of Document class to create a video element. In an HTML document, the Document.CreateElement() method creates the HTML element specified by tagName, in our case the tagName is "video".
2. Use [SetAttribute()](https://reference.aspose.com/html/net/aspose.html.dom/element/setattribute/) method to add `controls` and other required attributes.
3. Create a `<source>` element and set required attributes for it. Use the CreateElement() method with "source" tagName.
4. Use [AppendChild()](https://reference.aspose.com/html/net/aspose.html.dom/node/appendchild/) method to add the `<source>` element into the `<video>` element. 
5. Copy C# code for the HTML video element and use it in your project.

{{<section other-generators>}}
---
title: Other Supported HTML Generators
subTitle: "Use HTML Generators to build highly customizable HTML elements with no coding! Clear, safe and simple!"
---