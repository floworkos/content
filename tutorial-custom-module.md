---
title: "Panduan Lengkap: Membuat Custom Module (UDF) di Flowork OS"
date: "2026-03-08"
author: "SYSTEM_ADMIN"
cover: "/images/cover.webp"
keywords: ["flow designer", "custom module", "javascript", "automation", "edge compute", "tutorial"]
version: "1.0"
---

Selamat datang di dokumentasi resmi **Flowork Neural Builder**. Di era komputasi Edge modern, Flowork OS memungkinkan Anda untuk tidak hanya menggunakan modul bawaan (sistem), tetapi juga menciptakan **Custom Module** Anda sendiri menggunakan JavaScript murni. 

Fitur ini menggunakan teknik *On-The-Fly Compiler* di dalam browser, mengubah Flowork dari sekadar *Visual Builder* menjadi *Platform as a Service (PaaS)* seutuhnya tanpa perlu menyentuh server backend.

Berikut adalah panduan langkah demi langkah merakit logika Anda sendiri.

## Langkah 1: Mengakses Custom Module Builder

Untuk mulai membuat modul:
1. Buka Workspace Flow Designer Anda.
2. Perhatikan menu navigasi di pojok kanan atas.
3. Klik tombol **"🛠 Build Module"**.
4. Sebuah pop-up (Modal) akan muncul. Di sinilah Anda akan merancang identitas dan logika modul Anda.

---

## Langkah 2: Mengisi Metadata Modul

Bagian pertama dari form adalah identitas visual modul yang akan muncul di *Sidebar* kiri:

* **Module Name (Display):** Berikan nama yang jelas, misalnya `Kalkulator Pajak` atau `Auto Formatter`.
* **Module Icon (Emoji):** Masukkan satu atau dua karakter emoji untuk memudahkan identifikasi visual (contoh: 🧮 atau 📝).
* **Description:** Deskripsikan secara singkat fungsi modul ini. Ini sangat membantu jika Anda berencana membagikan (Share) workflow ini ke orang lain.

---

## Langkah 3: Mendefinisikan Parameters Schema (JSON)

Parameter UI adalah kolom input yang akan muncul di panel sebelah kanan (Properties) ketika modul Anda di-klik di atas kanvas. Flowork menggunakan skema **JSON Array** untuk me-render form secara otomatis.

Berikut adalah contoh konfigurasi parameter untuk membuat modul Kalkulator:

```json
[
  {
    "name": "angka1",
    "displayName": "Angka Pertama",
    "type": "string",
    "default": "0"
  },
  {
    "name": "angka2",
    "displayName": "Angka Kedua",
    "type": "string",
    "default": "0"
  },
  {
    "name": "operasi",
    "displayName": "Pilih Operasi Logika",
    "type": "options",
    "options": ["tambah", "kurang", "kali", "bagi"],
    "default": "tambah"
  }
]