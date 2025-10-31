---
layout: post
date: 2025-09-07
author: "Kelompok 5 - Sistem Informasi 2023"
title: "Pengantar Unit Testing"
categories: [Software Development, Quality Assurance]
description: Panduan pengantar unit testing, dari konsep dasar, pentingnya, pola AAA (Arrange, Act, Assert), hingga framework populer seperti JUnit, Jest, dan Pytest.
tags: [Unit Testing, SDLC, Testing, QA, JUnit, Jest, Pytest, AAA]
image: /assets/img/pengantar-unit-testing.png
---

# **Panduan Lengkap Software Testing: Dari Unit Testing hingga Bug Report**

Dalam pengembangan perangkat lunak, memastikan kualitas adalah kunci. Dua presentasi dari rekan-rekan kami di Sistem Informasi 2023 (Kelompok 4 dan Kelompok 5) mencakup spektrum fundamental dari *Quality Assurance* (QA).

Postingan ini menggabungkan kedua materi tersebut untuk memberikan panduan komprehensif, mulai dari fondasi kode hingga pelaporan kesalahan fungsional.

---

## **Bagian 1: Fondasi - Pengantar Unit Testing (Materi Kel. 5)**

> **Ingin Coding Tanpa Khawatir Bug? [cite_start]Unit Testing Adalah Kuncinya!** [cite: 87]

Setiap aplikasi yang kompleks dibangun dari unit-unit kecil. Sebelum kita menguji keseluruhan aplikasi, kita harus memastikan setiap unit (komponen) berfungsi dengan benar.

### **Apa Itu Unit Testing?**

[cite_start]Unit testing adalah jenis pengujian yang berfokus pada **unit-unit terkecil** dalam sebuah sistem, seperti *function*, *method*, atau *class*[cite: 130, 131].

Dalam "Piramida Pengujian", unit testing adalah fondasi. [cite_start]Ini adalah tes yang jumlahnya paling banyak, paling **cepat** untuk dijalankan, dan paling **murah** untuk dibuat[cite: 136, 137].



* **Analogi:** Bayangkan merakit mobil. [cite_start]Unit testing adalah proses memastikan setiap komponen (mesin, rem, ban) berfungsi sempurna secara terpisah *sebelum* dirakit menjadi mobil utuh[cite: 142].

### **Kenapa Unit Testing Penting?**

[cite_start]Menerapkan unit testing sangat penting untuk[cite: 147]:
* [cite_start]**Mendeteksi Bug Lebih Awal:** Menemukan masalah di level fungsi jauh lebih mudah[cite: 150].
* [cite_start]**Mempermudah Refactoring:** Kita bisa mengubah kode dengan percaya diri, karena tes akan memberi tahu jika ada yang rusak[cite: 149].
* [cite_start]**Dokumentasi yang Hidup:** Tes berfungsi sebagai contoh cara menggunakan kode tersebut[cite: 156].
* [cite_start]**Menghemat Waktu dan Biaya:** Memperbaiki bug di tahap awal jauh lebih murah[cite: 154].

### **Pola Dasar: Arrange, Act, Assert (AAA)**

[cite_start]Sebuah unit test yang baik umumnya mengikuti pola Tiga A (AAA)[cite: 193]:
1.  [cite_start]**Arrange (Menyiapkan):** Menyiapkan semua kondisi awal dan data yang diperlukan[cite: 195].
2.  [cite_start]**Act (Menjalankan):** Menjalankan satu fungsi atau metode yang ingin diuji[cite: 198].
3.  [cite_start]**Assert (Memverifikasi):** Memverifikasi bahwa hasil dari tindakan (Act) sesuai dengan ekspektasi[cite: 201].

### **Framework Populer**

Untuk mempermudah, kita menggunakan *framework* seperti:
* [cite_start]**JUnit 5 (Java):** Pelopor dan standar de facto di ekosistem Java[cite: 168, 169].
* [cite_start]**Pytest (Python):** Dikenal karena sintaksnya yang sederhana dan fitur *fixtures*-nya yang kuat[cite: 184, 188, 189].
* [cite_start]**Jest (JavaScript):** Pilihan populer untuk React, Node.js, dll., dengan konfigurasi minimal[cite: 176, 178, 180].

---

## **Bagian 2: Perencanaan - Test Scenario & Test Case (Materi Kel. 4)**

Setelah memastikan unit-unit dasar kita berfungsi, kita perlu naik level dan menguji fungsionalitas aplikasi dari perspektif pengguna. Di sinilah Test Scenario dan Test Case berperan.

### **Test Scenario: Apa yang Harus Diuji?**

* [cite_start]**Definisi:** Ini adalah gambaran umum tentang apa yang akan diuji untuk memastikan fungsi aplikasi sesuai kebutuhan[cite: 12]. [cite_start]Ini menjawab pertanyaan, "Fitur apa yang akan kita uji?"[cite: 25].
* [cite_start]**Komponen:** Biasanya terdiri dari ID, Deskripsi singkat, dan Modul/Fitur yang diuji[cite: 28].

**Contoh (Aplikasi BMI):**
* [cite_start]**TS001:** Periksa fungsi slider input berat dan tinggi badan[cite: 32].
* [cite_start]**TS002:** Periksa hasil perhitungan dan klasifikasi BMI[cite: 32].
* [cite_start]**TS003:** Periksa fungsi penyimpanan history BMI[cite: 32].

### **Test Case: Bagaimana Melakukan Pengujian?**

