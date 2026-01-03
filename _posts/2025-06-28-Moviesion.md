---
layout: post
date: 2025-06-28
author: "Nurul Wahdania"
title: "Moviesion: Platform Streaming & Katalog Film"
categories: [Web Development, Backend, Database]
description: Aplikasi katalog film berbasis web yang memungkinkan pengguna menjelajahi film, menonton trailer, dan mengelola daftar tontonan (watchlist).
tags: [Python, React, MySQL, XAMPP, Backend Development, API Integration]
image: /assets/img/moviesion.png
---

# **Moviesion: Your Ultimate Movie Companion**

**Moviesion** adalah sebuah platform web interaktif yang dirancang bagi para pencinta film. Proyek ini bertujuan untuk memberikan pengalaman menjelajah katalog film yang mulus, lengkap dengan detail episode, trailer, dan fitur personalisasi.

Website ini dikembangkan sebagai **Tugas Besar Kelompok** (Group Project), di mana kami membangun sistem yang menyerupai layanan streaming populer dengan antarmuka yang modern dan responsif.

> **Fitur Utama:** Eksplorasi film berdasarkan kategori, pemutaran trailer, detail sinopsis/episode, dan fitur *Watchlist* untuk menyimpan film favorit.

---

## **👥 Tim Pengembang (Kelompok)**

Proyek ini merupakan hasil kolaborasi tim yang solid, terdiri dari:

1.  **Frisilia Kiki** (H071231003)
2.  **Nurul Wahdania** (H071231005) - *Backend & Integration*
3.  **Fitriani Jaya** (H071231012)

---

## **👩‍💻 Peran Saya: Backend & Integrator**

Dalam tim ini, saya memegang tanggung jawab utama di sisi **Backend Development**, yang meliputi:

* **API Development (Python):** Membangun RESTful API menggunakan Python untuk menangani permintaan data dari frontend (seperti mengambil daftar film, pencarian, dan detail user).
* **Database Management (MySQL):** Merancang skema database (*Entity Relationship Diagram*) dan mengelolanya menggunakan **XAMPP/MySQL** untuk menyimpan data film, user, dan watchlist.
* **System Integration:** Menghubungkan logika *Backend* (Python) dengan tampilan *Frontend* (React) agar data dapat tampil secara dinamis dan *real-time*.

---

## **🛠️ Tech Stack**

Kami menggunakan teknologi modern untuk memisahkan *concern* antara tampilan dan logika bisnis:

* **Frontend:** React.js + Vite (untuk antarmuka yang cepat dan interaktif).
* **Backend:** Python (menangani logic server).
* **Database:** MySQL via XAMPP (penyimpanan data relasional).
* **Styling:** CSS Modern / Tailwind (berdasarkan struktur UI).

---

## **💡 Fitur Unggulan**

1.  **Movie Discovery:** Halaman beranda yang menampilkan film *trending*, kategori *fantasy*, *action*, dll (seperti terlihat pada screenshot).
2.  **Watchlist System:** Pengguna dapat menekan tombol *"Add to Watchlist"* untuk menyimpan film yang ingin ditonton nanti ke dalam database pribadi mereka.
3.  **Detailed Info:** Menampilkan sinopsis, durasi, dan *trailer* film sebelum pengguna memutuskan untuk menonton.

---

## **📝 Cuplikan Kode (Backend Logic)**

Berikut adalah gambaran konseptual bagaimana saya menangani koneksi database dan pengambilan data film menggunakan Python:

```python
# Contoh ilustrasi backend logic untuk mengambil data film
import mysql.connector

def get_db_connection():
    conn = mysql.connector.connect(
        host="localhost",
        user="root",
        password="",
        database="moviesion_db"
    )
    return conn

def get_all_movies():
    conn = get_db_connection()
    cursor = conn.cursor(dictionary=True)
    
    # Query untuk mengambil data film
    query = "SELECT id, title, genre, poster_url FROM movies ORDER BY release_date DESC"
    cursor.execute(query)
    movies = cursor.fetchall()
    
    cursor.close()
    conn.close()
    return movies

```

---

## **🚀 Tautan Proyek**

Untuk melihat kode sumber lengkap baik dari sisi Frontend maupun Backend, silakan kunjungi repositori GitHub kami:

**[📂 Buka Repository Moviesion](https://github.com/NurulWahdania/Moviesion)**

