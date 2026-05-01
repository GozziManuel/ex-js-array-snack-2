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

SNACK 4

<!-- // Creare un array (ages) che contiene le età degli autori dei libri.
const booksCopy = [...books];
const ages = booksCopy.map((e) => e.author.age);
console.log(ages);

// Calcola la somma delle età (agesSum) usando reduce.
const agesSum = ages.reduce((acc, curr) => acc + curr, 0);
console.log(agesSum);

// Stampa in console l’età media degli autori dei libri.
console.log(agesSum / books.length); -->

Bonus 1

<!-- // Usando la l'API http://localhost:3333/books/{id} usa la combinazione di .map() e Promise.all(),
// per creare una funzione (getBooks)
//  che a partire da un array di id (ids), ritorna una promise che risolve un array di libri (books).
const handleAsync = async (url) => {
  const response = await fetch(url);
  const obj = await response.json();
  return obj;
};
async function getBooks(ids) {
  const fetchApi = ids.map((el) =>
    handleAsync(`http://localhost:3333/books/${el}`),
  );
  const books = await Promise.all(fetchApi);
  return books;
}

(async () => {
  const ids = [2, 13, 7, 21, 19];
  const object = await getBooks(ids);
  console.log(object);
})();

// Testala con l’array [2, 13, 7, 21, 19] . -->

Bonus 2

<!-- // Crea una variabile booleana (areThereAvailableBooks) per verificare se c’è almeno un libro disponibile.
const bookCopy = [...books];

const areThereAvailableBooks = bookCopy.some((el) => el.available === true);
console.log(areThereAvailableBooks);

// Crea un array (booksByPrice) con gli elementi di books ordinati in base al prezzo (crescente).
const booksByPrice = bookCopy.sort(
  (a, b) => parseFloat(a.price) - parseFloat(b.price),
);
bookCopy.sort((a, b) =>
  (a.available === b.available ? 0 : a.available) ? -1 : 1,
);
console.log(booksByPrice);

// Ordina l’array booksByPricein base alla disponibilità (prima quelli disponibili), senza creare un nuovo array. -->