* [cite_start]**Definisi:** Ini adalah langkah-langkah detail pengujian, yang mencakup input spesifik, proses, dan hasil yang diharapkan (*expected result*)[cite: 14]. [cite_start]Ini menjawab pertanyaan, "Bagaimana kita akan menguji fitur itu?"[cite: 26].
* [cite_start]**Komponen:** Jauh lebih rinci, mencakup ID, Deskripsi, Precondition, Test Steps, Test Data, Expected Result, Actual Result, dan Status (Pass/Fail)[cite: 30].

**Contoh (untuk Skenario TS002):**
* [cite_start]**ID Test Case:** TC003[cite: 37].
* [cite_start]**Deskripsi:** Verifikasi hasil perhitungan BMI sesuai rumus standar ($kg/m^2$)[cite: 37].
* [cite_start]**Precondition:** Aplikasi terbuka[cite: 37].
* **Test Steps:** 1. Masukkan tinggi 170cm. 2. [cite_start]Masukkan berat 65kg[cite: 37].
* [cite_start]**Test Data:** Tinggi = 170, Berat = 65[cite: 37].
* [cite_start]**Expected Result:** Hasil Perhitungan BMI... adalah 22.49[cite: 37].

---

## **Bagian 3: Pelaporan - Bug Report (Materi Kel. 4)**

Saat pengujian (baik Unit Test atau Test Case), *Actual Result* terkadang tidak sesuai dengan *Expected Result*. Ketika ini terjadi, kita harus membuat **Bug Report**.

### **Apa Itu Bug Report?**

[cite_start]Ini adalah laporan formal tentang kesalahan atau masalah pada sistem[cite: 16, 42]. Tujuannya adalah memberikan informasi yang jelas kepada developer agar mereka dapat mereproduksi dan memperbaiki masalah tersebut.

### **Severity vs. Priority**

Dua konsep penting dalam Bug Report:

* [cite_start]**Bug Severity (Tingkat Keparahan):** Mengukur dampak *bug* pada fungsionalitas *software*[cite: 45].
    * [cite_start]**Critical:** Menyebabkan kegagalan total, aplikasi tidak dapat digunakan[cite: 52].
    * [cite_start]**Major (High):** Fungsionalitas utama tidak bekerja dengan benar[cite: 50].
    * [cite_start]**Minor (Medium):** Tidak memengaruhi fungsionalitas utama, tapi menyebabkan ketidaknyamanan[cite: 48].
    * [cite_start]**Low:** Bug kosmetik atau minor yang tidak merusak sistem[cite: 46].

* **Bug Priority (Prioritas Perbaikan):** Menentukan seberapa mendesak *bug* tersebut harus diperbaiki (sering ditentukan oleh dampak bisnis).
    * [cite_start]**P1 (Urgent/Critical):** Harus diperbaiki sesegera mungkin[cite: 55].
    * [cite_start]**P2 (High):** Bug penting yang harus diperbaiki secepatnya[cite: 57].
    * [cite_start]**P3 (Medium):** Bisa diperbaiki di rilis berikutnya[cite: 59].
    * [cite_start]**P4 (Low):** Bisa diperbaiki kapan saja[cite: 61].

### **Contoh Format Bug Report**

* [cite_start]**Bug Title:** Perhitungan BMI salah saat input berat 60kg dan tinggi 170cm[cite: 63].
* [cite_start]**Bug ID:** BMI-001[cite: 63].
* [cite_start]**Step to reproduce:** 1. Buka aplikasi... 2. Masukkan Berat = 60...[cite: 63].
* [cite_start]**Actual result:** Hasil BMI = 12.5[cite: 63].
* [cite_start]**Expected result:** Hasil BMI seharusnya = 20.8[cite: 63].
* [cite_start]**Severity:** Major (High)[cite: 65].
* [cite_start]**Priority:** P2 - High[cite: 65].

---

## **Kesimpulan: Cara Terbaik Menghindari Bug**

[cite_start]Cara terbaik untuk menghindari *bug* adalah dengan menerapkan praktik terbaik di **seluruh siklus pengembangan**, tidak hanya saat pengujian[cite: 67].

Kedua presentasi ini memberikan kita strategi gabungan:
1.  [cite_start]**Mulai dari Awal (Unit Test):** Lakukan pengujian unit untuk mendeteksi bug di tahap awal[cite: 72].
2.  [cite_start]**Pahami Persyaratan:** Pastikan semua persyaratan dipahami dengan jelas[cite: 70].
3.  [cite_start]**Lakukan Code Review:** Minta pengembang lain meninjau kode untuk menemukan kesalahan[cite: 74].
4.  [cite_start]**Buat Rencana Pengujian:** Buat *test plan* yang komprehensif (Test Scenarios & Cases)[cite: 76].
5.  [cite_start]**Gunakan Otomatisasi:** Manfaatkan *automation testing* untuk deteksi lebih cepat[cite: 78].
6.  [cite_start]**Kolaborasi Tim:** Tingkatkan komunikasi antara pengembang dan penguji[cite: 80].

Dengan membangun fondasi yang kuat (Unit Testing) dan memiliki rencana yang jelas (Test Scenarios/Cases) serta proses pelaporan yang baik (Bug Reports), kita dapat memastikan perangkat lunak yang dirilis memiliki kualitas tinggi dan bebas dari kesalahan kritis.

---

## **Referensi**

Materi ini dirangkum dari dua presentasi berikut:

[Lihat Presentasi (PPT)](https://drive.google.com/file/d/1qSDpXubcQlTiRXuM2tdDO30rPo-3GkCS/view?usp=drive_link)
