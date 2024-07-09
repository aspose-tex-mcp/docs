---
title: Frequently Asked Questions | Aspose.TeX for С++
linktitle: FAQ
type: docs
weight: 80
url: /cpp/faq/
description:  Get answers to all the most frequent questions about Aspose.TeX for C++, which is a comprehensive API for typesetting and manipulation TeX and LaTeX.
submenu: menu-tex-for-cpp
---

<br><br>

**Q: What is the primary functionality of Aspose.TeX API Solution for C++?**

**A:** The primary functionality of Aspose.TeX is the programmatic creation, manipulation, and conversion of TeX and LaTeX documents. It lets load existing TeX/LaTeX files, modify their content, and perform actions like adding or removing elements.
<br><br>

**Q: What formats does Aspose.TeX for C++ support?**

**A:** Aspose.TeX supports TeX and LaTeX as input and  XPS, PDF, PNG, JPEG, TIFF, SVG, and BMP formats as output.
<br><br>

**Q: How to convert TeX?**

**A:** It is very simple. You need to take only a few steps! 

1. Create an object of the TeXOptions class.
2. Specify the output by calling the set_OutputWorkingDirectory() method.
3. Initialize save options for the output format, and instantiate the TeXJob class.
4. Run the conversion.

For more examples, please visit [Convertion](/tex/cpp/conversion/) guides.
<br><br>

**Q: Can I create a custom format using Aspose.TeX for C++?**

**A:** Yes, the Library has such functionality. It is briefly described in the [Other TeX conversion output formats ] (/tex/cpp/other-tex-formats/#creating-a-custom-format) article.
<br><br>

**Q: What packages are embedded into Aspose.TeX API Solution?**

**A:** By now there are [Aspose.TeX embedded LaTeX packages](/tex/net/embedded-packages/) included: 
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

**A:** It is really simple. Take a look at the example below! 

```C++
    // Create conversion options for the Object TeX/Object LaTeX format upon the Object TeX engine extension.
    System::SharedPtr<TeXOptions> options = TeXOptions::ConsoleAppOptions(TeXConfig::ObjectTeX()); // TeXConfig::get_ObjectLaTeX()
    // Specify a file system working directory for the output.
    options->set_OutputWorkingDirectory(System::MakeObject<OutputFileSystemDirectory>(RunExamples::OutputDirectory));
    // Run the job.
    System::MakeObject<Aspose::TeX::TeXJob>(System::IO::Path::Combine(RunExamples::InputDirectory, u"hello-world"),
        System::MakeObject<XpsDevice>(), options)->Run();
```
<br><br>

**Q: How to install Aspose.TeX for C++ Package from Nuget?**

**A:** Open the NuGet package manager, search for Aspose.TeX.Cpp, and install it. You may also use the following command from the Package Manager Console:

```C++
    PM> Install-Package Aspose.TeX.Cpp
```

**Q: Can I render LaTeX formulas using Aspose.TeX for C++?**

**A:** Yes, Aspose.TeX math rendering library lets you create an SVG or PNG image with a math formula easily. 
1. Create rendering options.
2. Specify the background color, preamble, resolution, foreground color, and scaling factor.
3. Specify the output stream for the log file.
4. Create a file stream to save the output image.
5. Create an object of the *(file format)MathRenderer* class and run rendering the formula by calling the *Render()* method. 

For more examples, please visit [LaTeX math formulas rendering](/tex/cpp/latex-math-formula-rendering/) guides.
<br><br>

**Q: Where can I learn more about TeX?**

**A:** There is a [knowledge base for TeX and LaTeX](/tex/net/introduction-to-tex/) so you can understand the subject deeper. Also, take a look at the [General articles on LaTeX](/tex/java/general-articles-latex/) that will teach you rules that every document author must follow. It also defines the structure of the source file, which is essentially a typesetting program.
<br><br>

**Q: Can Aspose.TeX for C++ work with archives, using them as output without previously unpacking the files or saving the result right to the archive?**

**A:** Yes, just open a stream containing a ZIP archive that will serve as the input working directory. You can optionally specify a subdirectory in the archive. Otherwise, the file will be searched throughout the archive. For specifying ZIP archive working directories for input and output use the InputZipDirectory and OutputZipDirectory classes.
<br><br>

**Q: Can I try the Solution before purchasing it?**

**A:** Yes, you can easily download Aspose.TeX for C++ products for evaluation purposes. The evaluation version of Aspose.TeX (without a license specified) provides full product functionality except for some [evaluation limitations](/tex/cpp/licensing/#evaluation-version-limitations).

If you want to try Aspose.TeX out without evaluation limitations, request a 30-day [temporary license](https://purchase.aspose.com/temporary-license/).
<br><br>

**Q: Where can I get help if I have any issues with the Library?**

**A:** Check the [Aspose Forum](https://forum.aspose.com/c/tex/47) for answers or add a new topic with your issue if you did not find the one suitable for your problem. 
<br><br>

**Q: How can I apply for a license for Aspose.TeX for C++?**

**A:** Use the `License::SetLicense` method to license the component. The easiest way to [set a license](/tex/cpp/licensing/) is to put the license file in the same folder as the Aspose.TeX.dll and specify the filename, without a path.
<br><br>

**Q: Can I see the functionality of this API Solution implemented in web applications?**

**A:** Check our [web solutions](https://products.aspose.app/tex/applications) to convert, view, merge, and edit TeX and LaTeX files, and create mathematical equations and many more.
<br><br>


