---
title: Cara Install Apache di Ubuntu
description: Panduan langkah demi langkah untuk menginstall Apache di Ubuntu, mulai dari update sistem hingga cek status server.
excerpt: Panduan lengkap cara install Apache di Ubuntu untuk server lokal.
date: 2024-11-19
categories:
  - Server
  - Linux
  - Panduan
tags:
  - Apache
  - Ubuntu
  - Linux
  - Web Server
  - Installasi
last_modified_at: 2024-11-19
author: Putra Jaya
---
# Cara Install Apache di Ubuntu
Sebenarnya aku install pada tanggal 2024-11-18, tapi baru sempat menulis pada tanggal 2024-11-19, telat sehari ngak masalah lah ya, hehe.
Langsung aja tanpa banyak basa-basi:

## Langkah 1: Update Package Manager
Kita mulai dengan memastikan semua paket di sistemmu up-to-date:
```bash
sudo apt update && sudo apt upgrade
```

## Langkah 2: Install Apache
Install Apache dengan perintah berikut:
```bash
sudo apt install apache2
```

Setelah selesai, Apache seharusnya langsung berjalan otomatis.

## Langkah 3: Cek Status Apache
Kamu bisa cek apakah Apache sudah aktif dengan perintah ini:
```bash
sudo systemctl status apache2
```
Kalau sudah jalan, kamu akan lihat statusnya “active (running)”. harusnya seperti di bawah ini:
```bash
└─$ sudo systemctl status apache2
● apache2.service - The Apache HTTP Server
     Loaded: loaded (/usr/lib/systemd/system/apache2.service; enabled; preset: >
     Active: active (running) since Mon 2024-11-18 08:02:39 WIB; 9min ago
       Docs: https://httpd.apache.org/docs/2.4/
   Main PID: 8648 (apache2)
      Tasks: 55 (limit: 18806)
     Memory: 5.9M (peak: 6.8M)
        CPU: 50ms
     CGroup: /system.slice/apache2.service
             ├─8648 /usr/sbin/apache2 -k start
             ├─8650 /usr/sbin/apache2 -k start
             └─8651 /usr/sbin/apache2 -k start
```

## Langkah 4: Coba Akses di Browser
Sekarang, buka browser dan ketik:
```
http://localhost/
```
Kalau instalasi berhasil, kamu akan melihat halaman “Apache2 Ubuntu Default Page”. Artinya, Apache sudah berjalan dengan baik!

## Langkah 5: Konfigurasi Firewall (Opsional)
Kalau kamu pakai firewall, kamu bisa buka akses untuk Apache dengan perintah:
```bash
sudo ufw allow 'Apache'
```

### Selesai!
Apache sudah berhasil terinstall dan berjalan di sistemmu. Gimana, sampai sini lancar? 😊