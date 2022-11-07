---
translation: true
template: /_templates/_customize-input-net.md
title: Δημιουργία προσαρμοσμένης εισαγωγής TeX | .NET API
url: /net/customize-input/
description: "Λύση .NET API για εργασία με TeX. Μάθετε στο παράδειγμα πώς να δημιουργείτε προσαρμοσμένη είσοδο για αρχείο TeX με μερικές γραμμές κώδικα C#."
keywords: προσαρμοσμένη εισαγωγή tex net api, C# api για προσαρμογή tex
informat: TEX
family: tex
platformtag: net
---

{{<section banner>}}
---
h1: Προσαρμογή εισαγωγής
h2: "Λύση .NET API για την προσαρμογή της εισαγωγής αρχείων TeX"
---

{{<section overview>}}
---
p1: "Το TeX είναι γνωστό ως γλώσσα στοιχειοθεσίας. Σημαίνει ότι δεν μορφοποιείτε το κείμενό σας στο έγγραφο, αλλά εισάγετε το απλό κείμενο μαζί με τις εντολές. Όπως περιγράφεται στο άρθρο [*TeX I/O*](https://docs.aspose.com/tex/net/tex-io/) της Τεκμηρίωσης, η εργασία TeX εκτελείται σε ένα ρητά καθορισμένο αρχείο TeX. Έτσι, συμπεριλαμβάνουμε αυτό το αρχείο στην είσοδο μιας συγκεκριμένης εργασίας TeX."
p2: "Σε αυτή τη σελίδα θα βρείτε ένα παράδειγμα κώδικα που εξηγεί πώς να προσαρμόσετε την εισαγωγή των αρχείων πηγής TeX λαμβάνοντας υπόψη ότι η είσοδος πρέπει να ακολουθεί τη σύνταξη TeX και, ιδανικά, να περιέχει μόνο εντολές που είναι γνωστές στον κινητήρα."
p3: "Για να προσαρμόσουμε την εισαγωγή αρχείων .tex χρειαζόμαστε:"
p4: "Το Aspose.TeX για .NET API το οποίο είναι ένα πλούσιο σε χαρακτηριστικά, ισχυρό και εύχρηστο API χειρισμού και μετατροπής εγγράφων για πλατφόρμα C#."
p5: "Ανοίξτε τη διαχείριση πακέτων NuGet και αναζητήστε Aspose.TeX και εγκαταστήστε. Μπορείτε επίσης να χρησιμοποιήσετε την ακόλουθη εντολή από την Κονσόλα Package Manager."
---

{{<section feature1>}}
---
title: "Βήματα για την προσαρμογή της εισόδου TeX C#:"
h3: "Κωδικός C# για προσαρμογή εισόδου TeX"
item1: "Χρήση [*ConsoleAppOptions()*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/consoleappoptions) Μέθοδος [*TeXOptions*](https://reference.aspose.com/tex/net/aspose.tex/texoptions/) Κατηγορία, δημιουργήστε επιλογές μηχανών TeX χωρίς μορφή κατά την επέκταση κινητήρα ObjectTeX."
item2: "Χρησιμοποιώντας την κλάση [*InputFileSystemDirectory*](https://reference.aspose.com/tex/net/aspose.tex.io/inputfilesystemdirectory/), καθορίστε έναν κατάλογο εργασίας συστήματος αρχείων για την είσοδο."
item3: "Με τη βοήθεια της μεθόδου [*TeXJob.CreateFormat()*](https://reference.aspose.com/tex/net/aspose.tex/texjob/createformat/), δημιουργήστε την προσαρμοσμένη μορφή."
---