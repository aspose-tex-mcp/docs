---
translation: true
title: Markdown Text, Markdown Blockquote  - C# Code
template: /templates/_template-md-child.md
description: Create Markdown text or Markdown blockquote in C#. Use the C# library to create Markdown from scratch and open, parse, or edit MD files.
url: /net/markdown-text/
platformtag: net
family: html
element: Text
tag: markdown-text
---

{{<section banner>}}
---
h1: Markdown Text and Markdown Blockquote in C#
h2: Use the C# library to create Markdown from scratch and open, parse, or edit MD files.
---

{{<section overview>}}
---
h2: How to Create Markdown Text in C#
---

Like HTML, Markdown is a markup language. Unlike HTML, Markdown aims to be as readable as possible. You can apply bold, italics, quotation marks, and strikethrough to the text. They can also be used in combination to use multiple styles at the same time. [Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) library is a stand-alone solution that allows you to parse and manipulate Markdown files without using other software. You can create a Markdown document from scratch, open it from a local file and manipulate it by inserting new elements, and removing, or editing the content of existing nodes.<br>

The [MarkdownSyntaxFactory](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/) class contains methods to create various Markdown elements. For headers creation, you may use the [AtxHeading()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/atxheading/#atxheading_1) method that creates Atx Heading Syntax Node with text content. You can use the [Emphasis()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/emphasis/#emphasis) method that takes as a parameter the Emphasis enumeration values to make text bold or italic, and more. Here we look at some C# examples of how to work with Markdown text.

{{<section "code-add-element" i18n-exclude>}}

```cs
// Create the MarkdownSyntaxTree
    var md = new MarkdownSyntaxTree(new Configuration());

    // Use the SyntaxFactory property to get the factory for creating the Markdown syntax tree
    var mdf = md.SyntaxFactory;

    var header = mdf.AtxHeading("How to create Markdown Text in C#?", 2);    

    // Create and add newLineTrivia element for an empty line after header 
    var newLineTrivia = mdf.NewLineTrivia();
    header.GetTrailingTrivia().Add(newLineTrivia);

    // Add the  headers to the Markdown syntax tree
     md.AppendChild(header);

    // Create an empty paragraph
    var paragraph = mdf.Paragraph();

    // Add texts to the paragraph
    paragraph.AppendChild(mdf.Text("First, add an Aspose.HTML for .NET library reference to your C# project."));

    // Add a space after the first sentence in the paragraph through a special WhiteSpace node
    paragraph.AppendChild(mdf.Whitespace());

    paragraph.AppendChild(mdf.Text("Then create the Markdown Syntax Tree and use the SyntaxFactory property to get a syntax factory to create new elements."));

    // Add the filled paragraph into MD document
    md.AppendChild(paragraph);

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "markdown-text.md");

    // Save MD file
    md.Save(savePath);    
```

{{<section "code-remove-element" i18n-exclude>}}

```cs
// Create the MarkdownSyntaxTree
    var markdown = new MarkdownSyntaxTree(new Configuration());

    // Create a Markdown syntax factory
    var mdf = markdown.SyntaxFactory;

    // Create a blockQuote object
    var blockQuote = mdf.BlockQuote();

    // Add a leading trivia token blockquote
    blockQuote.GetLinesLeadingTrivia().Add(mdf.Token(SourceText.From("> ")));

    // Create a paragraph with text content 
    var paragraph = mdf.Paragraph();
    paragraph.AppendChild(mdf.Text("For blockquote creation, you should put a sign `>` before the first line of a hard-wrapped paragraph.."));

    // Add paragraph into blockQuote
    blockQuote.AppendChild(paragraph);

    // Add blockQuote object into MD document
    markdown.AppendChild(blockQuote);

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "markdown-blockquote.md");

    // Save MD file
    markdown.Save(savePath);    
```

{{<section code-text>}}
---
h2: Markdown Text in C#
h3: Create Markdown Blockquote in C# 
title: C# code to create Markdown text
title1: C# code to add Markdown blockquote
p: "The following C# code example shows how to create Markdown blockquote."
---

Using the C# library, you can programmatically edit MD files - change the document structure and content. Let's look at creating a new Markdown document from scratch and adding texts to it.

{{<section steps>}}
---
h2: Steps to Create Markdown Text in C#
---

Let's consider a few simple steps to create Markdown texts:

1. Create the MarkdownSyntaxTree using [MarkdownSyntaxTree()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/markdownsyntaxtree/#constructor_1) constructer.
2. Use the [SyntaxFactory](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/syntaxfactory/) property to get the factory for creating the Markdown syntax tree.
3. Create a new header using [AtxHeading(string, int)](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/atxheading/#atxheading_2) constructor of the [MarkdownSyntaxFactory](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/) class. It creates AtxHeadingSyntaxNode with text content and heading level.
4. Create a newLineTrivia element for an empty line after header. Use the [NewLineTrivia()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/newlinetrivia/) constructor.
5. Call the Add() method of the SyntaxNodeCollection class to add the newLineTrivia node into header element.
6. After all header nodes have been collected into one element, add it to the document syntax tree.
7. Create a new empty paragraph node using [Paragraph()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/paragraph/) constructor in SyntaxFactory.
8. Use the [Text()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/text/#text_2) constructor to create text nodes for paragraph.
9. Use the [Whitespace()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxfactory/whitespace/#whitespace_2) constructor to create space between text nodes in paragraph.
10. Call the [AppendChild()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxnode/appendchild/) method of the MarkdownSyntaxNode class to add text nodes and whitespaces into paragraph.
11. After all paragraph nodes have been collected into one element, add it to the document syntax tree. Call the [AppendChild()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxnode/appendchild/) method of the MarkdownSyntaxNode class.

{{<section documentation>}}
---
h2: Documentation
---

To learn more about Aspose.HTML API, please visit our [documentation](https://docs.aspose.com/html/net/) guide. Markdown is a simple markup language that allows you to format plain text. The [Markdown Syntax](https://docs.aspose.com/html/net/converting-between-formats/markdown-syntax/) documentation article provides information on the main Markdown elements, details and examples of the Markdown syntax. <br>

{{<section other-editors>}}
---
title: Other Supported Markdown Features
---