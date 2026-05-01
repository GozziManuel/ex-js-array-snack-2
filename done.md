<!-- // Crea un array (longBooks) con i libri che hanno più di 300 pagine;
const bookCopy = [...books];
const longBooks = bookCopy.filter((element) => element.pages > 300);
console.log(longBooks);

// Creare un array (longBooksTitles) che contiene solo i titoli dei libri contenuti in longBooks.
const longBooksTitles = longBooks.map((element) => element.title);
console.log(longBooksTitles);

// Stampa in console ogni titolo nella console. -->

SNACK 2

<!-- // Creare un array (availableBooks) che contiene tutti i libri disponibili.
const booksCopy = [...books];
const availableBooks = booksCopy.filter(
  (element) => element.available === true,
);
console.log(availableBooks);

// Crea un array (discountedBooks) con gli availableBooks, ciascuno con il prezzo scontato del 20% (mantieni lo stesso formato e arrotonda al centesimo)

const discountedBooks = availableBooks.map((e) => {
  const prezzoLibro = parseFloat(e.price);
  console.log(prezzoLibro);
  const Sconto = (prezzoLibro * 20) / 100;
  const PrezzoScontato = prezzoLibro - Sconto;
  return { ...e, price: (e.price = PrezzoScontato) };
});
console.log(discountedBooks);

// Salva in una variabile (fullPricedBook) il primo elemento di discountedBooks che ha un prezzo intero (senza centesimi).

const fullPricedBook = discountedBooks.find((e) => e.price % 1 === 0);
console.log(fullPricedBook); -->

SNACK 3

<!-- // Creare un array (authors) che contiene gli autori dei libri.
const booksCopy = [...books];
let authors = booksCopy.map((e) => e.author);
console.log(authors);

// Crea una variabile booleana (areAuthorsAdults) per verificare se gli autori sono tutti maggiorenni.
const areAuthorsAdults = authors.every((e) => e.age >= 18);

console.log(areAuthorsAdults);
// Ordina l’array authors in base all’età, senza creare un nuovo array.
// (se areAuthorsAdult è true, ordina in ordine crescente, altrimenti in ordine decrescente)

if (areAuthorsAdults === true) {
  authors = authors.sort((a, b) => a.age - b.age);
} else {
  authors = authors.sort((a, b) => b.age - a.age);
} -->
