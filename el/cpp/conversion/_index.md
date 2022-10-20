---
translation: true
template: /_templates/_conversion-cpp.md
title: Μετατροπή αρχείων TeX (LaTeX) | C++
url: /cpp/conversion/
keywords: μετατροπέας tex cpp api, μετατροπέας tex c++ api
description: Λύση API C++ μετατροπής TeX(LaTeX). Μετατρέψτε αρχεία LaTeX σε PDF, XPS και Εικόνες, συμπεριλαμβανομένων των PNG, JPEG, TIFF, BMP με λίγες γραμμές κώδικα C++.
family: tex
platformtag: cpp
feature: conversion
---

{{<section banner>}}
---
h1: Μετατροπή TeX και LaTeX
h2: "Λύση API μετατροπέα TeX για C++."
---

{{<section overview>}}
---
p1: "Το Aspose.TeX είναι ένα API για το σύστημα Object TeX, για λεπτομέρειες του αρχείου Tex, εδώ είναι η [Εισαγωγή Tex](https://docs.aspose.com/tex/cpp/what-is-tex/). Οι προγραμματιστές μπορούν εύκολα να μετατρέψουν το TeX σε μορφές PDF, XPS, PNG, JPG, BMP και TIFF ενσωματώνοντας το API για C++. Παρακάτω είναι μερικά δείγματα κώδικα που οι προγραμματιστές μπορούν να βελτιώσουν και να ενσωματώσουν σε λύσεις LaTex."
p2: "Η λύση API για Java εδώ σάς επιτρέπει να μετατρέπετε αρχεία TeX και LaTeX μέσω προγραμματισμού, αλλά μπορεί να σας φανεί χρήσιμο να δείτε και να δοκιμάσετε [μετατροπείς μεταξύ πλατφορμών](https://products.aspose.app/tex/conversion) που έχουν αναπτυχθεί σε αυτά τα εγγενή API. Εκεί μπορείτε επίσης να βρείτε [εφαρμογές](https://products.aspose.app/tex/applications) για να δημιουργήσετε και να επεξεργαστείτε αρχεία TeX, πίνακες, γραφικά, για να συγχωνεύσετε αρχεία σε αυτό της μορφής PDF κ.λπ."
---

{{<section feature1>}}
---
title: "Μετατροπή LaTeX σε Εικόνες, XPS, PDF, SVG C++."
h3: "Παράδειγμα κώδικα C++ Μετατροπή TeX σε Εικόνες, XPS, PDF ή SVG."
item1: "Το API υποστηρίζει BMP, JPEG, PDF, SVG, TIFF, XPS και PNG ως μορφές εξόδου. Για να μετατρέψετε αρχεία TeX σε Εικόνες, PDF, XPS ή SVG, πραγματοποιήστε τα ακόλουθα βήματα:"
item2: "Δημιουργήστε παράδειγμα της [Τάξης TeXOptions](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options)."
item3: "Καθορίστε τον τύπο και το μέγεθος της εικόνας χρησιμοποιώντας το [*ImageDevice*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device)."
item4: "Καθορίστε τον κατάλογο εργασίας του συστήματος αρχείων για την έξοδο/είσοδο χρησιμοποιώντας το [*OutputWorkingDirectory*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495ba1b40800495]https://king./reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_options#aa4f4ea6dab7db5ba1b40800495f16f63)."
item5: "Αρχικοποιήστε τις επιλογές για αποθήκευση χρησιμοποιώντας [*BmpSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.bmp_save_options), [*PngSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.png_save_options), [*TiffSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.tiff_save_options), [*JpegSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.jpeg_save_options) ή [*PdfSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_save_options), [*SvgSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_save_options), [*XpsSaveOptions*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_save_options), το οποίο είναι προεπιλεγμένο, δεν χρειάζεται να οριστεί."
item6: "Εκτέλεση μετατροπής χρησιμοποιώντας τη μέθοδο εκτέλεσης του [*TeXJob()*](https://reference.aspose.com/tex/cpp/class/aspose.te_x.te_x_job) για το [ImageDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.image.image_device) ή [PdfDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.pdf.pdf_device), [ SvgDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.svg.svg_device), [XpsDevice](https://reference.aspose.com/tex/cpp/class/aspose.te_x.presentation.xps.xps_device)."
item7: "Το Aspose.TeX για C++ λειτουργεί καλά σε οποιοδήποτε περιβάλλον ανάπτυξης που υποστηρίζει C++, αλλά οι ακόλουθες απαιτήσεις συνιστώνται ιδιαίτερα:"
item8: Microsoft Visual Studio 2015 ή νεότερη έκδοση.
item9: Επιτραπέζιος υπολογιστής Microsoft Windows (7, 8, 10).
item10: Λειτουργικά συστήματα διακομιστή (2008, 2012) κ.λπ.
item11: Συστήματα Linux (Ubuntu-16.04 ή νεότερη έκδοση).
---


