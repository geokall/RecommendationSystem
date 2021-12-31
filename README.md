# Movies Recommendation System

## What this is all about
## Σκοπός
Σκοπός της εργασίας είναι να υλοποιήσετε ένα frontend το οποίο θα σας επιτρέπει μέσω της χρήσης ενός API να προσπελάσετε ταινίες και αξιολογήσεις χρηστών και να τα αξιοποιήσετε προκειμένου να φτιάξετε ένα σύστημα παροχής προτάσεων (recommendation) προς τους χρήστες του frontend.

## Λειτουργικότητα
Συγκεκριμένα η λειτουργικότητα που θα υποστηρίζει το frontend θα είναι η εξής:

Αναζήτηση με τίτλο ταινίας και εμφάνιση στο frontend στοιχείων ταινίας με δομημένο τρόπο
Προσθήκη αξιολόγησης [0.5, 1, 1.5, 2, 2.5,..., 5] για την ταινία. Οι αξιολογήσεις θα αποθηκεύονται σε ένα αντικείμενο για κάθε χρήστη στον client.
Προβολή προτάσεων για ταινίες που το σύστημα εκτιμά ότι θα άρεσαν στο χρήστη.
Προσέγγιση
Η λογική του recommendation βασίζεται στην τεχνική "collaborative filtering", όπου –πρακτικά- οι προτιμήσεις ενός χρήστη συγκρίνονται με προτιμήσεις άλλων χρηστών στα ίδια αντικείμενα. Το αποτέλεσμα της σύγκρισης ονομάζεται συντελεστής συσχέτισης (correlation coefficient) και το σύστημα θεωρεί ότι όσο μεγαλύτερος είναι τόσο περισσότερο τα “profiles” δύο χρηστών ταυτίζονται. Επομένως, προτιμήσεις με υψηλή βαθμολογία από ένα χρήστη μπορούν να χρησιμοποιηθούν ως συστάσεις για έναν άλλο με τον οποίο "ταυτίζονται". Ένας τέτοιος συντελεστής είναι και ο Pearson correlation coefficient[1].

Αναμένεται να χρησιμοποιήσετε pure Javascript, HTML, CSS (προαιρετικά).

## Στόχοι
Μείωση του όγκου των δεδομένων που μεταφέρονται μέσω του δικτύου χρησιμοποιώντας τεχνικές στο frontend
Χρήση μίας μόνο σελίδας .html και δυναμική διαχείριση του περιεχομένου (επομένως έντονη χρήση της Javascript και του AJAX)
Ελαχιστοποίηση σφαλμάτων στο UI (π.χ. μη εύρεση ταινίας λόγω λανθασμένου τρόπου γραφής)
API (Backend)
URL: http://62.217.127.19:8010/movie

Μέθοδος: POST

Είσοδος: Ένα string ως json της μορφής {"keyword":"Toy"}

Έξοδος: Ένα json array με στοιχεία της/των ταινίας/ιών συμπεριλαμβανόμενου και του ID της/τους (mID) που ξεκινούν από το input string.



URL: http://62.217.127.19:8010/movie/{mId}

Μέθοδος: GET

Είσοδος: mID ταινίας ως παράμετρο με τίτλο "id" στο HTTP request

Έξοδος: Ένα json array με τα στοιχεία της ταινίας



URL: http://62.217.127.19:8010/ratings

Μέθοδος: POST

Είσοδος: Ένα json που θα περιέχει ένα array με mID ταινιών της μορφής {"movieList":[4,5,12]}

Έξοδος: Ένα json array με αξιολογήσεις για κάθε ταινία και κάθε χρήστη



URL: http://62.217.127.19:8010/ratings/{id}

Μέθοδος: GET

Είσοδος: uID χρήστη ως παράμετρο με τίτλο "id" στο HTTP request

Έξοδος: Ένα json array με τα ratings και τα υπόλοιπα στοιχεία των ταινιών τις οποίες ο χρήστης uID έχει αξιολογήσει.

Παραδοτέα και προθεσμίες<br />
Ως προθεσμία παράδοσης ορίζεται η 07-01-2022 23:55:00<br />
Θα πρέπει να παραδώσετε όλα τα αρχεία html, css και js που έχετε υλοποιήσει σε ένα αρχείο .zip με όνομα τον Α.Μ. σας.
Σημειώσεις<br />
Δε χρειάζεται να υλοποιήσετε μηχανισμούς authorization, authentication, accounting. Θεωρείστε ότι τη σελίδα τη χρησιμοποιεί ένας χρήστης για όσο διάστημα την έχει ανοιχτή.<br />
Θα πρέπει να χρησιμοποιήσετε τα APIs και τις τεχνικές που είδαμε στο μάθημα (vanilla JS). Όχι frameworks και τίποτα μετά από την ES2015<br />
Μπορείτε να βρείτε τους κανόνες για την παράδοση της εργασίας εδώ: http://www.dit.hua.gr/~tserpes/instructions.html

## How it works
User is able to search a movie only by typing alphanumerical. Only english letters and non-special characters are allowed.<br />
User must type at least 3 characters.<br />
User must rate at least 2 movies and maximum 5 movies.<br />
User is able to re-rate the same movies but not more than 5. In case user tries to rate a 6th movie, an alert message will be appeared in the screen.<br />
Calculation button once is clicked, it gets disabled. Need to re-rate to be enabled again.<br />
In order for the algorithm to recommend movies, there must be users that have been scored with >= 0.7 pearson.<br />
If none filtered user found with more than 0.7 pearson, alert message will be appeared in the screen.<br />

## Credits

Below you can find all the credits I'd like to give. <br />
[https://www.digitalvidya.com/blog/collaborative-filtering/](https://www.digitalvidya.com/blog/collaborative-filtering/) <br/>
[https://becominghuman.ai/introduction-to-recommendation-system-in-javascript-74209c7ff2f7](https://becominghuman.ai/introduction-to-recommendation-system-in-javascript-74209c7ff2f7) <br/>
[https://stackoverflow.com/questions/1069666/sorting-object-property-by-values](https://stackoverflow.com/questions/1069666/sorting-object-property-by-values) <br/>
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions) <br/>
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce) <br/>
[https://coderedirect.com/questions/547235/await-with-array-foreach-containing-async-await](https://coderedirect.com/questions/547235/await-with-array-foreach-containing-async-await) <br/>
[https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Async_await](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Asynchronous/Async_await) <br/>
[https://stackoverflow.com/questions/4550505/getting-a-random-value-from-a-javascript-array](https://stackoverflow.com/questions/4550505/getting-a-random-value-from-a-javascript-array) <br/>
[https://stackoverflow.com/questions/15148659/how-can-i-use-queryselector-on-to-pick-an-input-element-by-name](https://stackoverflow.com/questions/15148659/how-can-i-use-queryselector-on-to-pick-an-input-element-by-name) <br/>
[https://stackoverflow.com/questions/7271490/delete-all-rows-in-an-html-table](https://stackoverflow.com/questions/7271490/delete-all-rows-in-an-html-table) <br/>