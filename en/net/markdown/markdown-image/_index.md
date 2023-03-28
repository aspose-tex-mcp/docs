---
translation: true
title: Markdown Image - C# Code
template: /templates/_template-md-child.md
description: Code for adding image in Markdown via C#. Use the C# library to create Markdown from scratch and open, parse, or edit MD files.
url: /net/markdown-image/
platformtag: net
family: html
element: Image
tag: markdown-image
---

{{<section banner>}}
---
h1: Markdown Image in C#
h2: Use the C# library to add Image in Markdown, parse, or edit MD files.
---

{{<section overview>}}
---
h2: Image in Markdown via C#
---

Images can be added to any Markdown file using Markdown Syntax. In this article, you learn about adding images in Markdown, showing images as links, and adding altText to Markdown images using C#. [Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) library is a stand-alone solution that allows you to parse and manipulate Markdown files without using other software. You can create a Markdown document from scratch, open from a local file and manipulate by inserting new elements, removing, or editing the content of existing nodes. <br>
Use the [Aspose.Html.Toolkit.Markdown.Syntax](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/) and [Aspose.Html.Toolkit.Markdown.Parser](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax.parser/) namespaces to provide full Markdown parsing and MD syntax tree management based on the GitHub Flavored Markdown (GFM) specification.<br>

{{<section "code-add-element" i18n-exclude>}}

```cs
    // Create the MarkdownSyntaxTree
    var md = new MarkdownSyntaxTree(new Configuration());

    // Create a Markdown syntax factory
    var mdf = md.SyntaxFactory;

    // Specify an image altText
    var altText = "The San Juan Mountains are beautiful";

    // Specify an image label
    var label = "San Juan Mountains";

    // Specify the path to an image
    var href = "C:/temp/image.png";

    // Create an Image element:
    var image = mdf.InlineImage(altText, href, label);

    // Add the image into MD document
    md.AppendChild(image);            

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "markdown-image.md");

    // Save MD file
    md.Save(savePath);
```

{{<section "code-remove-element" i18n-exclude>}}

```cs
    // Create the MarkdownSyntaxTree
    var markdown = new MarkdownSyntaxTree(new Configuration());

    // Create a link node and add it to Markdown syntax tree        
    var link = markdown.SyntaxFactory.InlineLink("", "https://docs.aspose.com/html/", "");
    markdown.AppendChild(link);

    // Markdown Image Link - create an image node and add it as a link
    var image = markdown.SyntaxFactory.InlineImage("Aspose.HTML for .NET", "https://products.aspose.com/html/images/headers/aspose_html-for-net.svg", "C# HTML Parser - Documentation");
    link.AppendChild(image);
            
    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "markdown-image-link.md");

    // Save MD file
    markdown.Save(savePath);   
```

{{<section code-text>}}
---
h2: How to Add Image in Markdown using C#
h3: Add a Markdown Image as a Link in C#
title: C# code to add an image to MD file
title1: C# code to create a Markdown image as a link
p: "The following C# code example shows how to add an image as a link into MD document:"
---

Using the C# library, you can programmatically edit MD files - change the document structure and content. Let's look at creating a new Markdown document from scratch and adding image to it.

{{<section steps>}}
---
h2: Steps to Add an Image to MD File in C#
---

A few simple steps to create Markdown Image:

1. Create the MarkdownSyntaxTree using [MarkdownSyntaxTree()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/markdownsyntaxtree/#constructor_1) constructer.
2. Use the [SyntaxFactory](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/syntaxfactory/) property to get the factory for creating the Markdown syntax tree.
3. Specify an image altText, label and path to the image and pass them to InlineImage().
4. Create an Image element using [InlineImage()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/inlineimage/#inlineimage_1) constructor in SyntaxFactory.
5. Call the [AppendChild()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxnode/appendchild/) method of the MarkdownSyntaxNode class to add the image into MD syntax tree.

{{<section documentation>}}
---
h2: Documentation
---

To learn more about Aspose.HTML API, please visit our [documentation](https://docs.aspose.com/html/net/) guide. Markdown is a simple markup language that allows you to format plain text. The [Markdown Syntax](https://docs.aspose.com/html/net/converting-between-formats/markdown-syntax/) documentation article provides information on the main Markdown elements, details and examples of the Markdown syntax. <br>

{{<section other-editors>}}
---
title: Other Supported Markdown Features
---