A simple HTML/JS/CSS starter template# Kalkulator-Umur


Penjelasan setiap kode 

// Get the input element for the user's birth date
let userInput = document.getElementById("date");

// Set the maximum date for the input element to today's date
userInput.max = new Date().toISOString().split("T")[0];

// Get the element where the result will be displayed
let result = document.getElementById("result");

// Function to calculate the user's age
function calculateAge() {
    // Create a Date object from the user's input
    let birthDate = new Date(userInput.value);

    // Get the day, month, and year of the user's birth date
    let d1 = birthDate.getDate();
    let m1 = birthDate.getMonth() + 1;
    let y1 = birthDate.getFullYear();

    // Create a Date object for today's date
    let today = new Date();

    // Get the day, month, and year of today's date
    let d2 = today.getDate();
    let m2 = today.getMonth() + 1;
    let y2 = today.getFullYear();

    // Initialize variables to store the difference in years, months, and days
    let d3, m3, y3;

    // Calculate the difference in years
    y3 = y2 - y1;

    // Calculate the difference in months
    if (m2 >= m1) {
        m3 = m2 - m1;
    } else {
        y3--;
        m3 = 12 + m2 - m1;
    }

    // Calculate the difference in days
    if (d2 >= d1) {
        d3 = d2 - d1;
    } else {
        m3--;
        d3 = getDaysInMonth(y1, m1) + d2 - d1;
    }

    // If the difference in months is less than 0, adjust the year and month values
    if (m3 < 0) {
        m3 = 11;
        y3--;
    }

    // Display the result
    result.innerHTML = `Kamu berumur <span> ${y3} </span> tahun,<span> ${m3} </span> bulan, dan <span> ${d3} </span


Kode yang Anda berikan adalah fungsi JavaScript yang menghitung usia seseorang berdasarkan tanggal lahir mereka.

Berikut adalah penjelasan dari apa yang dilakukan kode tersebut:

Mendapatkan Elemen Input:
let userInput = document.getElementById("date");
javascript (auto)


Baris ini memilih elemen HTML dengan ID "date" dan menyimpannya dalam variabel userInput. Elemen ini diasumsikan sebagai bidang input tempat pengguna memasukkan tanggal lahir mereka.

Mengatur Tanggal Maksimum:
userInput.max = new Date().toISOString().split("T")[0];
cpp (auto)


Baris ini menetapkan tanggal maksimum untuk bidang input hingga tanggal hari ini. Hal ini dilakukan dengan membuat objek Date baru untuk tanggal hari ini, mengonversinya menjadi string dalam format ISO, membagi string pada karakter "T", dan kemudian menetapkan elemen pertama (yang mewakili tanggal) ke properti max dari elemen userInput.

Mendapatkan Elemen Hasil:
let result = document.getElementById("result");
javascript (auto)


Baris ini memilih elemen HTML dengan ID "result" dan menyimpannya dalam variabel result. Elemen ini diasumsikan sebagai tempat usia yang dihitung akan ditampilkan.

Fungsi Menghitung Usia:
function calculateAge() {
  // ...
}
javascript (auto)


Ini adalah fungsi utama yang menghitung usia pengguna. Diasumsikan dipanggil ketika peristiwa tertentu terjadi, seperti ketika pengguna mengklik tombol.

Mendapatkan Tanggal Lahir Pengguna:
let birthDate = new Date(userInput.value);
javascript (auto)


Baris ini membuat objek Date baru dari nilai elemen userInput, yang mewakili tanggal lahir pengguna.

Mengekstrak Komponen Tanggal:
let d1 = birthDate.getDate();
let m1 = birthDate.getMonth() + 1;
let y1 = birthDate.getFullYear();
javascript (auto)


Baris-baris ini mengekstrak komponen hari, bulan, dan tahun dari objek birthDate. Perhatikan bahwa nilai bulan ditambah 1 karena bulan JavaScript berbasis nol (Januari adalah 0, Desember adalah 11).

Mendapatkan Tanggal Hari Ini:
let today = new Date();
javascript (auto)


Baris ini membuat objek Date baru untuk tanggal hari ini.