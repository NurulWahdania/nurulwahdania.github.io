---
layout: post
date: 2024-12-15
author: "Nurul Wahdania"
title: "Minecraft Web Clone: Eksplorasi Desain Native HTML & CSS"
categories: [Web Development, Frontend, UI Design]
description: Replikasi landing page Minecraft.net yang dibangun menggunakan murni HTML dan CSS untuk melatih fundamental web design dan responsivitas.
tags: [HTML5, CSS3, Web Design, Minecraft, Frontend, Clone]
image: /assets/img/minecraft.png
---

# **Minecraft Web Clone**

Siapa yang tidak mengenal Minecraft? Game *sandbox* legendaris ini memiliki gaya visual yang sangat khas: kotak-kotak, *pixelated*, dan kreatif.

Sebagai bagian dari tugas praktikum Pemrograman Web, saya menantang diri sendiri untuk mereplikasi antarmuka (UI) dari situs resmi [Minecraft.net](https://www.minecraft.net/en-us). Proyek ini bertujuan untuk memperkuat pemahaman tentang struktur **HTML5** dan kekuatan **CSS3** murni tanpa bantuan framework instan.

> **🎯 Misi:** Menciptakan kembali pengalaman visual website Minecraft yang ikonik dengan akurasi tinggi, mulai dari tata letak grid hingga tipografi khas, menggunakan teknologi web native.

---

## **🛠️ Tech Stack & Tools**

Karena tujuan utamanya adalah memperdalam fundamental, saya membatasi diri untuk tidak menggunakan CSS Framework (seperti Bootstrap atau Tailwind).

* **HTML5 (Semantic Markup):** Menyusun struktur halaman yang rapi (Header, Nav, Section, Footer).
* **CSS3 (Styling):** Menangani seluruh aspek visual, termasuk layouting dengan *Flexbox* & *Grid*, animasi transisi, dan responsivitas.
* **VS Code:** Editor kode utama.
* **Google Fonts:** Menggunakan font yang menyerupai gaya tipografi Minecraft.

---

## **💡 Fitur & Highlight Desain**

Website ini bukan sekadar gambar statis, tetapi halaman web fungsional yang responsif:

### **1. Navigation Bar & Hero Section**
Bagian atas halaman dirancang untuk menangkap perhatian pengunjung dengan latar belakang visual dunia Minecraft yang imersif dan menu navigasi yang melayang (*sticky/fixed*).

### **2. Card Layout System**
Menampilkan berbagai varian game Minecraft (Dungeons, Legends, Education) menggunakan sistem **Grid Layout**. Kartu-kartu ini akan merespons ukuran layar, berubah dari susunan 4 kolom (desktop) menjadi 1 kolom (mobile).

### **3. Interactivity (Hover Effects)**
Memberikan umpan balik visual saat pengguna mengarahkan kursor ke elemen tertentu.
* *Button Hover:* Tombol berubah warna atau skala saat disentuh.
* *Card Lift:* Kartu game sedikit "terangkat" ke atas untuk memberikan efek 3D.

---

## **📝 Cuplikan Kode (Aesthetic Snippet)**

Berikut adalah kode CSS yang saya gunakan untuk membuat kartu game terlihat elegan dengan nuansa gelap (*Dark Mode*) dan efek interaktif:

```css
/* Container untuk kartu game menggunakan Flexbox */
.game-container {
    display: flex;
    justify-content: center;
    gap: 20px;
    flex-wrap: wrap; /* Agar responsif turun ke bawah */
    padding: 2rem 0;
}

/* Styling visual kartu */
.game-card {
    background-color: #1a1a1a; /* Warna gelap khas Minecraft */
    border-radius: 8px;
    overflow: hidden;
    transition: all 0.3s ease; /* Animasi halus */
    border: 1px solid #333;
    max-width: 300px;
}

/* Efek saat mouse diarahkan (Hover) */
.game-card:hover {
    transform: translateY(-8px); /* Efek melayang naik */
    box-shadow: 0 12px 24px rgba(0, 0, 0, 0.5); /* Bayangan dramatis */
    border-color: #43b548; /* Aksen hijau Creeper */
}

```

---

## **🔥 Tantangan & Pembelajaran**

Mengerjakan proyek ini dengan *Vanilla CSS* mengajarkan saya banyak hal yang seringkali tersembunyi saat menggunakan Framework:

1. **CSS Box Model:** Memahami secara mendalam bagaimana margin, border, dan padding mempengaruhi dimensi elemen.
2. **Flexbox vs Grid:** Belajar kapan harus menggunakan Flexbox (untuk penyusunan 1 dimensi) dan kapan menggunakan Grid (untuk tata letak 2 dimensi yang kompleks).
3. **Asset Management:** Mengelola gambar agar tetap tajam namun ringan (*optimized*) saat dimuat.

---

## **🚀 Tautan Proyek**

Ingin melihat hasil akhirnya secara langsung atau membedah kodenya? Kunjungi repositori di bawah ini:

**[📂 Buka Repository Minecraft Clone](https://www.google.com/search?q=https://github.com/NurulWahdania)**
*(Link akan diperbarui)*
