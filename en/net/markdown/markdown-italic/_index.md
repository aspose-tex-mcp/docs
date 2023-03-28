---
translation: true
title: Italic in Markdown - C# Code
template: /templates/_template-md-child.md
description: Create Markdown italic text in C#. Use the C# library to create Markdown from scratch and open, parse, or edit MD files.
url: /net/markdown-italic/
platformtag: net
family: html
element: Italic
tag: markdown-italic
---

{{<section banner>}}
---
h1: Italic in Markdown - C# Code
h2: Use the C# library to create Markdown from scratch and open, parse, or edit MD files.
---

{{<section overview>}}
---
h2: How to Create Markdown Italic in C#
---

[Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) library is a stand-alone solution that allows you to parse and manipulate Markdown files without using other software. You can create a Markdown document from scratch, open from a local file and manipulate by inserting new elements, removing, or editing the content of existing nodes. <br>
The [MarkdownSyntaxFactory](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/) class contains methods to create various Markdown elements. For italic text making, we will use the Emphasis() method that takes as a parameter the Emphasis enumeration value `Emphasis.Regular`. You can use italic for single words, multiple words, sentences, paragraphs, and so on, depending on the formatting style of the document.

{{<section "code-add-element" i18n-exclude>}}

```cs
    // Create the MarkdownSyntaxTree
    var markdown = new MarkdownSyntaxTree(new Configuration());

    // Create a Markdown syntax factory
    var mdf = markdown.SyntaxFactory;

    // Create an italic object add text for it
    var italic = mdf.Emphasis(Emphasis.Regular);
    italic.AppendChild(mdf.Text("Italic in Markdown"));

    // Add italic text to the Markdown syntax tree
    markdown.AppendChild(italic);

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "markdown-italic.md");

    // Save MD file
    markdown.Save(savePath);
```

{{<section "code-remove-element" i18n-exclude>}}

```cs
    // Create Markdown syntax tree
    var md = new MarkdownSyntaxTree(new Configuration());

    // Create a Markdown syntax factory
    var mdf = md.SyntaxFactory;

    // Create an emphasis of type Strong (bold)
    var bold = mdf.Emphasis(Emphasis.Strong);

    // Create an italic object add text for it
    var italic = mdf.Emphasis(Emphasis.Regular);
    italic.AppendChild(mdf.Text("Bold Italic Text"));

    // Add italic object to bold element
    bold.AppendChild(italic);

    // Add the bold element to the Markdown syntax tree
    md.AppendChild(bold);

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "italic-bold.md");

    // Save MD file
    md.Save(savePath);
```

{{<section code-text>}}
---
h2: Markdown Italic Text in C#
h3: Markdown Bold Italic 
title: C# code to create italic in Markdown
title1: C# code to add Markdown bold italic text
p: "The following C# code example shows how to create bold italic in Markdown i.e. make text bold and italic at the same time."
---

Using the C# library, you can programmatically edit MD files - change the document structure and content. Let's look at creating a new Markdown document from scratch and adding italic text to it.

{{<section steps>}}
---
h2: Steps to Create Markdown Italic in C#
---

Let' discuss C# example based on italic in Markdown. We consider a few simple steps to create Markdown italic text:

1. Create the MarkdownSyntaxTree using [MarkdownSyntaxTree()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/markdownsyntaxtree/#constructor_1) constructer.
2. Use the [SyntaxFactory](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/syntaxfactory/) property to get the factory for creating the Markdown syntax tree.
3. Create italic object add text for it using [Emphasis()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/emphasis/#emphasis) constructor and the [Text()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/text/#text_2) constructor.
4. Call the [AppendChild()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxnode/appendchild/) method of the MarkdownSyntaxNode class to add italic node into the the document syntax tree.

{{<section documentation>}}
---
h2: Documentation
---

To learn more about Aspose.HTML API, please visit our [documentation](https://docs.aspose.com/html/net/) guide. Markdown is a simple markup language that allows you to format plain text. The [Markdown Syntax](https://docs.aspose.com/html/net/converting-between-formats/markdown-syntax/) documentation article provides information on the main Markdown elements, details and examples of the Markdown syntax. <br>

{{<section other-editors>}}
---
title: Other Supported Markdown Features
---