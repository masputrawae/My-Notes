---
title: Javascript | Menyembunyikan dan Menampilkan Elemen
description: Cara sederhana untuk menyembunyikan dan menampilkan elemen menggunakan JavaScript di HTML
excerpt: Panduan untuk membuat tombol yang dapat menyembunyikan atau menampilkan elemen di halaman web menggunakan JavaScript.
date: 2024-11-26
categories:
  - JavaScript
  - Belajar
  - Cheat Sheet
tags:
  - catatan_belajar
  - cheat-sheet
  - javascript
  - html
  - css
  - web_development
  - belajar_javascript
last_modified_at: 2024-11-26
author: Putra Jaya
---
## Menyembunyikan dan Menampilkan Elemen dengan JavaScript

Pada catatan ini, kita akan membuat tombol untuk menyembunyikan atau menampilkan sebuah elemen HTML menggunakan JavaScript. Misalnya, kita akan membuat konten tersembunyi yang hanya muncul setelah tombol diklik.

### Struktur HTML

```html
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Sembunyikan dan Tampilkan</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>

  <!-- Tombol untuk menampilkan atau menyembunyikan elemen -->
  <button id="tampilkan">Tampilkan Elemen</button>
  
  <!-- Elemen konten yang akan disembunyikan atau ditampilkan -->
  <div id="konten" style="display: none;">
    <p>Ini adalah konten yang bisa disembunyikan atau ditampilkan.</p>
  </div>

  <script src="script.js"></script>
</body>
</html>

Kode JavaScript
```
### Kode Javascript 
```javascript
document.getElementById('tampilkan').addEventListener('click', function() {
  const konten = document.getElementById('konten');
  
  // Cek apakah konten sedang tersembunyi
  if (konten.style.display === 'none') {
    konten.style.display = 'block';  // Menampilkan konten
  } else {
    konten.style.display = 'none';   // Menyembunyikan konten
  }
});
```
Penjelasan Kode

1. HTML: Tombol dengan id="tampilkan" digunakan untuk memicu event klik. Konten yang akan disembunyikan atau ditampilkan dibungkus dalam elemen <div> dengan id="konten" dan memiliki gaya display: none; agar tersembunyi secara default.


2. JavaScript: Ketika tombol diklik, kita mendapatkan elemen dengan id="konten" dan mengecek nilai display-nya. Jika display bernilai none, maka konten akan ditampilkan dengan mengubahnya menjadi block. Sebaliknya, jika konten sudah ditampilkan, maka akan disembunyikan lagi.



Semoga catatan ini dapat membantu Anda memahami cara menyembunyikan dan menampilkan elemen menggunakan JavaScript!