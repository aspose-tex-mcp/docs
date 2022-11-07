---
translation: true
template: /_templates/_load-tex-from-disk-net.md
title: Φόρτωση TeX από δίσκο | Λύση .NET API
url: /net/load-tex-from-disk/
description: "Λύση .NET API για εργασία με TeX. Μάθετε στο παράδειγμα πώς να φορτώνετε ένα αρχείο TeX από δίσκο με μερικές γραμμές κώδικα C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Φορτώστε τα αρχεία προέλευσης TeX από το δίσκο
h2: "Λύση .NET API για τη φόρτωση αρχείων TeX/LaTeX από το δίσκο"
---

{{<section overview>}}
---
p1: "Το TeX είναι γνωστό ως γλώσσα στοιχειοθεσίας. Σημαίνει ότι δεν μορφοποιείτε το κείμενό σας στο έγγραφο, αλλά εισάγετε το απλό κείμενο μαζί με τις εντολές. Ως έξοδο, θα λάβετε το μορφοποιημένο αρχείο της απαιτούμενης (καθορισμένης) μορφής. Το [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) είναι ο κεντρικός πυρήνας του συστήματος συνόλου δημοσιεύσεων (στοιχειοθεσία υπολογιστή). Μια εργασία TeX εκτελείται σε ένα ρητά καθορισμένο αρχείο TeX. Για να κατανοήσετε καλύτερα την είσοδο και την έξοδο TeX, μάθετε το [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) της Τεκμηρίωσης."
p2: "Όπως είναι γνωστό, ο κύριος σκοπός του TeX είναι να βοηθήσει στη δημιουργία μαθηματικής ή τεχνικής γραφής κειμένου. Αλλά πριν από οποιουσδήποτε χειρισμούς, θα πρέπει πρώτα να φορτωθεί το αρχείο. Εδώ θα βρείτε αποσπάσματα κώδικα που εξηγούν πώς να φορτώνετε αρχεία πηγής TeX από το δίσκο χρησιμοποιώντας καταλόγους συστήματος αρχείων για είσοδο και έξοδο, έξοδο σε συσκευή XPS, εγγραφή τερματικού εξόδου στην κονσόλα."
p3: "Για να εκτελέσουμε τα παραδείγματα χρειαζόμαστε:"
p4: "Το Aspose.TeX για .NET API το οποίο είναι ένα πλούσιο σε χαρακτηριστικά, ισχυρό και εύχρηστο API χειρισμού και μετατροπής εγγράφων για πλατφόρμα C#."
p5: "Ανοίξτε τη διαχείριση πακέτων NuGet και αναζητήστε Aspose.TeX και εγκαταστήστε. Μπορείτε επίσης να χρησιμοποιήσετε την ακόλουθη εντολή από την Κονσόλα Package Manager."
---

{{<section feature1>}}
---
title: Βήματα για τη φόρτωση του TeX από έναν δίσκο C#.
h3: "Κωδικός C# για φόρτωση TeX"
item1: "Δημιουργήστε επιλογές μετατροπής για μια προσαρμοσμένη μορφή με την επέκταση κινητήρα ObjectTeX χρησιμοποιώντας [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Μέθοδο [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Τάξη."
item2: "Καθορίστε έναν κατάλογο εργασίας συστήματος αρχείων για την είσοδο. Χρησιμοποιήστε την κλάση [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) για αυτό."
item3: "Καθορίστε έναν κατάλογο εργασίας συστήματος αρχείων για την έξοδο χρησιμοποιώντας την κλάση [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/)."
item4: "Καθορίστε την κονσόλα ως τερματικό εξόδου χρησιμοποιώντας την κλάση [*OutputConsoleTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputconsoleterminal/)."
item5: "Καθορίστε ένα τερματικό μνήμης ως τερματικό εξόδου, εάν χρειάζεστε. Για αυτό χρησιμοποιήστε την κλάση [*OutputMemoryTerminal*](https://reference.aspose.com/tex/net/aspose.tex.io/outputmemoryterminal/)."
item6: "Εκτελέστε τη μέθοδο εργασίας [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) για [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item7: Βελτιώστε την έξοδο.
---