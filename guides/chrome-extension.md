---
title: "Etherly Extension για Chrome"
description: "Εγκατάσταση και ρύθμιση του Chrome Extension για αυτόματο συγχρονισμό Airbnb κρατήσεων."
---

# Etherly Extension για Chrome

Το Etherly Chrome Extension κατεβάζει αυτόματα τις κρατήσεις σας από το Airbnb κάθε ώρα και τις στέλνει στο Etherly Sync, χωρίς να χρειάζεται να κάνετε τίποτα χειροκίνητα.

<Note>
Το extension χρειάζεται να είναι ανοιχτός ο Chrome και να έχετε συνδεθεί στο Airbnb.
</Note>

## Εγκατάσταση

<Steps>
  <Step title="Ενεργοποιήστε Developer Mode στο Chrome">
    Ανοίξτε **chrome://extensions** στον Chrome.
    Ενεργοποιήστε το toggle **«Developer mode»** πάνω δεξιά.
  </Step>
  <Step title="Κατεβάστε και εγκαταστήστε το extension">
    Μεταβείτε στις **Ρυθμίσεις → Airbnb → Chrome Extension** και πατήστε **«Εγκατάσταση Etherly Extension»**.

    Ο Chrome θα σας ρωτήσει αν θέλετε να εγκαταστήσετε το extension — πατήστε **«Add extension»**.

    <Warning>
    Αν ο Chrome εμφανίσει μήνυμα «This extension is not from the Chrome Web Store», αυτό είναι αναμενόμενο για private extensions. Πατήστε **«Add extension»** για να συνεχίσετε.
    </Warning>
  </Step>
  <Step title="Συνδέστε το extension με τον λογαριασμό σας">
    Μεταβείτε στις **Ρυθμίσεις → Airbnb** στο Etherly και αντιγράψτε το **Extension Token**.

    Κλικάρετε το εικονίδιο του Etherly στη γραμμή εργαλείων του Chrome, επικολλήστε το token και πατήστε **«Σύνδεση»**.
  </Step>
</Steps>

## Αυτόματες ενημερώσεις

Το extension ενημερώνεται αυτόματα χωρίς να χρειαστεί να κάνετε κάτι. Ο Chrome ελέγχει για νέες εκδόσεις κάθε 5 ώρες.

Για να ελέγξετε άμεσα για ενημέρωση: ανοίξτε **chrome://extensions** και πατήστε **«Update»**.

## Πώς λειτουργεί

Κάθε ώρα το extension:

1. Ανοίγει τη σελίδα κρατήσεων του Airbnb (ή χρησιμοποιεί υπάρχον tab)
2. Κατεβάζει αυτόματα το CSV με τις κρατήσεις
3. Το στέλνει στο Etherly Sync
4. Κλείνει το tab αν το άνοιξε μόνο του

Μπορείτε επίσης να ξεκινήσετε συγχρονισμό χειροκίνητα πατώντας **«Sync τώρα»** από το popup του extension.

## Αντιμετώπιση προβλημάτων

**«Δεν βρέθηκε token»**: Επαναλάβετε το βήμα σύνδεσης token από τις Ρυθμίσεις.

**«CSV download returned empty result»**: Βεβαιωθείτε ότι είστε συνδεδεμένοι στο Airbnb στον Chrome.

**Το extension δεν εμφανίζει νέες κρατήσεις**: Ελέγξτε ότι το Airbnb tab φορτώνει κανονικά και δοκιμάστε χειροκίνητο sync.
