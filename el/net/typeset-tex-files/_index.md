---
translation: true
template: /_templates/_typeset-tex-files-net.md
title: Λειτουργία στοιχειοθεσίας TeX | .NET API
url: /net/typeset-tex-files/
description: "Λύση .NET API για εργασία με TeX. Μάθετε στο παράδειγμα πώς να δημιουργείτε στοιχειοθετήσεις TeX με μερικές γραμμές κώδικα C#."
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Πληκτρολογήστε αρχεία TeX
h2: "Πληκτρολογήστε ένα αρχείο TeX χρησιμοποιώντας μια προσαρμοσμένη μορφή TeX C# .NET"
---

{{<section overview>}}
---
p1: "Το TeX είναι γνωστό ως μία από τις γλώσσες σήμανσης δεδομένων και/ή ως γλώσσα στοιχειοθεσίας ταυτόχρονα. Σημαίνει ότι δεν μορφοποιείτε το κείμενό σας στο έγγραφο, αλλά εισάγετε το απλό κείμενο μαζί με τις εντολές. Ως έξοδο, θα λάβετε το μορφοποιημένο αρχείο της απαιτούμενης (καθορισμένης) μορφής. Το [*TeX*](https://docs.aspose.com/tex/net/what-is-tex/) είναι ο κεντρικός πυρήνας του συστήματος συνόλου δημοσιεύσεων (στοιχειοθεσία υπολογιστή)."
p2: "Για να κατανοήσετε περισσότερο τη στοιχειοθεσία TeX, μάθετε το [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) της Τεκμηρίωσης. Και σε αυτή τη σελίδα θα βρείτε αποσπάσματα κώδικα που εξηγούν πώς να στοιχειοθετήσετε ένα αρχείο TeX χρησιμοποιώντας μια προσαρμοσμένη μορφή TeX."
p3: "Για να εκτελέσουμε τα παραδείγματα χρειαζόμαστε:"
p4: "Το Aspose.TeX για .NET API το οποίο είναι ένα πλούσιο σε χαρακτηριστικά, ισχυρό και εύχρηστο API χειρισμού και μετατροπής εγγράφων για πλατφόρμα C#."
p5: "Ανοίξτε τη διαχείριση πακέτων NuGet και αναζητήστε Aspose.TeX και εγκαταστήστε. Μπορείτε επίσης να χρησιμοποιήσετε την ακόλουθη εντολή από την Κονσόλα Package Manager."
---

{{<section feature1>}}
---
title: Βήματα για τη στοιχειοθέτηση TeX χρησιμοποιώντας C#.
h3: "Κωδικός C# για στοιχειοθεσία TeX"
item1: "Δημιουργήστε τον πάροχο μορφής χρησιμοποιώντας την κλάση [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/)."
item2: "Δημιουργήστε επιλογές μετατροπής για μια προσαρμοσμένη μορφή με την επέκταση κινητήρα ObjectTeX χρησιμοποιώντας [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Μέθοδο [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Τάξη."
item3: "Καθορίστε τον κατάλογο εργασίας εισόδου εάν η κύρια είσοδος δεν παρέχεται ως ροή. Χρησιμοποιήστε την κλάση [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/) για αυτό."
item4: "Καθορίστε έναν κατάλογο εργασίας συστήματος αρχείων για την έξοδο. Χρησιμοποιήστε την κλάση [*OutputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/outputfilesystemdirectory/) για αυτό."
item5: "Εκτελέστε τη μέθοδο εργασίας [*TeXJob()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/) για [*XpsDevice*](https://reference.aspose.com/tex/net/aspose.tex.presentation.xps/xpsdevice/)."
item6: Βελτιώστε την έξοδο.
---