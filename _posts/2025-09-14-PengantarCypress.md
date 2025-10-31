---
layout: post
date: 2025-09-14
author: "Kelompok 8 - Sistem Informasi 2023"
title: "Pengantar Cypress: Framework E2E Testing Modern"
categories: [Software Development, Quality Assurance, Automation]
description: "Sebuah panduan pengantar Cypress, framework end-to-end testing modern, mencakup keunggulan, setup, perintah dasar, dan studi kasus pengujian."
tags: [Cypress, Automation Testing, E2E Testing, QA, JavaScript, Web Testing, Node.js]
image: /assets/img/pengantar-cypress.png
---

# **Pengantar Cypress**

Cypress adalah sebuah *framework* pengujian *end-to-end* (E2E) modern yang dirancang dari awal untuk mengatasi tantangan pengujian aplikasi web terbaru. Alat ini sangat populer untuk memvalidasi fungsionalitas aplikasi yang dibangun dengan *framework* JavaScript dinamis seperti React, Vue, dan Angular.

Dalam piramida pengujian, fokus utama Cypress adalah pada level **End-to-End**. Ini berarti Cypress mensimulasikan alur kerja pengguna secara lengkap, dari awal hingga akhir (misalnya, mengunjungi situs, login, menambahkan barang ke keranjang, lalu *checkout*). Namun, arsitekturnya yang fleksibel juga membuatnya sangat mumpuni untuk **Integration Testing** dan **Component Testing**.

> **Tujuan Utama:** Menyediakan platform pengujian yang cepat, andal, dan *developer-friendly* untuk memvalidasi aplikasi web modern dari perspektif pengguna akhir.

---

## **Keunggulan Cypress (Mengapa Berbeda?)**

Cypress dirancang untuk mengatasi banyak "penderitaan" yang biasa dialami dengan *tools* pengujian generasi sebelumnya (seperti Selenium). Keunggulannya terletak pada arsitektur uniknya:

* **Arsitektur Modern (In-Browser)**
    Berbeda dengan Selenium yang beroperasi sebagai *server* eksternal dan mengirim perintah ke *browser* melalui jaringan (JSON Wire Protocol), Cypress beroperasi **langsung di dalam browser**. Ia berjalan pada *run-loop* yang sama dengan aplikasi Anda. Ini memberinya akses *native* ke semua objek, *window*, DOM, dan *event* aplikasi, menghasilkan eksekusi yang lebih cepat dan tes yang jauh lebih stabil.

* **Test Runner Interaktif**
    Ini adalah fitur andalan Cypress. Saat Anda menjalankan `npx cypress open`, sebuah aplikasi *desktop* akan terbuka. Di sana, Anda bisa melihat daftar *file* tes Anda. Saat Anda menjalankan tes, Anda akan melihat dua panel: di satu sisi adalah aplikasi Anda yang sedang diuji, dan di sisi lain adalah log perintah visual. Anda bisa mengklik perintah mana pun di log untuk melihat *snapshot* aplikasi pada saat itu.

* **Time Travel (Perjalanan Waktu)**
    Terkait erat dengan Test Runner, fitur "Time Travel" adalah berkah untuk *debugging*. Jika sebuah tes gagal, Anda tidak perlu menebak-nebak. Anda cukup mengarahkan kursor ke setiap langkah perintah di log dan melihat DOM "kembali ke masa lalu". Anda bisa melihat *snapshot* **sebelum** dan **sesudah** sebuah aksi, memudahkan untuk mengidentifikasi mengapa sebuah elemen tidak ditemukan atau mengapa *assertion* gagal.

* **Automatic Waits (Menunggu Otomatis)**
    Masalah terbesar dalam *automation testing* adalah *flaky tests*—tes yang terkadang lulus dan terkadang gagal tanpa alasan jelas. Ini biasanya terjadi karena skrip mencoba berinteraksi dengan elemen sebelum elemen itu selesai dimuat. Cypress secara cerdas **menunggu secara otomatis** hingga elemen yang Anda perintahkan menjadi tersedia di DOM dan dapat diinteraksi. Anda tidak perlu lagi menulis `wait`, `sleep`, atau `waitForElement` secara manual.

---

## **Setup dan Instalasi**

Memulai proyek dengan Cypress sangatlah cepat. Prasyarat utamanya hanyalah memiliki **Node.js** terinstal di komputer Anda.

1.  **Inisialisasi Proyek Node.js**
    Jika Anda memulai dari folder kosong, buat file `package.json`:
    ```bash
    npm init -y
    ```

2.  **Instal Cypress**
    Instal Cypress sebagai *dev dependency* (hanya dibutuhkan untuk pengembangan):
    ```bash
    npm install cypress --save-dev
    ```

3.  **Buka Cypress Test Runner**
    Perintah ini adalah cara Anda bekerja dengan Cypress selama pengembangan.
    ```bash
    npx cypress open
    ```
    Saat pertama kali dijalankan, Cypress akan mengonfigurasi proyek Anda dan membuat struktur folder yang disarankan, termasuk `cypress/e2e` di mana Anda akan menyimpan semua *file* tes (yang berekstensi `.cy.js`).

