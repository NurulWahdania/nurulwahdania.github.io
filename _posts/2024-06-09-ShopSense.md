---
layout: post
date: 2024-06-09
author: "MAJO Group - Sistem Informasi 2023"
title: "ShopSense: Solusi Cerdas Manajemen Keuangan Toko"
categories: [Software Development, Java, OOP, Finance]
description: ShopSense adalah aplikasi desktop berbasis Java untuk manajemen keuangan, stok barang, dan kasir yang menerapkan prinsip Object-Oriented Programming (OOP) secara menyeluruh.
tags: [Java, JavaFX, OOP, Management System, Finance, Budgeting]
image: /assets/img/shop-sense.png
---

# **ShopSense**

Dalam dunia bisnis ritel, efisiensi adalah segalanya. Kesalahan kecil dalam pencatatan stok atau transaksi dapat berdampak besar pada keuntungan. **ShopSense** hadir sebagai solusi digital untuk membantu pemilik toko mengelola bisnis mereka dengan lebih cerdas, akurat, dan terstruktur.

Proyek ini dikembangkan oleh **MAJO Group** sebagai tugas besar Semester 2 (2024) dengan tema *Finance and Budgeting*.

> **Executive Summary:** ShopSense adalah aplikasi yang dirancang untuk mempermudah manajemen keuangan toko dengan memantau stok barang secara *real-time*, menghitung transaksi dengan akurasi tinggi, serta mencatat arus keuangan secara teratur dan otomatis.

---

## **Latar Belakang & Masalah**

Pembuatan aplikasi ShopSense didasari oleh kebutuhan nyata untuk meningkatkan efisiensi operasional toko. Selama ini, banyak toko konvensional menghadapi kendala utama seperti:

* **Pemantauan Stok Manual:** Sulitnya melacak keluar-masuk barang secara manual sering menyebabkan *human error* dan selisih stok.
* **Kesalahan Perhitungan:** Risiko kesalahan hitung saat transaksi kasir yang dapat merugikan toko atau pelanggan.
* **Pencatatan yang Tidak Rapi:** Riwayat penjualan yang seringkali terlewat atau tidak terdokumentasi dengan baik, menyulitkan analisis keuntungan.

ShopSense hadir untuk mengotomasi proses tersebut, membantu pemilik toko mengambil keputusan berbasis data, serta meningkatkan pelayanan kepada pelanggan melalui proses transaksi yang cepat.

---

## **Fitur Utama Aplikasi**

ShopSense tidak hanya sekadar kalkulator kasir, namun menawarkan fitur manajerial yang komprehensif:

#### **1. Manajemen Stok & Informasi Barang**
Memungkinkan pengguna untuk menambah, mengedit, dan melihat informasi stok barang secara detail. Sistem akan memberikan informasi akurat mengenai ketersediaan produk.

#### **2. Pencatatan Transaksi & Diskon**
Fitur kasir yang responsif untuk menghitung total belanja. Kami juga menyematkan **Fitur Diskon**, memudahkan toko memberikan potongan harga kepada pelanggan setia secara fleksibel.

#### **3. Laporan Keuangan Toko**
Sistem secara otomatis merekapitulasi jumlah pemasukan. Pemilik toko dapat melihat laporan pendapatan tanpa perlu menghitung ulang nota satu per satu.

#### **4. Manajemen Karyawan (Opsional)**
Fitur untuk memasukkan dan mengelola data karyawan. Fitur ini dibuat fleksibel agar aplikasi dapat digunakan baik oleh toko yang memiliki staf maupun yang dikelola sendiri.

---

## **Penerapan Object-Oriented Programming (OOP)**

Sebagai proyek pengembangan perangkat lunak berbasis Java, ShopSense menerapkan prinsip-prinsip utama OOP untuk memastikan kode yang rapi, aman, dan mudah dikembangkan:

#### **Abstraction (Abstraksi)**
Kami menggunakan kelas abstrak untuk membuat kerangka dasar objek.
* **Implementasi:** Kelas `Karyawan.java` mewarisi atribut dari kelas abstrak `KaryawanAbstrak.java`. Ini memastikan struktur data karyawan konsisten.

#### **Inheritance (Pewarisan) & Polymorphism**
Kami menggunakan pewarisan untuk menghindari duplikasi kode dan polimorfisme untuk memodifikasi perilaku metode.
* **Implementasi:** Kelas `FromBarang.java` mewarisi (*extends*) dari kelas `ListPaneBarang.java`.
* **Overriding:** Terdapat *method overriding* pada `FromBarang.java` dan `DatePickerExample.java`, memungkinkan sub-kelas memiliki perilaku spesifik yang berbeda dari kelas induknya.

#### **Encapsulation (Enkapsulasi)**
Kami melindungi data sensitif agar tidak bisa diakses sembarangan dari luar kelas.
* **Implementasi:** Pada kelas `Transaksi.java`, atribut disembunyikan (*private*) dan hanya dapat diakses atau dimodifikasi melalui metode *getter* dan *setter* publik. Ini menjaga integritas data transaksi.

---

## **Tim Pengembang (MAJO Group)**

Proyek ini berhasil diselesaikan berkat kerjasama tim yang solid di bawah bimbingan Kak **Kelvin Leonardo Sianipar**.

**Anggota Tim:**
1.  **A. Aisar Saputra Dwi Anna** (H071231048)
2.  **Indy Sekar Ayu** (H071231010)
3.  **Nurul Wahdania** (H071231005)

---

## **Kesimpulan**

ShopSense adalah bukti bahwa digitalisasi manajemen toko tidak harus rumit. Dengan antarmuka yang ramah pengguna dan struktur kode yang kokoh menggunakan prinsip OOP, aplikasi ini siap membantu UMKM beralih dari pencatatan manual ke sistem digital yang efisien dan akurat.

---

## **Tautan Proyek**
Untuk melihat kode sumber (*source code*) lengkap dan dokumentasi teknis, silakan kunjungi repositori GitHub kami:

[Lihat Repository ShopSense](https://github.com/NurulWahdania/PROYEK-KELOMPOK-23-SEMESTER2-2024)