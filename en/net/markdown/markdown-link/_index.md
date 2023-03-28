---
translation: true
title: Markdown Link - C# Code
template: /templates/_template-md-child.md
description: Code for creating Markdown link in C#. Use the C# library to create Markdown from scratch and open, parse, or edit MD files.
url: /net/markdown-link/
platformtag: net
family: html
element: Link
tag: markdown-link
---

{{<section banner>}}
---
h1: Markdown Link in C#
h2: Use the C# library to create Markdown from scratch and open, parse, or edit MD files.
---

{{<section overview>}}
---
h2: How to Create Markdown Link in C#
---

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) library is a stand-alone solution that allows you to parse and manipulate Markdown files without using other software. You can create a Markdown document from scratch, open from a local file and manipulate by inserting new elements, removing, or editing the content of existing nodes. <br>
Use the [Aspose.Html.Toolkit.Markdown.Syntax](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/) and [Aspose.Html.Toolkit.Markdown.Parser](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax.parser/) namespaces to provide full Markdown parsing and MD syntax tree management based on the GitHub Flavored Markdown (GFM) specification.<br>

{{<section "code-add-element" i18n-exclude>}}

```cs
    // Create the MarkdownSyntaxTree
    var md = new MarkdownSyntaxTree(new Configuration());

    // Create a Markdown syntax tree
    var mdf = md.SyntaxFactory;

    var link = mdf.InlineLink("C# HTML Parser", "https://products.aspose.com/html/net/", "Aspose.HTML  for .NET\r\nC# API to Parse HTML Files");

    // Add link into MD document
    md.AppendChild(link);

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "markdown-link.md");

    // Save MD file
    md.Save(savePath);
```

{{<section "code-remove-element" i18n-exclude>}}

```cs
// Create the MarkdownSyntaxTree
    var markdown = new MarkdownSyntaxTree(new Configuration());

    // Create a link node and add it to Markdown syntax tree        
    var link = markdown.SyntaxFactory.InlineLink("", "https://products.aspose.com/html/", "");
    markdown.AppendChild(link);

    // Create an image node and add it as a link
    var image = markdown.SyntaxFactory.InlineImage("Aspose.HTML High Code APIs", "https://products.aspose.com/html/images/headers/aspose_html-brand.svg", "Hyper Text Markup Language Solution");
    link.AppendChild(image);
            
    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "markdown-image-link.md");

    // Save MD file
    markdown.Save(savePath);      
```

{{<section code-text>}}
---
h2: How to Add Markdown Link in C#
h3: Add Image as a Markdown Link in C#
title: C# code to add MD link
title1: C# code to add Markdown Image link
p: "The following C# example shows how to add an image as a link into MD document"
---

Using the C# library, you can programmatically edit MD files - change the document structure and content. Let's look at creating a new Markdown document from scratch and adding a link element to it.

{{<section steps>}}
---
h2: Steps to Create Markdown Link in C#
---

Let's consider a few simple steps to create Markdown link:

1. Create the MarkdownSyntaxTree using [MarkdownSyntaxTree()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/markdownsyntaxtree/#constructor_1) constructer.
2. Use the [SyntaxFactory](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/syntaxfactory/) property to get the factory for creating the Markdown syntax tree.
3. Create a new link node. Use the [InlineLink()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/inlinelink/#inlinelink_1) constructor in SyntaxFactory and pass text, destination, and title to it as a parameters.
4. Call the [AppendChild()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxnode/appendchild/) method of the MarkdownSyntaxNode class to add link node into the Markdown syntax tree.

{{<section documentation>}}
---
h2: Documentation
---

To learn more about Aspose.HTML API, please visit our [documentation](https://docs.aspose.com/html/net/) guide. Markdown is a simple markup language that allows you to format plain text. The [Markdown Syntax](https://docs.aspose.com/html/net/converting-between-formats/markdown-syntax/) documentation article provides information on the main Markdown elements, details and examples of the Markdown syntax. <br>

{{<section other-editors>}}
---
title: Other Supported Markdown Features
---