4.  **Jalankan Tes (Mode Headless)**
    Untuk menjalankan tes di server CI/CD atau dari terminal tanpa membuka *browser* visual:
    ```bash
    npx cypress run --browser chrome
    ```

---

## **Perintah Dasar & Assertion**

Sintaks Cypress sangat intuitif. Hampir semua perintah diawali dengan `cy` dan dapat "dirantai" (*chainable*).

| Perintah | Deskripsi |
| :--- | :--- |
| **`cy.visit('URL')`** | Membuka (mengunjungi) halaman web target di *browser*. |
| **`cy.get('selector')`** | Mendapatkan satu atau lebih elemen DOM berdasarkan *selector* (CSS, ID, class, dll). |
| **`cy.contains('text')`** | Mencari elemen berdasarkan teks yang terlihat oleh pengguna. |
| **`cy.click()`** | Melakukan aksi klik pada elemen yang telah dipilih. |
| **`cy.type('text')`** | Mengetikkan serangkaian teks ke dalam sebuah *input field*. |
| **`cy.url()`** | Mendapatkan URL yang sedang aktif di *browser*. |
| **`.should('assertion')`** | Ini adalah *assertion*. Perintah ini "dirantai" setelah `cy.get()` atau `cy.url()` untuk memverifikasi sebuah kondisi. Contoh: `.should('be.visible')` atau `.should('have.text', 'Selamat Datang')`. |

---

## **Studi Kasus: Fungsionalitas Login (SauceDemo)**

Berikut adalah contoh *test case* untuk memvalidasi skenario login di situs `saucedemo.com`.

| ID | Skenario Tes | Langkah-langkah (Steps) | Hasil yang Diharapkan (Expected Result) |
| :--- | :--- | :--- | :--- |
| **TC01** | Login dengan kredensial valid | 1. Buka halaman login.<br>2. Masukkan username: `standard_user`<br>3. Masukkan password: `secret_sauce`<br>4. Klik tombol login. | Pengguna berhasil masuk dan URL terverifikasi mengandung `/inventory.html`. |
| **TC02** | Login dengan password salah | 1. Buka halaman login.<br>2. Masukkan username: `standard_user`<br>3. Masukkan password: `wrong_pass`<br>4. Klik tombol login. | Pengguna tetap di halaman login. Muncul pesan error "Username and password do not match". |
| **TC03** | Login dengan username kosong | 1. Buka halaman login.<br>2. Biarkan username kosong.<br>3. Masukkan password: `secret_sauce`<br>4. Klik tombol login. | Pengguna tetap di halaman login. Muncul pesan error "Username is required". |

### Contoh Kode Tes (untuk TC01)

Sebuah file tes Cypress (misalnya `cypress/e2e/login.cy.js`) akan terlihat seperti ini:

```javascript
describe('Uji Fungsionalitas Login SauceDemo', () => {

  // Blok "beforeEach" berjalan sebelum setiap tes ("it")
  beforeEach(() => {
    // 1. Buka halaman login
    cy.visit('[https://www.saucedemo.com/](https://www.saucedemo.com/)');
  });

  it('TC01: Berhasil login dengan kredensial valid', () => {
    // 2. Masukkan username
    cy.get('[data-test="username"]').type('standard_user');
    
    // 3. Masukkan password
    cy.get('[data-test="password"]').type('secret_sauce');
    
    // 4. Klik tombol login
    cy.get('[data-test="login-button"]').click();
    
    // Verifikasi (Assertion):
    // Memastikan URL mengandung '/inventory.html'
    cy.url().should('include', '/inventory.html');
    
    // Memastikan elemen keranjang belanja terlihat
    cy.get('.shopping_cart_link').should('be.visible');
  });

  // Tes lain (TC02, TC03) akan ditulis di sini...
});
````

-----

## **Kesimpulan**

Cypress telah merevolusi cara *developer* dan QA melakukan pengujian *end-to-end*. Dengan memprioritaskan pengalaman *developer*, menyediakan *feedback* visual yang instan, dan menghilangkan sumber-sumber ketidakstabilan tes (seperti *flaky tests*), ia secara signifikan mempercepat siklus pengembangan.

Proses instalasi yang mudah dan sintaks yang intuitif membuatnya mudah diadopsi, sementara fitur-fitur canggihnya (seperti *Time Travel* dan *automatic waits*) membuatnya menjadi alat yang sangat kuat untuk memastikan kualitas dan keandalan aplikasi web modern.

-----

## **Referensi**

Materi ini dirangkum dari presentasi "Pengantar Cypress" oleh Kelompok 8 - Sistem Informasi 2023. Presentasi (PPT) lengkap dari materi ini dapat dilihat melalui tautan berikut:

[Lihat Presentasi (PPT)](https://drive.google.com/file/d/1lBwmTvmXF0iDxCIX0SbTfTBOQ7-eOLOx/view?usp=drive_link)
