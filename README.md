# Catatan Belajar JavaScript

Repositori ini berisi dokumentasi dan kode latihan harian saya selama mempelajari JavaScript.

---

## Daftar Isi
- [1. JavaScript Trivia Bot](#1-javascript-trivia-bot)
- [2. Pembuat Kalimat (Sentence Maker)](#2-pembuat-kalimat-sentence-maker)
- [3. Fortune Teller (Peramal Keberuntungan)](#3-fortune-teller-peramal-keberuntungan)
- [4. Build a Calculator (Kalkulator Sederhana)](#4-build-a-calculator-kalkulator-sederhana)
- [5. Membangun Fungsi Pemeriksaan Boolean (booWho)](#5-membangun-fungsi-pemeriksaan-boolean-boowho)
- [6. Buat Masker Email (Email Masker)](#6-buat-masker-email-email-masker)
- [7. Konverter Celsius ke Fahrenheit (convertCtoF)](#7-konverter-celsius-ke-fahrenheit-convertctof)
- [8. Card Counting Assistant (Penghitung Kartu Blackjack)](#8-card-counting-assistant-penghitung-kartu-blackjack)
- [9. Algoritma Pemotong String (Truncate a String Algorithm)](#9-algoritma-pemotong-string-truncate-a-string-algorithm)
- [10. Kalkulator Tahun Kabisat (Leap Year Calculator)](#10-kalkulator-tahun-kabisat-leap-year-calculator)
- [11. Alat Konfirmasi Akhir String (Confirm the Ending)](#11-alat-konfirmasi-akhir-string-confirm-the-ending)
- [12. Program Pemilih Makan Siang (Lunch Picker)](#12-program-pemilih-makan-siang-lunch-picker)
- [13. Penerjemah Skor Golf (Golf Score Translator)](#13-penerjemah-skor-golf-golf-score-translator)
- [14. Membangun Validator Manifest Kargo (Build a Cargo Manifest Validator)](#14-validator-manifest-kargo-build-a-cargo-manifest-validator)
- [15. Buat Permainan Kuis (Build a Quiz Game)](#14-buat-permainan-kuis-build-a-quiz-Game)

---

## 1. JavaScript Trivia Bot

Pada latihan ini, saya belajar membuat program bot sederhana menggunakan JavaScript untuk melatih konsep variabel (`let`), *reassign* nilai variabel, dan *string concatenation*.

### Objective & User Stories
1. Menampilkan pesan menyapa (*greeting message*).
2. Membuat variabel `botName`, `botLocation`, dan `favoriteLanguage`.
3. Menampilkan informasi nama dan lokasi bot.
4. Menampilkan bahasa pemrograman favorit.
5. Memperbarui nilai variabel `codingFact` beberapa kali (*reassign*).
6. Menampilkan pesan perpisahan.

### Solusi Kode

```javascript
console.log("Hello! I'm your coding fun fact guide!");

let botName = "Wahyu";
let botLocation = "East Java";
let favoriteLanguage = "Javascript";

console.log("My name is " + botName + " and I live on " + botLocation + ".");
console.log("My favorite programming language is " + favoriteLanguage + ".");

// Menampilkan fakta 1
let codingFact = "Java, " + favoriteLanguage;
console.log(codingFact);

// Reassign nilai ke fakta 2
codingFact = "Java, HTML, " + favoriteLanguage;
console.log(codingFact);

// Reassign nilai ke fakta 3
codingFact = "Java, HTML, CSS, and " + favoriteLanguage;
console.log(codingFact);

// Pesan perpisahan
console.log("It was fun sharing these facts with you. Goodbye! - " + botName + " from " + botLocation + ".");
```

### Hasil Output

```text
Hello! I'm your coding fun fact guide!
My name is Wahyu and I live on East Java.
My favorite programming language is Javascript.
Java, Javascript
Java, HTML, Javascript
Java, HTML, CSS, and Javascript
It was fun sharing these facts with you. Goodbye! - Wahyu from East Java.
```

---

## 2. Pembuat Kalimat (Sentence Maker)

Pada latihan ini, saya belajar membuat templat cerita dinamis menggunakan dua pendekatan: pendekatan dasar (*basic assignment & string concatenation*) dan pendekatan profesional (*reusable function & template literals*).

### Objective & User Stories
1. Mendeklarasikan variabel `adjective`, `noun`, `verb`, `place`, `adjective2`, dan `noun2` menggunakan `let`.
2. Mengisi nilai string awal ke setiap variabel.
3. Mendeklarasikan variabel `firstStory` dan mengisinya dengan templat cerita pertama.
4. Menampilkan `firstStory` ke konsol.
5. Memberikan nilai baru pada variabel-variabel tersebut (*reassign*).
6. Mendeklarasikan `secondStory` dan mengisinya dengan cerita kedua.
7. Menampilkan `secondStory` ke konsol.

### Solusi Kode (Solusi Basic & Refactoring Pro-Code)

#### Cara 1: Pendekatan Dasar (Basic Solution)

```javascript
// Mengisi nilai awal
let adjective = "cute", 
    noun = "cat", 
    verb = "eat", 
    place = "cat house", 
    adjective2 = "big", 
    noun2 = "mouse";

const firstStory = "Once upon a time, there was a(n) " + adjective + " " + noun + " who loved to eat " + noun2 + ". The " + noun + " lived in a " + place + " and had " + adjective2 + " nostrils that blew fire when it was " + verb + ".";

console.log("First story: " + firstStory);

// Reassign nilai baru untuk cerita kedua
adjective = "big";
noun = "dog";
verb = "bark";
place = "house";
adjective2 = "large";
noun2 = "bone";

const secondStory = "Once upon a time, there was a(n) " + adjective + " " + noun + " who loved to eat " + noun2 + ". The " + noun + " lived in a " + place + " and had " + adjective2 + " nostrils that blew fire when it was " + verb + ".";

console.log("Second story: " + secondStory);
```

#### Cara 2: Pendekatan Efisien (Pro-Code dengan Function)

```javascript
// Membuat pembuat/pabrik cerita menggunakan Function dan Template Literals (${})
function buatCerita(adj, nn, vb, plc, adj2, nn2) {
    return `Once upon a time, there was a(n) ${adj} ${nn} who loved to eat${nn2}. The ${nn} lived in a${plc} and had ${adj2} nostrils that blew fire when it was${vb}.`;
}

// Memanggil fungsi secara efisien
let firstStory = buatCerita("cute", "cat", "eat", "cat house", "big", "mouse");
let secondStory = buatCerita("big", "dog", "bark", "house", "large", "bone");

console.log("First story: " + firstStory);
console.log("Second story: " + secondStory);
```

### Hasil Output

```text
First story: Once upon a time, there was a(n) cute cat who loved to eat mouse. The cat lived in a cat house and had big nostrils that blew fire when it was eat.

Second story: Once upon a time, there was a(n) big dog who loved to eat bone. The dog lived in a house and had large nostrils that blew fire when it was bark.
```

---

## 3. Fortune Teller (Peramal Keberuntungan)

Pada latihan ini, saya belajar memilih teks ramalan secara acak menggunakan fungsi `Math.random()`, `Math.floor()`, serta logika pengkondisian `if-else`.

### Objective & User Stories
1. Menginisialisasi lima variabel `fortune1` sampai `fortune5` dengan nilai string ramalan.
2. Memilih angka acak antara 1 dan 5 (inklusif) dan menyimpannya ke variabel `randomNumber`.
3. Menentukan variabel `selectedFortune` berdasarkan nilai `randomNumber` menggunakan pengkondisian `if-else`.
4. Menampilkan `selectedFortune` ke konsol.

### Solusi Kode

```javascript
const fortune1 = "Your cat will look very cuddly today."; 
const fortune2 = "The weather will be nice tomorrow.";
const fortune3 = "Be cautious of your new neighbors.";
const fortune4 = "You will find a new hobby soon.";
const fortune5 = "It would be wise to avoid the color red today.";

// Menghasilkan angka acak antara 1 dan 5
const randomNumber = Math.floor(Math.random() * 5 + 1);

let selectedFortune;
if (randomNumber === 1) {
  selectedFortune = fortune1;
} else if (randomNumber === 2) {
  selectedFortune = fortune2;
} else if (randomNumber === 3) {
  selectedFortune = fortune3;
} else if (randomNumber === 4) {
  selectedFortune = fortune4;
} else {
  selectedFortune = fortune5;
}

console.log(`Your Fortune Number today is ${randomNumber}. \nIt is said,`);
console.log(selectedFortune);
```

### Hasil Output

```text
Your Fortune Number today is 3. 
It is said,
Be cautious of your new neighbors.
```

---

## 4. Build a Calculator (Kalkulator Sederhana)

Pada latihan ini, saya belajar membuat fungsi-fungsi kalkulasi matematika dasar di JavaScript, meliputi penjumlahan, pengurangan, perkalian, pembagian (dengan validasi pembagian nol), pemangkatan, dan akar kuadrat.

### Objective & User Stories
1. Membuat fungsi `calculateSum` untuk menjumlahkan dua angka.
2. Membuat fungsi `calculateDifference` untuk menghitung selisih dua angka.
3. Membuat fungsi `calculateProduct` untuk mengalikan dua angka.
4. Membuat fungsi `calculateQuotient` untuk membagi dua angka serta menangani pembagian dengan angka `0`.
5. Membuat fungsi `calculateSquare` untuk memangkatkan dua sebuah angka.
6. Membuat fungsi `calculateSquareRoot` untuk menghitung akar kuadrat menggunakan `Math.sqrt()`.

### Solusi Kode

```javascript
// Penjumlahan
function calculateSum(num1, num2) {
  return num1 + num2;
}

console.log(calculateSum(2, 5));
console.log(calculateSum(10, 10));
console.log(calculateSum(5, 5));

// Pengurangan
function calculateDifference(num1, num2) {
  return num1 - num2;
}

console.log(calculateDifference(22, 5));
console.log(calculateDifference(12, 1));
console.log(calculateDifference(17, 9));

// Perkalian
function calculateProduct(num1, num2) {
  return num1 * num2;
}

console.log(calculateProduct(13, 5));

// Pembagian dengan validasi angka nol
function calculateQuotient(num1, num2) {
  return num2 === 0 ? "Error: Division by zero" : num1 / num2;
}

console.log(calculateQuotient(7, 11));
console.log(calculateQuotient(3, 0));

// Pemangkatan (Square)
function calculateSquare(num) {
  return num ** 2;
}

console.log(calculateSquare(2));
console.log(calculateSquare(9));

// Akar Kuadrat (Square Root)
function calculateSquareRoot(num) {
  return Math.sqrt(num);
}

console.log(calculateSquareRoot(25));
console.log(calculateSquareRoot(100));
```

### Hasil Output

```text
7
20
10
17
11
8
65
0.6363636363636364
Error: Division by zero
4
81
5
10
```

---

## 5. Membangun Fungsi Pemeriksaan Boolean (booWho)

Pada latihan ini, saya belajar membuat fungsi untuk memeriksa apakah sebuah nilai merupakan tipe data Boolean primitif (`true` atau `false`). Saya menggunakan operator `typeof` yang merupakan cara paling efisien dalam JavaScript.

### Objective & User Stories
1. Membuat fungsi `booWho` yang menerima satu argumen.
2. Mengembalikan `true` jika argumen adalah tipe boolean primitif.
3. Mengembalikan `false` jika argumen bukan boolean.

### Solusi Kode

```javascript
// Fungsi pengecekan boolean yang efisien
function booWho(value) {
  return typeof value === "boolean";
}

// Pengujian dengan berbagai tipe data
console.log(booWho(true));           // true
console.log(booWho(false));          // true
console.log(booWho([1, 2, 3]));      // false
console.log(booWho("true"));         // false
console.log(booWho(1));              // false
```

### Hasil Output

```text
true
true
false
false
false
```

---

## 6. Buat Masker Email (Email Masker)

Pada latihan ini, saya belajar membuat fungsi untuk menyembunyikan (*masking*) sebagian dari nama pengguna pada alamat email dengan karakter asterisk (`*`) untuk menjaga privasi informasi sensitif.

### Objective & User Stories
1. Membuat fungsi bernama `maskEmail` yang menerima argumen string `email`.
2. Menyembunyikan bagian tengah *username* pada email dengan tanda `*` dan mempertahankan huruf pertama, huruf terakhir *username*, serta nama domain.
3. Deklarasi variabel `email` di luar fungsi dan menampilkan hasil pemanggilan fungsi ke konsol.

### Solusi Kode (Pendekatan Utama & Alternatif)

#### Cara 1: Menggunakan Indeks & Concatenation String (Pendekatan Utama)

```javascript
function maskEmail(email) {
  let atIndex = email.indexOf("@");
  let username = email.slice(0, atIndex);
  let domain = email.slice(atIndex);
  
  let firstLetter = username[0];
  let lastLetter = username[username.length - 1];
  let maskedMiddle = "*".repeat(username.length - 2);
  
  let maskedUsername = firstLetter + maskedMiddle + lastLetter;
  return maskedUsername + domain;
}

let email = "apple.pie@example.com";
console.log(maskEmail(email));
```

#### Cara 2: Menggunakan `replace()` dan `slice()` (Pendekatan Alternatif)

```javascript
function maskEmail(email) {
  let atIndex = email.indexOf("@");
  let domain = email.slice(atIndex);
  let username = email.slice(0, atIndex);
  
  let middlePart = username.slice(1, -1);
  let middleMasked = username.replace(middlePart, "*".repeat(middlePart.length));
  
  return middleMasked + domain;
}

let email = "apple.pie@example.com";
console.log(maskEmail(email));
```

### Hasil Output

```text
a*******e@example.com
f**********p@example.com
i**o@test.dev
u**r@domain.org
```

---

## 7. Konverter Celsius ke Fahrenheit (convertCtoF)

Pada latihan ini, saya belajar membuat fungsi matematika untuk mengonversi nilai suhu dari Celsius ke Fahrenheit menggunakan rumus matematika baku.

### Objective & User Stories
1. Membuat fungsi bernama `convertCtoF`.
2. Fungsi menerima satu parameter numerik yang merepresentasikan suhu Celsius.
3. Fungsi mengembalikan angka berupa nilai suhu dalam Fahrenheit.

### Solusi Kode

```javascript
function convertCtoF(celcius) {
  let fahrenheit = celcius * (9 / 5) + 32;
  return fahrenheit;
}

let celcius = -30;
console.log(`Mengonversi nilai celcius ke Fahrenheit dengan nilai celcius sebesar ${celcius} menjadi nilai Fahrenheit sebesar${convertCtoF(celcius)}`);
```

### Hasil Output

```text
Mengonversi nilai celcius ke Fahrenheit dengan nilai celcius sebesar -30 menjadi nilai Fahrenheit sebesar -22
```

---

## 8. Card Counting Assistant (Penghitung Kartu Blackjack)

Pada latihan ini, saya belajar membuat fungsi penghitung kartu (*card counting*) untuk permainan Blackjack. Fungsi ini memperbarui variabel global `count` berdasarkan kartu yang keluar dan mengembalikan rekomendasi keputusan taruhan (`Bet` atau `Hold`).

### Objective & User Stories
1. Deklarasi variabel global `count` dengan `let` dan isi nilai awal `0`.
2. Membuat fungsi `cardCounter` yang menerima satu argumen `card` (angka atau string).
3. Mengubah variabel `count`:
   - Kartu 2, 3, 4, 5, 6: `count` bertambah 1 (`+1`).
   - Kartu 7, 8, 9: `count` tidak berubah.
   - Kartu 10, "J", "Q", "K", "A": `count` berkurang 1 (`-1`).
4. Mengembalikan nilai `count` dan teks `Bet` jika `count > 0`, atau `Hold` jika `count <= 0`, dipisahkan oleh satu spasi.

### Solusi Kode (Pendekatan Utama & Alternatif)

#### Cara 1: Menggunakan Switch Statement (Pendekatan Utama)

```javascript
let count = 0;

function cardCounter(card) {
  switch (card) {
    case 2:
    case 3:
    case 4:
    case 5:
    case 6:
      count++;
      break;
    case 10:
    case "J":
    case "Q":
    case "K":
    case "A":
      count--;
      break;
  }

  let action = "Hold";
  if (count > 0) {
    action = "Bet";
  }

  return count + " " + action;
}
```

#### Cara 2: Menggunakan If-Else & Ternary Operator (Pendekatan Alternatif)

```javascript
let count = 0;

function cardCounter(card) {
  if (typeof card === "number" && card >= 2 && card <= 6) {
    count++;
  } else if (typeof card === "string" || card === 10) {
    count--;
  }

  return `${count}${count > 0 ? "Bet" : "Hold"}`;
}
```

### Hasil Output

```javascript
console.log(cardCounter(2));   // "1 Bet"
console.log(cardCounter(3));   // "2 Bet"
console.log(cardCounter("K")); // "1 Bet"
console.log(cardCounter(10));  // "0 Hold"
console.log(cardCounter("A")); // "-1 Hold"
```

---

## 9. Algoritma Pemotong String (Truncate a String Algorithm)

Pada latihan ini, saya belajar membuat fungsi untuk memotong string jika panjangnya melebihi batas maksimum yang ditentukan, lalu menambahkan akhiran `...` di akhir string yang dipotong.

### Objective & User Stories
1. Membuat fungsi `truncateString` yang menerima dua argumen: sebuah string (`string`) dan sebuah angka (`number`).
2. Jika panjang string lebih besar dari angka batas, potong string sesuai batas tersebut dan tambahkan `...` di akhirnya.
3. Jika panjang string kurang dari atau sama dengan angka batas, kembalikan string asli tanpa perubahan.

### Solusi Kode (Pendekatan Utama & Alternatif)

#### Cara 1: Menggunakan Pengkondisian If-Else (Pendekatan Utama)

```javascript
function truncateString(string, number) {
  if (string.length > number) {
    return string.slice(0, number) + "...";
  } else {
    return string;
  }
}

let result1 = truncateString("A-tisket a-tasket A green and yellow basket", 8),
    result2 = truncateString("Peter Piper picked a peck of pickled peppers", 11),
    result3 = truncateString("A-tisket a-tasket A green and yellow basket", "A-tisket a-tasket A green and yellow basket".length),
    result4 = truncateString("A-tisket a-tasket A green and yellow basket", "A-tisket a-tasket A green and yellow basket".length + 2),
    result5 = truncateString("A-", 1),
    result6 = truncateString("Absolutely Longer", 2);
    
console.log(`${result1} \n${result2} \n${result3} \n${result4} \n${result5} \n${result6}`);

```

#### Cara 2: Menggunakan Ternary Operator (Pendekatan Alternatif)

```javascript
function truncateString(string, number) {
  return string.length > number ? string.slice(0, number) + "..." : string;
}

let result1 = truncateString("A-tisket a-tasket A green and yellow basket", 8),
    result2 = truncateString("Peter Piper picked a peck of pickled peppers", 11),
    result3 = truncateString("A-tisket a-tasket A green and yellow basket", "A-tisket a-tasket A green and yellow basket".length),
    result4 = truncateString("A-tisket a-tasket A green and yellow basket", "A-tisket a-tasket A green and yellow basket".length + 2),
    result5 = truncateString("A-", 1),
    result6 = truncateString("Absolutely Longer", 2);
    
console.log(`${result1} \n${result2} \n${result3} \n${result4} \n${result5} \n${result6}`);

```

### Hasil Output

```text
A-tisket... 
Peter Piper... 
A-tisket a-tasket A green and yellow basket 
A-tisket a-tasket A green and yellow basket 
A... 
Ab...
```

---

## 10. Kalkulator Tahun Kabisat (Leap Year Calculator)

Pada latihan ini, saya belajar membuat fungsi logika untuk menentukan apakah suatu tahun merupakan tahun kabisat (*leap year*) berdasarkan aturan keterbagian tahun 4, 100, dan 400.

### Objective & User Stories
1. Mendefinisikan fungsi `isLeapYear` yang menerima argumen angka berupa tahun.
2. Mendeklarasikan variabel `year` di luar fungsi untuk menyimpan nilai tahun yang diperiksa.
3. Menggunakan kondisi logika:
   - Habis dibagi 4 **dan** tidak habis dibagi 100, **atau**
   - Habis dibagi 400.
4. Mengembalikan string `[year] is a leap year.` jika tahun kabisat, atau `[year] is not a leap year.` jika bukan.
5. Memanggil fungsi `isLeapYear(year)`, menyimpannya ke variabel `result`, dan mencetaknya ke konsol menggunakan `console.log()`.

### Solusi Kode (Pendekatan Utama & Alternatif Ternary)

#### Cara 1: Menggunakan If-Else & Logical Operators (Pendekatan Utama)

```javascript
function isLeapYear(number) {
  if ((number % 4 === 0 && number % 100 !== 0) || (number % 400 === 0)) {
    return `${number} is a leap year.`;
  } else {
    return `${number} is not a leap year.`;
  }
}

let year = 1900, year1 = 2024, year2 = 2000;
let result = isLeapYear(year),
    result1 = isLeapYear(year1),
    result2 = isLeapYear(year2)
console.log(`${result} \n${result1} \n${result2}`);
```

#### Cara 2: Menggunakan Ternary Operator (Pendekatan Alternatif)

```javascript
function isLeapYear(number) {
  const isLeap = (number % 4 === 0 && number % 100 !== 0) || (number % 400 === 0);
  return `${number} is${isLeap ? "a" : "not a"} leap year.`;
}

let year = 1900, year1 = 2024, year2 = 2000;
let result = isLeapYear(year),
    result1 = isLeapYear(year1),
    result2 = isLeapYear(year2)
console.log(`${result} \n${result1} \n${result2}`);
```

### Hasil Output

```text
1900 is not a leap year. 
2024 is a leap year. 
2000 is a leap year.
```

---

## 11. Alat Konfirmasi Akhir String (Confirm the Ending)

Pada latihan ini, saya belajar memeriksa apakah sebuah string diakhiri dengan string target tertentu tanpa menggunakan metode bawaan `.endsWith()`, melainkan memanfaatkan metode pemotongan string `slice()`.

### Objective & User Stories
1. Membuat fungsi `confirmEnding` yang menerima dua parameter: string utama (`str`) dan string target (`target`).
2. Mengembalikan nilai boolean murni `true` jika `str` diakhiri dengan `target`, dan `false` jika tidak.
3. Dilarang menggunakan metode `.endsWith()`, sebagai gantinya menggunakan metode `slice(-target.length)`.

### Solusi Kode (Pendekatan Standar & Ringkas)

#### Pendekatan Ringkas & Efisien (Pro-Code)

```javascript
function confirmEnding(str, target) {
  console.log(`is "${str}" ending with "${target}"?`);
  return str.slice(- target.length) === target? true:false;
}
let newLine = "\n"
console.log(confirmEnding("Bastian", "n") + newLine);
console.log(confirmEnding("Congratulation", "on") + newLine);
console.log(confirmEnding("Connor", "n") + newLine);
console.log(confirmEnding("Walking on water and developing software from a specification are easy if both are frozen", "specification") + newLine);
console.log(confirmEnding("He has to give me a new name", "name") + newLine);
console.log(confirmEnding("Open sesame", "same") + newLine);
console.log(confirmEnding("Open sesame", "game") + newLine);
console.log(confirmEnding("If you want to save our world, you must hurry. We don't know how much longer we can withstand the nothing", "mountain") + newLine);
console.log(confirmEnding("Abstraction", "action") + newLine);
```

### Hasil Output

```text
is "Bastian" ending with "n"?
true

is "Congratulation" ending with "on"?
true

is "Connor" ending with "n"?
false

is "Walking on water and developing software from a specification are easy if both are frozen" ending with "specification"?
false

is "He has to give me a new name" ending with "name"?
true

is "Open sesame" ending with "same"?
true

is "Open sesame" ending with "game"?
false

is "If you want to save our world, you must hurry. We don't know how much longer we can withstand the nothing" ending with "mountain"?
false

is "Abstraction" ending with "action"?
true

```

---

## 12. Program Pemilih Makan Siang (Lunch Picker) 

Pada latihan ini, saya belajar mengelola array dalam JavaScript dengan manipulasi data seperti menambah item di depan/belakang (unshift, push), menghapus item dari depan/belakang (shift, pop), memilih item secara acak (Math.random), dan menampilkan daftar menu yang tersambung (join).

### Objective & User Stories
1. Mendeklarasikan variabel lunches berisi array kosong.
2. Membuat fungsi addLunchToEnd(arr, item) untuk menambahkan item ke akhir array dan mencetak notifikasi.
3. Membuat fungsi addLunchToStart(arr, item) untuk menambahkan item ke awal array dan mencetak notifikasi.
4. Membuat fungsi removeLastLunch(arr) untuk menghapus elemen terakhir dari array dan mencetak notifikasi (dengan validasi jika array kosong).
5. Membuat fungsi removeFirstLunch(arr) untuk menghapus elemen pertama dari array dan mencetak notifikasi (dengan validasi jika array kosong).
6. Membuat fungsi getRandomLunch(arr) untuk memilih elemen secara acak tanpa mengubah isi array asli.
7. Membuat fungsi showLunchMenu(arr) untuk mencetak seluruh item dalam menu dipisahkan oleh koma.

### Solusi Kode (Pendekatan Standar & Ringkas)
```javascript
const lunches = [];

function addLunchToEnd(arr, item) {
  arr.push(item);
  console.log(`${item} added to the end of the lunch menu.`);
  return arr;
}

function addLunchToStart(arr, item) {
  arr.unshift(item);
  console.log(`${item} added to the start of the lunch menu.`);
  return arr;
}

function removeLastLunch(arr) {
  if (arr.length === 0) {
    console.log("No lunches to remove.");
  } else {
    const removedItem = arr.pop();
    console.log(`${removedItem} removed from the end of the lunch menu.`);
  }
  return arr;
}

function removeFirstLunch(arr) {
  if (arr.length === 0) {
    console.log("No lunches to remove.");
  } else {
    const removedItem = arr.shift();
    console.log(`${removedItem} removed from the start of the lunch menu.`);
  }
  return arr;
}

function getRandomLunch(arr) {
  if (arr.length === 0) {
    console.log("No lunches available.");
  } else {
    const randomIndex = Math.floor(Math.random() * arr.length);
    const randomItem = arr[randomIndex];
    console.log(`Randomly selected lunch: ${randomItem}`);
  }
}

function showLunchMenu(arr) {
  if (arr.length === 0) {
    console.log("The menu is empty.");
  } else {
    console.log(`Menu items: ${arr.join(", ")}`);
  }
}

console.log(removeLastLunch(lunches));
console.log(removeFirstLunch(lunches));
console.log(getRandomLunch(lunches));
console.log(showLunchMenu(lunches));
console.log(addLunchToEnd(lunches, "Tacos"));
console.log(addLunchToEnd(["Pizza", "Tacos"], "Burger"));
console.log(addLunchToStart(lunches, "Sushi"));
console.log(addLunchToStart(["Burger", "Sushi"], "Pizza"));
console.log(removeLastLunch(["Stew", "Soup", "Toast"]));
console.log(removeLastLunch(["Sushi", "Pizza", "Noodles"]));
console.log(removeFirstLunch(["Salad", "Eggs", "Cheese"]));
console.log(removeFirstLunch(["Sushi", "Pizza", "Burger"]));
console.log(getRandomLunch(lunches));
console.log(showLunchMenu(["Greens", "Corns", "Beans"]));
console.log(showLunchMenu(["Pizza", "Burger", "Fries", "Salad"]));
```

### Hasil Output

```text
No lunches to remove.
[]
No lunches to remove.
[]
No lunches available.
undefined
The menu is empty.
undefined
Tacos added to the end of the lunch menu.
[ 'Tacos' ]
Burger added to the end of the lunch menu.
[ 'Pizza', 'Tacos', 'Burger' ]
Sushi added to the start of the lunch menu.
[ 'Sushi', 'Tacos' ]
Pizza added to the start of the lunch menu.
[ 'Pizza', 'Burger', 'Sushi' ]
Toast removed from the end of the lunch menu.
[ 'Stew', 'Soup' ]
Noodles removed from the end of the lunch menu.
[ 'Sushi', 'Pizza' ]
Salad removed from the start of the lunch menu.
[ 'Eggs', 'Cheese' ]
Sushi removed from the start of the lunch menu.
[ 'Pizza', 'Burger' ]
Randomly selected lunch: Sushi
undefined
Menu items: Greens, Corns, Beans
undefined
Menu items: Pizza, Burger, Fries, Salad
undefined

```

---

## 13. Penerjemah Skor Golf (Golf Score Translator)
Pada latihan ini, saya belajar menggunakan struktur pengkondisian rantai if...else if...else untuk menerjemahkan nilai par dan jumlah pukulan (strokes) pada permainan golf menjadi julukan/sebutan skor yang sesuai.

### Objective & User Stories
1. Membuat fungsi bernama golfScore yang menerima dua argumen numerik (par dan strokes).
2. Mengembalikan string "Hole-in-one!" jika strokes === 1.
3. Mengembalikan string "Eagle" jika strokes <= par - 2.
4. Mengembalikan string "Birdie" jika strokes === par - 1.
5. Mengembalikan string "Par" jika strokes === par.
6. Mengembalikan string "Bogey" jika strokes === par + 1.
7. Mengembalikan string "Double Bogey" jika strokes === par + 2.
8. Mengembalikan string "Go Home!" jika strokes >= par + 3.

### Solusi Kode
```javascript

const names = ["Hole-in-one!", "Eagle", "Birdie", "Par", "Bogey", "Double Bogey", "Go Home!"];

function golfScore(par, strokes) {
  if (strokes === 1) {
    return "Hole-in-one!";
  } else if (strokes <= par - 2) {
    return "Eagle";
  } else if (strokes === par - 1) {
    return "Birdie";
  } else if (strokes === par) {
    return "Par";
  } else if (strokes === par + 1) {
    return "Bogey";
  } else if (strokes === par + 2) {
    return "Double Bogey";
  } else if (strokes >= par + 3) {
    return "Go Home!";
  }
}

console.log(golfScore(1, 1));
console.log(golfScore(3, 1));
console.log(golfScore(4, 1));
console.log(golfScore(5, 1));
console.log(golfScore(4, 2));
console.log(golfScore(5, 2));
console.log(golfScore(3, 2));
console.log(golfScore(4, 3));
console.log(golfScore(5, 4));
console.log(golfScore(3, 3));
console.log(golfScore(4, 4));
console.log(golfScore(4, 5));
console.log(golfScore(3, 5));
console.log(golfScore(5, 9));

```

### Hasil Output

```text
Hole-in-one!
Hole-in-one!
Hole-in-one!
Hole-in-one!
Eagle
Eagle
Birdie
Birdie
Birdie
Par
Par
Bogey
Double Bogey
Go Home!
```

---
## 14. Membangun Validator Manifest Kargo (Build a Cargo Manifest Validator)
Pada latihan ini, saya belajar mengimplementasikan fungsi-fungsi JavaScript untuk melakukan normalisasi, validasi, dan pemrosesan objek manifes kargo tanpa mengubah (*mutate*) objek aslinya.

### Objective & User Stories
1. Membuat fungsi `normalizeUnits(manifest)` yang mengembalikan objek baru dengan berat (`weight`) yang dikonversi ke kilogram (1 lb = 0.45 kg) dan `unit` diatur ke `"kg"`.
2. Membuat fungsi `validateManifest(manifest)` yang menguji setiap properti (`containerId`, `destination`, `weight`, `unit`, `hazmat`). Mengembalikan `{}` jika valid, atau objek yang berisi status `"Missing"` / `"Invalid"` untuk properti yang tidak memenuhi kriteria.
3. Membuat fungsi `processManifest(manifest)` yang memeriksa hasil `validateManifest()`:
   - Jika valid: mencetak `"Validation success: ${containerId}"` dan `"Total weight: ${weight} kg"` (menggunakan `normalizeUnits()`).
   - Jika tidak valid: mencetak `"Validation error: ${containerId}"` dan mencetak objek kesalahan dari `validateManifest()`.
4. Menggunakan dua kali pemanggilan `console.log()` pada masing-masing kasus di `processManifest()`.
5. Tidak menggunakan `const` saat mendeklarasikan fungsi agar dapat ditetapkan kembali (*reassign*) oleh pengujian.

### Solusi Kode
```javascript
function normalizeUnits(manifest) {
  let copy = {
    containerId: manifest.containerId,
    destination: manifest.destination,
    weight: manifest.weight,
    unit: manifest.unit,
    hazmat: manifest.hazmat
  }
  if (copy.unit === "lb") {
    copy.unit = "kg";
    copy.weight = copy.weight * 0.45;
  }
  return copy;
}

function validateManifest(manifest) {
  let validate = {};

  if (manifest.containerId === undefined) {
    validate.containerId = "Missing";
  } else if 
  (
    typeof manifest.containerId !== "number" ||
    manifest.containerId <= 0 ||
    manifest.containerId % 1 !== 0
  ) {
    validate.containerId = "Invalid";
  }

  if (manifest.destination === undefined) {
    validate.destination = "Missing";
  } else if 
  (
    typeof manifest.destination !== "string" ||
    manifest.destination.trim() === ""
  ) {
    validate.destination = "Invalid";
  }

  if (manifest.weight === undefined) {
    validate.weight = "Missing";
  } else if 
  (
    typeof manifest.weight !== "number" ||
    manifest.weight <= 0 ||
    manifest.weight !== manifest.weight
  ) {
    validate.weight = "Invalid";
  }

  if (manifest.unit === undefined) {
    validate.unit = "Missing";
  } else if 
  (
    manifest.unit !== "kg" && manifest.unit !== "lb"
  ) {
    validate.unit = "Invalid";
  }

  if (manifest.hazmat === undefined) {
    validate.hazmat = "Missing";
  } else if (typeof manifest.hazmat !== "boolean") {
    validate.hazmat = "Invalid";
  }
  return validate;
}

function processManifest(manifest) {
  let errors = validateManifest(manifest);
  let countError = Object.keys(errors).length;

  if (countError === 0) {
    console.log(`Validation success! 
    containerId: ${manifest.containerId}
    destination: ${manifest.destination}
    weight: ${manifest.weight} ${manifest.unit}`);
    let convert = normalizeUnits(manifest);
    console.log(`Total weight: ${convert.weight} kg
    `);
  } else {
    console.log(`Validation error! 
    containerId: ${manifest.containerId}
    destination: ${manifest.destination}
    weight: ${manifest.weight} ${manifest.unit}`);
    console.log(errors);
    console.log("")
  }
}

let check1 = processManifest(
  {
    containerId: 68,
    destination: "Salinas",
    weight: 45.45,
    unit: "kg",
    hazmat: true
  });

let check2 = processManifest(
  {
    destination: "Salinas",
    weight: 45.45,
    unit: "kg",
    hazmat: true
  });

let check3 = processManifest(
  {
    containerId: 68,
    destination: "Salinas",
    weight: 45.45,
    unit: "lb",
    hazmat: true
  });
```

### Hasil Output

```text
Validation success! 
    containerId: 68
    destination: Salinas
    weight: 45.45 kg
Total weight: 45.45 kg
    
Validation error! 
    containerId: undefined
    destination: Salinas
    weight: 45.45 kg
{ containerId: 'Missing' }

Validation success! 
    containerId: 68
    destination: Salinas
    weight: 45.45 lb
Total weight: 20.4525 kg
```
---

## 15. Buat Permainan Kuis (Build a Quiz Game)
Pada latihan ini, saya belajar membangun logika permainan kuis sederhana menggunakan JavaScript dengan memanfaatkan manipulasi Array, Objek, serta pemilihan acak (*random choice generation*).

### Objective & User Stories
1. Membuat *array* `questions` yang berisi minimal 5 objek pertanyaan (masing-masing memiliki kunci `category`, `question`, `choices`, dan `answer`).
2. Kunci `choices` harus berisi *array* 3 *string*, dan nilai `answer` wajib ada di dalam *array* `choices`.
3. Membuat fungsi `getRandomQuestion(questionsArr)` untuk mengambil satu objek pertanyaan secara acak.
4. Membuat fungsi `getRandomComputerChoice(choicesArr)` untuk mengambil satu pilihan jawaban acak.
5. Membuat fungsi `getResults(questionsObject, computerChoice)` untuk mengevaluasi jawaban komputer dan mengembalikan pesan hasil.

### Solusi Kode
```javascript
const questions = [
  {
    category: "Math",
    question: "2 x 16 = ?",
    choices: ["32", "30", "22"],
    answer: "32"
  },
  {
    category: "History",
    question: "When did Indonesia gain independence?",
    choices: [
      "August 16, 1945",
      "August 17, 1945",
      "Auguts 17, 1950"
    ],
    answer: "August 17, 1945"
  },
  {
    category: "Biology",
    question: 'Which cell organelle is known as the "powerhouse of the cell"?',
    choices: [
      "Nucleus", "Mitochondria", "Ribosome"
    ],
    answer: "Mitochondria"
  },
  {
    category: "Chemistry",
    question: "What is the chemical symbol for Water?",
    choices: [
      "CO₂", "H₂O", "NaCl"
    ],
    answer: "H₂O"
  },
  {
    category: "Physics",
    question: "What is the standard International System of Units (SI) unit for measuring force?",
    choices: [
      "Joule", "Newton", "Watt"
    ],
    answer: "Newton"
  }
];

function getRandomQuestion(questionsArr) {
  const randomIndex = Math.floor(Math.random() * questionsArr.length);
  return questionsArr[randomIndex];
}

function getRandomComputerChoice(choicesArr) {
  const randomIndex = Math.floor(Math.random() * choicesArr.length);
  return choicesArr[randomIndex];
}

function getResults(questionsObject, computerChoice) {
  if (computerChoice === questionsObject.answer) {
    return `The computer's choice is correct!`;
  } else {
    return `The computer's choice is wrong. The correct answer is: ${questionsObject.answer}`;
  }
}

const randomQuestion = getRandomQuestion(questions);
let choicesFormatted = randomQuestion.choices.join("\n");

console.log(`Category: ${randomQuestion.category}`);
console.log(`Question: ${randomQuestion.question}`);
console.log("Choices:\n" + choicesFormatted);

const computerChoices = getRandomComputerChoice(randomQuestion.choices);
console.log("\nComputer's answer: " + computerChoices + "\n");

const result = getResults(randomQuestion, computerChoices);
console.log(result);
```

### Hasil Output

```text
Kategori: Biologi
Pertanyaan: Organel sel manakah yang dikenal sebagai "pembangkit energi sel"?
Pilihan:
Inti
Mitokondria
Ribosom

Jawaban komputer: Inti

Pilihan komputer salah. Jawaban yang benar adalah: Mitokondria
```
---

## 16.
### Objective & User Stories
### Solusi Kode
```javascript
```

### Hasil Output

```text
```
---
