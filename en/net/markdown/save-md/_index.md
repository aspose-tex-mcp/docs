---
translation: true
title: Save MD - C# Markdown Parser 
template: /templates/_template-md-child.md
description: Code for saving Markdown files in C#. Use the C# library to parse, edit and save Markdown.
url: /net/save-md/
family: html
feature: Save
platformtag: net
tag: save-md
howto: howtoMD
faq: faqMD
---

{{<section banner>}}
---
h1: Save MD in C#
h2: Use the C# library to to parse, edit and save Markdown files.
---

{{<section overview>}}
---
h2: How to Save MD in C#
---

Markdown is a simple markup language that allows you to format plain text. [Aspose.HTML for .NET](/html/{{lang.url-fragment}}net/) library is a stand-alone solution that allows you to parse and manipulate Markdown files without using other software. You can create from scratch or open a Markdown document from a local file, edit the content of existing nodes and save or convert the edited document to the required format.<br>
The [Aspose.Html.Toolkit.Markdown.Syntax](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/) namespace contains classes and methods to manipulate a Markdown syntax tree based on GitHub Flavored Markdown (GFM) Specification.<br>
The [Aspose.Html.Toolkit.Markdown.Parser](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax.parser/) namespace contains classes and methods to provide full Markdown parsing and rendering.<br>
The [Aspose.Html.Toolkit.Markdown.Extensions](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.extensions/) namespace contains classes and methods for manipulating the Markdown syntax tree based on specifications that are not part of the GFM specification. <br><br>

{{<section "code-remove-element" i18n-exclude>}}

```cs
    // Create the MarkdownSyntaxTree
    var md = new MarkdownSyntaxTree(new Configuration());

    // Create a Markdown syntax factory
    var mdf = md.SyntaxFactory;
            
    // Create an empty paragraph
    var paragraph = mdf.Paragraph();

    // Add texts to the paragraph
    paragraph.AppendChild(mdf.Text("Markdown is a simple markup language that allows you to format plain text."));

    // Add a space after the first sentence in the paragraph through a special WhiteSpace node
    paragraph.AppendChild(mdf.Whitespace());

    paragraph.AppendChild(mdf.Text("MD files use Markdown language that was proposed and developed by John Gruber."));

    // Add the filled paragraph into MD document
    md.AppendChild(paragraph);            

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "save.md");

    // Save MD file
    md.Save(savePath);
```

{{<section "code-add-element" i18n-exclude>}}

```cs
    // Specify the path to the source MD file
    var input = "C:/temp/document.md";

    // Create a MarkdownParser object
    var parser = new MarkdownParser();

    // Parse the MD document and get a syntax tree
    var markdown = parser.ParseFile(input);

    // Work with the Markdown document

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "output.md");

    // Save MD file
    markdown.Save(savePath);
```

{{<section code-text>}}
---
h2: How to Save MD File in C#?
h3: Create from Scratch and Save MD in C#
title: C# code to save MD
title1: C# code to save MD file
p: "Using the C# library, you can programmatically create, edit and save MD files. Let's see how to save MD file created from scratch."
---

The following C# code example shows how to save an MD document. The last two steps are required to save Markdown - you can prepare a path to save the MD file and use the Save() method.

{{<section steps>}}
---
h2: Steps to Save MD in C#
---

Let's take a look at the simple steps to save MD file after editing:

1. Specify a path to source MD file and use the [MarkdownParser()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax.parser/markdownparser/markdownparser/#constructor) constructor to initialize a new instance of the MarkdownParser class. 
2. Call the [ParseFile()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax.parser/markdownparser/parsefile/) method to parse Markdown and get a syntax tree.
3. Use the [SyntaxFactory](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/syntaxfactory/) property to get a syntax factory to create new elements.
4. Work with the document.
5. Prepare the path to save MD file.
6. Save the created MD file using [Save()](https://reference.aspose.com/html/net/aspose.html/htmldocument/save/#save_10) method.

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