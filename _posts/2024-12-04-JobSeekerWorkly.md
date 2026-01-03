---
layout: post
date: 2024-12-04
author: "Nurul Wahdania"
title: "Workly: Platform Pencarian Kerja Terintegrasi"
categories: [Web Development, Fullstack, Laravel]
description: Workly adalah aplikasi web pencarian kerja berbasis Laravel yang menghubungkan pencari kerja dan perusahaan, dikembangkan secara fullstack oleh Nurul Wahdania.
tags: [Laravel, PHP, Tailwind CSS, Web Development, Fullstack, MySQL]
image: /assets/img/workly-jobseeker.png
---

# **Workly: Platform Pencarian Kerja Modern**

Di era digital ini, proses rekrutmen membutuhkan platform yang cepat, efisien, dan transparan. **Workly** adalah solusi *fullstack* yang saya kembangkan untuk Tugas Akhir, menjembatani kebutuhan antara pencari kerja dan perusahaan.

> **🎯 Visi Proyek:** Menciptakan ekosistem rekrutmen digital yang memudahkan pelamar menemukan karir impian dan membantu perusahaan mengelola lowongan kerja secara efektif.

---

## **🛠️ Tech Stack & Tools**

Proyek ini dibangun menggunakan teknologi modern untuk memastikan performa dan skalabilitas:

* **Laravel (Backend):** Framework PHP yang kuat untuk logika bisnis, keamanan, dan manajemen API.
* **Tailwind CSS (Frontend):** *Utility-first* CSS framework untuk membangun UI yang cepat, modern, dan responsif.
* **MySQL (Database):** Penyimpanan data relasional yang efisien.
* **Eloquent ORM:** Memudahkan interaksi dengan database melalui sintaks yang elegan.

---

## **👨‍💻 Peran Saya: Fullstack Developer**

Dalam proyek ini, saya bertanggung jawab penuh atas seluruh siklus pengembangan (*End-to-End Development*):

### **1. Backend Development**
* Merancang arsitektur database (ERD) dan relasi antar tabel.
* Mengimplementasikan sistem autentikasi & otorisasi multi-role.
* Membangun RESTful logic dan pengelolaan data yang aman.

### **2. Frontend Development**
* Merancang antarmuka (UI/UX) yang ramah pengguna.
* Mengintegrasikan tampilan dengan data dari backend.
* Memastikan website responsif di berbagai ukuran layar (Desktop & Mobile).

---

## **🎭 Sistem Role & Fitur**

Workly memiliki 3 peran pengguna (*user roles*) dengan hak akses yang spesifik:

| Role | Deskripsi & Akses Fitur |
| :--- | :--- |
| **🔑 Admin** | Mengelola seluruh sistem, memverifikasi akun perusahaan, dan memoderasi konten lowongan. |
| **🏢 Employer** | (Pemberi Kerja) Memposting lowongan, melihat daftar pelamar, dan mengelola profil perusahaan. |
| **👤 Job Seeker** | (Pencari Kerja) Mencari lowongan dengan filter, mengirim lamaran, dan mengelola CV digital. |

---

## **💡 Fitur Unggulan**

Beberapa fitur kunci yang menjadi *highlight* dalam aplikasi ini:

1.  **Multi-Role Authentication:** Sistem keamanan berbasis *Middleware* untuk memisahkan akses Admin, Employer, dan Job Seeker.
2.  **Advanced Search:** Pencari kerja dapat memfilter lowongan berdasarkan kategori, lokasi, dan tipe pekerjaan.
3.  **Manajemen Pelamar:** Perusahaan dapat melihat status pelamar secara *real-time*.
4.  **Desain Responsif:** Tampilan yang optimal di perangkat desktop maupun *smartphone*.

---

## **📝 Cuplikan Kode (Snippet)**

Berikut adalah implementasi **Middleware** di Laravel yang saya buat untuk membatasi hak akses halaman berdasarkan tipe *user*:

```php
// app/Http/Middleware/CheckRole.php

namespace App\Http\Middleware;

use Closure;
use Illuminate\Http\Request;
use Illuminate\Support\Facades\Auth;

class CheckRole
{
    /**
     * Handle an incoming request.
     */
    public function handle(Request $request, Closure $next, string $role)
    {
        // 1. Validasi apakah user sudah login
        if (!Auth::check()) {
            return redirect()->route('login')
                ->with('error', 'Silakan login terlebih dahulu');
        }

        // 2. Validasi apakah role user sesuai
        if (Auth::user()->role !== $role) {
            // Jika role tidak cocok, tolak akses (403 Forbidden)
            abort(403, 'Akses ditolak. Anda tidak memiliki hak akses.');
        }

        return $next($request);
    }
}

```

---

## **🎯 Tantangan & Pembelajaran**

Pengembangan Workly memberikan banyak pelajaran berharga bagi saya sebagai developer:

* **Security:** Pentingnya memvalidasi setiap input dan akses pengguna untuk mencegah celah keamanan.
* **Database Design:** Merancang skema database yang efisien sangat krusial agar aplikasi tidak lambat saat data bertambah.
* **User Experience:** Membuat alur aplikasi yang *seamless* agar pengguna tidak bingung saat melamar kerja atau memposting lowongan.

---

## **🚀 Tautan Proyek**

Untuk melihat *source code* lengkap, dokumentasi instalasi, dan fitur lainnya, silakan kunjungi repositori GitHub di bawah ini:

**[📂 Buka Repository Workly di GitHub](https://github.com/NurulWahdania/JobSeeker-Workly)**
