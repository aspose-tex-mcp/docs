---
translation: true
template: /templates/_template-net.md
title: Frequently Asked Questions | Aspose.TeX for .NET
linktitle: FAQ
weight: 80
url: /net/faq/
description:  Get answers to all the most frequent questions about Aspose.TeX for .NET, which is a comprehensive API for typesetting and manipulating TeX and LaTeX.
lastmod: "2026-04-22"
---

{{<section overview>}}

<br><br>

**Q: What is the primary functionality of Aspose.TeX API Solution?**

**A:** Aspose.TeX is a comprehensive API solution for typesetting TeX and Latex that lets you create LaTeX equations, and create and convert TeX files. It is an efficient TeX document management and formula creation.
<br><br>

**Q: What formats does Aspose.TeX support?**

**A:** Aspose.TeX supports TeX and LaTeX as input and  XPS, PDF, PNG, JPEG, TIFF, SVG, and BMP formats as output.
<br><br>

**Q: How to convert TeX?**

**A:** It is very simple. You need to take only a few steps! 

1. Initiate the [TeXOptions](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) class.
2. Specify the file system working directory for the output by setting the [OutputWorkingDirectory](https://reference.aspose.com/tex/net/aspose.tex/texoptions/outputworkingdirectory/) property.
3. Initialize save options for the output format using the (file format)SaveOptions class.
4. Convert TeX using the [Run()](https://reference.aspose.com/tex/net/aspose.tex/texjob/run/) method.

For more examples, please visit [Conversion](/tex/{{lang.url-fragment}}net/conversion/) guides.
<br><br>

**Q: Which external LaTeX packages are supported by Aspose.TeX?**

**A:** You can use most of the packages but there are a few [restrictions](/tex/{{lang.url-fragment}}net/external-latex-packages/#restrictions) here.
<br><br>

**Q: What packages are embedded into Aspose.TeX API Solution?**

**A:** According to the list of [Aspose.TeX embedded LaTeX packages](/tex/{{lang.url-fragment}}net/embedded-packages/) they are: 

- eurosym
- geometry
- graphics
- hyperref
- multirow
- pgf
- pict2e
- setspace
- latex-tools bundle: afterpage, array, bm, calc, dcolumn, delarray, enumerate, fileerr, fontsmpl, ftnright, hhline, indentfirst, layout, longtable, multicol, rawfonts, showkeys, somedefs, tabularx, theorem, trace, varioref, verbatim, xr, and xspace.
- url
- wasysym
- xcolor 
<br><br>

**Q: How to typeset TeX files?**

**A:** It is very simple. You need to take only a few steps! 

1. Create conversion settings tailored to either the Object TeX or Object LaTeX format.
2. Designate a directory within the file system for the resulting output.
3. Instantiate the TeXJob class and initiate the typesetting operation by invoking the *TeXJob.Run*() method.
<br><br>

**Q: How to install Aspose.TeX Package from Nuget?**

**A:** Open the NuGet package manager, search for Aspose.TeX, and install it. You may also use the following command from the Package Manager Console:

{{< highlight csharp>}}
    PM> Install-Package Aspose.TeX
{{< /highlight >}}

**Q: How to render LaTeX formulas using Aspose.TeX?**

**A:** Aspose.TeX math rendering library lets you create an SVG or PNG image containing a math formula taking just a few steps:

1. Create an object of the *(file format)MathRendererOptions* class.
2. Specify the background color using the BackgroundColor property of the options if needed.
3. Set up a memory stream to capture the log output generated during the rendering process using the *LogStream* property.
4. Create a file stream to save the output image.
5. Create an object of the *(file format)MathRenderer* class and run rendering the formula by calling the *Render()* method. 

For more examples, please visit [LaTeX math formulas rendering](/tex/{{lang.url-fragment}}net/latex-math-formula-rendering/) guides.
<br><br>

**Q: Where can I learn more about TeX?**

**A:** There is a [knowledge base for TeX and LaTeX](/tex/{{lang.url-fragment}}net/introduction-to-tex/) so you can understand the subject deeper. Also take a look at the [General articles on LaTeX](/tex/{{lang.url-fragment}}java/general-articles-latex/) that will teach you rules that every document author must follow. It also defines the structure of the source file, which is essentially a typesetting program.
<br><br>

**Q: What ways of reading input and writing output are supported by Aspose.TeX?**

**A:** In this API Solution you can load TeX files and write output from/to:

- File system directory
- ZIP archive
- Main TeX file can also be passed through a stream
<br><br>

**Q: Can I try the Solution before purchasing it?**

**A:** Yes, you can easily download Aspose.TeX for .NET product for evaluation purposes. Evaluation version of Aspose.TeX (without a license specified) provides full product functionality except for some [evaluation limitations](/tex/{{lang.url-fragment}}net/licensing/#evaluation-version-limitations).

If you want to try Aspose.TeX out without evaluation limitations, request a 30-day [temporary license](https://purchase.aspose.com/temporary-license/).
<br><br>

**Q: Where can I get help if there are any issues with the Solution faced?**

**A:** Check the [Aspose Forum](https://forum.aspose.com/c/tex/47) for answers or add a new topic with your issue if you did not find the one suitable for your problem. 
<br><br>

**Q: How does Aspose.TeX API Solution ensure cross-platform compatibility?**

**A:** Aspose.TeX API Solution is designed to be platform-independent, allowing developers to build functionalities that work consistently across different operating systems and environments. 
<br><br>

**Q: Where can I see the functionality of this API Solution implemented in web applications?**

**A:** Check our [web solutions](https://products.aspose.app/tex/applications) to convert, view, merge, and edit TeX and LaTeX files and create mathematical equations. They are the brightest examples you can use the API for developing your own products.

Check also [Aspose.TeX AI Agents**](https://products.aspose.ai/tex/)  - a combination of our experience in developing API for TeX and LaTeX files processing API and Artificial Intelligence.
<br><br>


