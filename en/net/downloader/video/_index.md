---
translation: true
title: Video Downloader - Online Tool and C# code
template: /templates/_template-downloaders-child.md
description: Video Downloader extracts videos from the Web online and provides C# code to download videos programmatically.
url: /net/downloader/video/
family: html
platformtag: net
feature: downloader
downloader: Video Downloader
element: videos
tag: video
---

{{<section banner>}}
---
h1: Video Downloader
h2: Download videos from the Web by URL online and get C# code to extract videos programmatically.
---

{{<section overview>}}
---
h2: Download Videos Online
---

The Video Downloader uses [Aspose.HTML for .NET API](/html/{{lang.url-fragment}}net/) to extract videos from the web page. Our product supports video downloading in any format, including MP3, MP4, 3GP, AVI, ASF, MPEG and others, regardless of whether you are using Windows, Mac OS, Linux, Android, or iPhone. Just copy & paste the URL of the video you want to download, click the button and retain the desired video to review it any time!

{{<section plugin>}}

{{< app/downloader/video >}}

<br>

**Note:** We do not support downloading copyrighted videos and using other people's videos for commercial purposes without their express permission. We are not responsible for any copyright infringement that may occur when using this tool. By uploading your files or using our service, you agree with our [Terms of Service](https://about.aspose.app/legal/tos/) and [Privacy Policy.](https://about.aspose.app/legal/privacy-policy/)

<br>
<h2> How to Download Videos in C#</h2>

Using [Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) class library, you can easily create your own application, since our API provides a powerful toolset to analyze and collect information from HTML documents. If you want to use the HTML downloading features in your product or programmatically extract data from the Web, see the C# code example below. You can download videos from website with a few lines of code:
<br><br>

{{< /app/downloader/video >}}

{{<section steps>}}
---
h2: Steps to Download Videos in C#
---

1. Use the [HTMLDocument()](https://reference.aspose.com/html/net/aspose.html/htmldocument/htmldocument/) constructor to initialaze an HTML document from a URL.
2. Use `GetService<INetworkService>()` method to create a network object for resolving valid URLs.
3. Create a CSS Selector that extracts all `<video>` elements in the document. Use the [QuerySelectorAll(selector)](https://reference.aspose.com/html/net/aspose.html.dom/document/queryselectorall/) method that returns a list of all elements in the document, which match the selector.
4. Select videos with the `Src` attribute which is present and not empty.
5. Create a downloading request, get a response and save a video file from a stream for each videos' array item.
6. Copy C# code for video downloading and use it in your project.

{{<section other-downloaders>}}
---
title: Other Supported Web Downloaders
subTitle: "Use Web Downloaders to extract data from the Web! Clear, safe and simple!"
---