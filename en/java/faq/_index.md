---
title: Frequently Asked Questions | Aspose.TeX for С++
linktitle: FAQ
type: docs
weight: 80
url: /java/faq/
description:  Get answers to all the most frequent questions about Aspose.TeX for Java, which is a comprehensive API for typesetting and manipulation TeX and LaTeX.
submenu: menu-tex-for-java
---

<br><br>

**Q: What can I use Aspose.TeX API Solution for Java for?**

**A:** Aspose.TeX for Java is your one-stop shop for managing and manipulating TeX files. It empowers you to:
- Effortlessly convert TeX and LaTeX files.
- Aspose.TeX offers multiple ways to feed it TeX code and retrieve the generated output in your desired format.
- Create custom TeX formats.
- Create math equations and formulas.
<br><br>

**Q: What formats does Aspose.TeX for Java support?**

**A:** Aspose.TeX supports TeX and LaTeX as input and  XPS, PDF, PNG, JPEG, TIFF, SVG, and BMP formats as output.
<br><br>

**Q: How to convert TeX within Java?**

**A:** It is pretty simple. Let's describe it on the TeX to PDF Conversion example! 

```Java
// Create conversion options for Object LaTeX format on Object TeX engine extension
TeXOptions options = TeXOptions.consoleAppOptions(TeXConfig.objectLaTeX());
// Specify the file system working directory for the output
options.setOutputWorkingDirectory(new OutputFileSystemDirectory(Utils.getOutputDirectory()));
// Initialize the options
options.setSaveOptions(new PdfSaveOptions());

// Run the conversion
new TeXJob(Utils.getInputDirectory() + "hello-world.tex", new PdfDevice(), options).run();
```

For more examples, please visit [Convertion](/tex/java/conversion/) guides.
<br><br>

**Q: Can I create a custom format using Aspose.TeX for Java?**

**A:** Yes, the Library has such functionality. It is briefly described in the [Other TeX conversion output formats ](/tex/java/other-tex-formats/#creating-a-custom-format) article.
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

If there is a package that is not included in the list you can also [use such External LaTeX packages](/tex/java/external-latex-packages/).
<br><br>

**Q: Does Aspose.TeX for Java have functionality for geometric figure rendering?**

**A:** Yes, you can [write LaTeX figures to PNG or SVG](/tex/java/latex-figure-rendering/) using this Library.
<br><br>

**Q: How to install Aspose.TeX for Java Package from Maven?**

**A:** You can download its latest version directly from Aspose Maven Repository and install it within your Maven-based project by adding the following configurations to the pom.xml:

```Java
    <repository>
        <id>snapshots</id>
        <name>repo</name>
        <url>http://repository.aspose.com/repo/</url>
    </repository>
```

```Java
    <dependency>
        <groupId>com.aspose</groupId>
        <artifactId>aspose-tex</artifactId>
        <version>21.4</version>
    </dependency>
```

**Q: Can render LaTeX formulas using Aspose.TeX for Java?**

**A:** Yes, Aspose.TeX math rendering library lets you create an SVG or PNG image with a math formula. 
1. Instantiate the SvgMathRendererOptions class.
2. Specify the background color, preamble, resolution, foreground color, and scaling factor.
3. Specify the output stream for the log file.
4. Create a file stream to save the output image.
5. Create an object of the *(file format)MathRenderer* class and run rendering the formula by calling the *Render()* method. The resulting image will be written to the specified output stream.

For more examples, please visit [LaTeX math formulas rendering](/tex/java/latex-math-formula-rendering/) guides.
<br><br>

**Q: Where can I learn more about TeX?**

**A:** Take a look at the [General articles on LaTeX](/tex/java/general-articles-latex/) where you can learn the rules that every document author must follow. It also defines the structure of the source file, which is essentially a typesetting program.
<br><br>

**Q: What are the system requirements of Aspose.TeX for Java?**

**A:** Go to the [System Requirements](/tex/java/system-requirements/) page to get the actual information about operating systems and development environments needed to deal Aspose.TeX for Java.
<br><br>

**Q: Can I try the Solution before purchasing it?**

**A:** Yes, you can easily download Aspose.TeX for Java products for evaluation purposes. The evaluation version of Aspose.TeX (without a license specified) provides full product functionality except for some [evaluation limitations](/tex/java/licensing/#evaluation-version-limitations).

If you want to try out Aspose.TeX without evaluation limitations, request a 30-day [temporary license](https://purchase.aspose.com/temporary-license/).
<br><br>

**Q: Where can I get help if I have any issues with the Library?**

**A:** Check the [Aspose Forum](https://forum.aspose.com/c/tex/47) for answers or add a new topic with your issue if you did not find the one suitable for your problem. 
<br><br>

**Q: How can I get a license for Aspose.TeX for Java?**

**A:** Use the `License.setLicense` method to license the component. The easiest way to [set a license](/tex/java/licensing/) is to put the license file in the same folder as the aspose.tex.jar and specify the filename, without a path.
<br><br>

**Q: Can I see the functionality of this API Solution implemented in web applications?**

**A:** Check our [web solutions](https://products.aspose.app/tex/applications) to convert, view, merge, and edit TeX and LaTeX files, create mathematical equations, and many more.
<br><br>


