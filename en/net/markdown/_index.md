---
translation: true
template: /templates/_template-markdown.md
title: C# API to Parse Markdown Files
url: /net/parse-markdown/
description:  Markdown Parser C#. Use Aspose.HTML for .NET API features to parse Markdown content. 
feature: Parse
platformtag: net
tag: parse-markdown
howto: howtoMD
faq: faqMD
---

{{<section banner>}}
---
h1: C# API to Parse Markdown Files 
h2: Use C# library features to create elements, remove, or edit the content of existing nodes of an MD document.
---

{{<section overview>}}
---
h2: Parse Markdown Files Using C#
---

 [Aspose.HTML for .NET](https://products.aspose.com/html/{{lang.url-fragment}}net/) library provides Markdown parsing API for the C# platform. The [Aspose.Html.Toolkit.Markdown.Parser](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax.parser/) namespace contains classes and methods to provide full Markdown parsing and rendering.<br>

You can сreate, edit, save, merge, convert MD  files to other file formats, and add links, lists, code blocks, images and other elements into Markdown files by following the links:


{{<section "code" i18n-exclude>}}

```cs
    // Specify the path to the source MD file
    var input = "C:/temp/input.md";

    // Create a MarkdownParser object
    var parser = new MarkdownParser();

    // Parse the MD document and get a syntax tree
    var markdown = parser.ParseFile(input);
    
    // Create a TreeWalker object and navigate through the syntax tree starting at the first node
    using var iterator = markdown.CreateTreeWalker(markdown.FirstChild);
    while (iterator.NextNode() != null)
    {
        // Check the type of the current node as EmphasisSyntax
        if (iterator.CurrentNode is EmphasisSyntaxNode)
        {
            var node = (EmphasisSyntaxNode)iterator.CurrentNode;
            var n = node.FirstChild;
            while (n != null)
            {
                var next = n.NextSibling;
                // Remove the EmphasisSyntax node
                node.RemoveChild(n);
                n = next;
            }

            // Get a SyntaxFactory to create new elements 
            var syntax = markdown.SyntaxFactory;

            // Add the text to a new node
            node.AppendChild(syntax.Text("new text with"));            

            // Add whitespase
            node.AppendChild(syntax.Whitespace());

            // Create an emphasis object
            var emphasis = syntax.Emphasis(Emphasis.Strong);

            // Add the text into empasis and accumulate a new node
            emphasis.AppendChild(syntax.Text("strong emphasis!"));
            node.AppendChild(emphasis);
            break;
        }
    }

    // Prepare a path for MD file saving 
    string savePath = Path.Combine(OutputDir, "output-edit.md");

    // Save MD file
    markdown.Save(savePath);
        
```

{{<section how-to>}}
---
h2: How to Parse Markdown in C#
title: Parse and Edit Markdown in C#
---

The task of editing Markdown programmatically in C# is modifying elements in the MD document tree. Aspose.HTML for .NET API supports a set of MD elements that are defined in GitHub Flavored Markdown Spec, along with rules about how the elements can be nested. Moreover, the [Aspose.Html.Toolkit.Markdown.Extensions](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.extensions/) namespace contains classes and methods for manipulating the Markdown syntax tree based on specifications that are not part of the GFM specification. Consider simple steps to parse and edit Markdown. Let's parse Markdown and edit text content into it:

{{<section steps>}}
---
h2: Steps to Parse and Edit Markdown in C#
---

Consider simple steps to parse Markdown and edit existing text content:

1. Specify the path to the source MD file and use the [MarkdownParser()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax.parser/markdownparser/markdownparser/#constructor) constructor to initialize a new instance of the MarkdownParser class. 
2. Call the [ParseFile()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax.parser/markdownparser/parsefile/) method to parse Markdown and get a syntax tree.
3. Create a TreeWalker object and navigate through the Markdown syntax tree and remove unnecessary content - EmphasisSyntax node.
4. Use the [SyntaxFactory](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/syntaxfactory/) property to get a syntax factory to create new elements.
4. Create a new text node and add text content to the new emphasis.
5. Use [AppendChild()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxnode/appendchild/) method to add the new node to the syntax tree.
6. Save the edited MD file with [Save()](https://reference.aspose.com/html/net/aspose.html.toolkit.markdown.syntax/markdownsyntaxtree/save/#save_2) method.


{{<section documentation>}}
---
h2: Documentation
---

To learn more about Aspose.HTML API, please visit our [documentation](https://docs.aspose.com/html/net/) guide. You can download the examples from the [GitHub](https://github.com/aspose-html/Aspose.HTML-Documentation) repository. They are open source and can be freely used in your own applications.<br>
 
Markdown is a simple markup language that allows you to format plain text. John Gruber, the author of MD, designed Markdown’s formatting syntax with the goal of making it as readable as possible. Markdown is often used as a format for documentation and readme files since it allows writing in an easy-to-read and easy-to-write style. The [Markdown Syntax](https://docs.aspose.com/html/net/converting-between-formats/markdown-syntax/) documentation article provides information on the main Markdown elements, details and examples of the Markdown syntax. <br>

{{<section system>}}
---
h2: System Requirements
---

Our APIs are supported on all major platforms and Operating Systems. Before executing the code, please ensure that you have the following prerequisites on your system.

 - Microsoft Windows or a compatible OS with .NET Framework, .NET Core, Windows Azure, Mono or Xamarin Platforms.
 - Development environment like Microsoft Visual Studio.
 - Aspose.Html for .NET DLL referenced in your project - Install from NuGet using the Download button above.

{{<section other-aspose>}}
---
h2: Other Supported .NET API Features
---

Using Aspose.HTML, an advanced web scraping and HTML parsing library, you can create, edit, navigate through nodes, extract data, merge and convert HTML, XHTML, MD, EPUB, and MHTML files to PDF, XPS, DOCX, Images and other formats.