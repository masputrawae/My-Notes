---
title: Cara Install PHP di Ubuntu
description:
excerpt:
date: 2024-11-19
categories:
tags:
last_modified_at: 2024-11-19
author:
---
### Langkah-langkah Install PHP di Ubuntu:

#### Langkah 1: Install PHP
Ketikkan perintah ini di terminal untuk install PHP:
```bash
sudo apt install libapache2-mod-php php-mysql php-common
```
Ini akan menginstall PHP sekaligus modulnya untuk Apache biar mereka bisa saling terhubung.

#### Langkah 2: Cek Versi PHP
Pastikan PHP berhasil terinstall dengan cek versinya:
```bash
php -v
```
Kalau PHP sudah terinstall dengan benar, kamu akan melihat versi PHP yang aktif (misalnya, PHP 7.x atau PHP 8.x).

#### Langkah 3: Konfigurasi Apache untuk Utamakan PHP
Apache biasanya menampilkan file `index.html` lebih dulu dari file PHP. Untuk memastikan file PHP yang diutamakan, kita bisa edit sedikit file konfigurasi:
```bash
sudo nano /etc/apache2/mods-enabled/dir.conf
```

Cari baris seperti ini:
```
DirectoryIndex index.html index.php
```
Lalu, ubah agar `index.php` berada di depan `index.html`:
```
DirectoryIndex index.php index.html
```

Simpan perubahan (di Nano, tekan `CTRL + O` lalu `Enter` untuk simpan, dan `CTRL + X` untuk keluar).

#### Langkah 4: Restart Apache
Supaya perubahan konfigurasi diterapkan, restart Apache:
```bash
sudo systemctl restart apache2
```

#### Langkah 5: Tes PHP
Buat file PHP pertama kamu untuk cek apakah instalasi berhasil:
1. Buat file baru bernama `info.php` di folder root server (`/var/www/html/`):
   ```bash
   sudo nano /var/www/html/info.php
   ```
2. Tambahkan kode PHP berikut:
   ```php
   <?php
   phpinfo();
   ?>
   ```
3. Simpan file, lalu akses di browser dengan mengetik:
   ```
   http://localhost/info.php
   ```
Kalau halaman `phpinfo()` muncul dengan informasi tentang PHP, berarti instalasi kamu berhasil! 🎉 
Gimana, lancar?
Yes, bagus banget kalau sudah jalan! 🎉 Nah, file `info.php` ini sebenarnya hanya buat cek instalasi PHP aja, jadi setelah semuanya beres, sebaiknya dihapus supaya nggak ada informasi sistem yang bisa diakses orang lain secara nggak sengaja. 

Untuk hapus file `info.php`, tinggal pakai perintah ini di terminal:
```bash
sudo rm /var/www/html/info.php
```