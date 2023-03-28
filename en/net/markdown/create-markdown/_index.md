---
translation: true
title: Create Markdown - C# Code
template: /templates/_template-md-child.md
description: Code for creating Markdown files in C#. Use the C# library to create Markdown from scratch and open, parse, or edit MD files.
url: /net/create-markdown/
family: html
feature: Create
platformtag: net
tag: create-markdown
howto: howtoMD
faq: faqMD
---

{{<section banner>}}
---
h1: Create Markdown in C#
h2: Use the C# library to create Markdown from scratch and open, parse, or edit MD files.
---

{{<section overview>}}
---
h2: How to Create Markdown in C#
---

Markdown is a simple markup language that allows you to format plain text. [Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) library is a stand-alone solution that allows you to parse and manipulate Markdown files without using other software. You can create a Markdown document from scratch, open from a local file and manipulate by inserting new elements, removing, or editing the content of existing nodes. <br>
The [Aspose.Html.Toolkit.Markdown.Syntax](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/) namespace contains classes and methods to manipulate a Markdown syntax tree based on GitHub Flavored Markdown (GFM) Specification.<br>
The [Aspose.Html.Toolkit.Markdown.Parser](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax.parser/) namespace contains classes and methods to provide full Markdown parsing and rendering.<br>
The [Aspose.Html.Toolkit.Markdown.Extensions](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.extensions/) namespace contains classes and methods for manipulating the Markdown syntax tree based on specifications that are not part of the GFM specification. <br><br>

{{<section "code-add-element" i18n-exclude>}}

```cs
    // Create the MarkdownSyntaxTree
    var md = new MarkdownSyntaxTree(new Configuration());

    // Use the SyntaxFactory property to get the factory for creating the Markdown syntax tree
    var mdf = md.SyntaxFactory;

    var heading2 = mdf.AtxHeading("How to create Markdown from scratch in C#?", 2);

    // Add the  headers to the Markdown syntax tree
    md.AppendChild(heading2);

    // Create and add newLineTrivia element for an empty line after heading1 
    var newLineTrivia = mdf.NewLineTrivia();
    heading2.GetTrailingTrivia().Add(newLineTrivia);

    // Create an empty paragraph
    var paragraph = mdf.Paragraph();

    // Add texts to the paragraph
    paragraph.AppendChild(mdf.Text("First, add an Aspose.HTML for .NET library reference to your C# project."));

    // Add a space after the first sentence in the paragraph through a special WhiteSpace node
    paragraph.AppendChild(mdf.Whitespace());

    paragraph.AppendChild(mdf.Text("Create the MarkdownSyntaxTree. Then use the SyntaxFactory property to get a syntax factory to create new elements."));

    // Add the filled paragraph into MD document
    md.AppendChild(paragraph);

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "document.md");

    // Save MD file
    md.Save(savePath);
```

{{<section "code-remove-element" i18n-exclude>}}

```cs
    // Specify the path to the source MD file
    var input = "C:/temp/input.md";

    // Create a MarkdownParser object
    var parser = new MarkdownParser();

    // Parse the MD document and get a syntax tree
    var markdown = parser.ParseFile(input);

    // Work with Markdown document

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "output.md");

    // Save MD file
    markdown.Save(savePath);
```

{{<section code-text>}}
---
h2: How to Create Markdown from Scratch in C#?
h3: How to Open MD File in C#
title: C# code to create MD file
title1: C# code to open MD file
p: "The following C# code example shows how to open an existing MD document:"
---

Using the C# library, you can programmatically create MD files. Let's look at how to create Markdown from scratch.

{{<section steps>}}
---
h2: Steps to Create Markdown in C#
---

Let's take a look at the simple steps to create Markdown from scratch. The first two steps are mandatory for the creation of Markdown. The next steps are adding new elements and saving the document:

1. Create the MarkdownSyntaxTree using [MarkdownSyntaxTree()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/markdownsyntaxtree/#constructor_1) constructer.
2. Use the [SyntaxFactory](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/syntaxfactory/) property to get the factory for creating the Markdown syntax tree.
3. Create and add new elements to a Markdown file.
4. Save the created MD file using [Save()](https://reference.aspose.com/html/net/aspose.html/htmldocument/save/#save_10) method.

{{<section documentation>}}
---
h2: Documentation
---

To learn more about Aspose.HTML API, please visit our [documentation](https://docs.aspose.com/html/net/) guide. The [Markdown Syntax](https://docs.aspose.com/html/net/converting-between-formats/markdown-syntax/) documentation article provides information on the main Markdown elements, details and examples of the Markdown syntax. <br>

MD files use Markdown language that was proposed and developed by John Gruber. John Gruber designed Markdown’s formatting syntax with the goal of making it as readable as possible. Markdown is often used as a format for documentation and readme files since it allows writing in an easy-to-read and easy-to-write style. In addition, MD files can be converted to HTML, PDF, XPS or images to take advantage of other formats for specific tasks.

{{<section other-editors>}}
---
title: Other Supported Markdown Features
---