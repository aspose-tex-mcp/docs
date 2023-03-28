---
translation: true
title: Web Scraper - Online Tool and C# code
template: /templates/_template-web-scraper.md
description: Use Web Scraper to extract data from any public website using C# or online. Make web data extraction easy and accessible!
url: /net/web-scraper/
family: html
platformtag: net
feature: scraper
---

{{<section banner>}}
---
h1: Web Scraper - Online Tool and C# code
h2: Use Web Scraper to extract data from any public website. Make web data scraping easy and accessible!
---

{{<section overview>}}
---
h2: Online Web Scraper
---

Web Scraper is a free and easy-to-use tool that can navigate a website and extract data you need. We made web scraping quick and effective. Data extraction runs in your browser and does not require installing anything on your computer. Start data scraping now! 

 - Enter a site URL to scrape data.
 - Choose a data selector from the drop-down menu - CSS Query or XPath.
 - Enter an expression, for example `img` for CSS Query or `//img` for XPath. In this case, the Web Scrater selects all `<img>` elements no matter where they are in the document. We covered in detail how to use XPath expressions in the [How to use XPath](https://docs.aspose.com/html/net/how-to-articles/how-to-use-xpath/) documentation article.
 - Push the Find button, get the result and copy it to the clipboard.

{{<section plugin>}}

{{< app/web-scraper >}}

<br>
<h2> How to Extract Data from the Web in C#</h2>

Using Aspose.HTML for the .NET API, you can easily create your own application because our API provides a powerful set of tools for parsing and gathering information from HTML documents. An important part of every web scraper is the data selectors that are used to find the data you want to extract from the HTML file - usually XPath selectors, CSS selectors, or both.

In the following example, we use the QuerySelectorAll() method for navigation through an HTML document and search the needed elements. This method takes as a parameter the query selector and returns a NodeList of all the elements, which match the specified selector.
<br><br>

{{< /app/web-scraper >}}

{{<section steps>}}
---
h2: Steps to Extract Data using C#
---

1. Use the [HTMLDocument()](https://reference.aspose.com/html/net/aspose.html/htmldocument/htmldocument/) constructor to initialaze an HTML document from a URL.
2. Use the [QuerySelectorAll(selector)](https://reference.aspose.com/html/net/aspose.html.dom/document/queryselectorall/) method that returns a list of all elements in the document, which match the selector.
3. Iterate through the list of elements and print the content of the element.
4. Copy C# code for the web scraper and use it in your project.

**Note:** Using the Web Scraper require you to accept our [Terms of Service](https://about.aspose.app/legal/tos/) and [Privacy Policy.](https://about.aspose.app/legal/privacy-policy/) Web scraping becomes illegal when non-publicly available data is extracted.

{{<section documentation>}}
---
h2: Web Scraping in Documentation
---

[Web Scraping](https://docs.aspose.com/html/net/web-scraping/) section describes how to inspect, capture and extract data from the web pages automatically using Aspose.HTML for .NET. In the [How-to Articles](https://docs.aspose.com/html/net/how-to-articles/) chapter you find answers to popular questions about web scraping. In addition, the articles contain C# examples that provide the necessary information about using the Aspose.HTML class library to solve specific tasks.

 - [HTML Navigation](https://docs.aspose.com/html/net/web-scraping/html-navigation/) - In this article, you learn how to perform a detailed inspection of the HTML document and its elements using the API, about custom filters usage for iterating over the document elements, and how to navigate over the document by using CSS Selector or XPath.
 - [How to use CSS Selector - QuerySelector() and QuerySelectorAll()](https://docs.aspose.com/html/net/how-to-articles/how-to-use-css-selector/)- In this article, discover how to effectively apply selectors to select the elements.
 - [How to use XPath Query in HTML - Evaluate() method](https://docs.aspose.com/html/net/how-to-articles/how-to-use-xpath/) - This article introduces how to navigate through an HTML document and select nodes by various criteria. You will learn with C# examples, how to select all Nodes with specified Name using XPath query.
 - [How To Use XPath To Select XML Nodes](https://docs.aspose.com/html/net/how-to-articles/how-to-use-xpath-to-select-xml-nodes/) - You will learn how to navigate through an XML document and select nodes using XPath. The article considers a С# example of selecting the required information from an XML file using XPath queries.

{{<section other-aspose>}}
---
title: Other Supported Aspose.HTML for .NET API Features
subTitle: "Use the Aspose.HTML for .NET library to convert, merge, edit HTML, EPUB, MHTML, XHTML, MD documents, extract data from the web, and more!"
---