---
layout: post
date: 2025-08-15
author: "Nurul Wahdania"
title: "Danus Matics: Platform Katalog Digital & Order Otomatis"
categories: [Web Development, Frontend, Business Tools]
description: Website katalog sederhana untuk penjualan aplikasi premium (Dana Usaha) dengan integrasi pemesanan langsung ke WhatsApp menggunakan template chat otomatis.
tags: [HTML, JavaScript, Tailwind CSS, Automation, Vercel]
image: /assets/img/danus-matics.png
---

# **Danus Matics: Digitalisasi Dana Usaha**

Dalam kegiatan organisasi mahasiswa, **Dana Usaha (Danus)** adalah aspek vital. Namun, mempromosikan jualan aplikasi premium (seperti Netflix, Spotify, Canva, dll) hanya melalui *broadcast message* seringkali tidak efektif dan membingungkan pelanggan terkait daftar harga.

Untuk mengatasi hal tersebut, saya membangun **Danus Matics**, sebuah website katalog digital yang rapi, responsif, dan memudahkan calon pembeli untuk melihat produk serta melakukan pemesanan instan.

> **Tujuan:** Menggantikan daftar harga manual dengan tampilan web profesional yang mempercepat proses transaksi melalui otomatisasi pesan WhatsApp.

---

## **🛠️ Tech Stack**

Website ini dibangun dengan pendekatan *utility-first* agar ringan dan cepat saat diakses:

* **HTML5:** Struktur semantik halaman.
* **Tailwind CSS:** Untuk styling antarmuka yang modern, *clean*, dan responsif di perangkat mobile.
* **JavaScript (Vanilla):** Menangani logika dinamis untuk pembuatan link WhatsApp otomatis.
* **Vercel:** Platform deployment (hosting) agar website dapat diakses publik dengan cepat.

---

## **💡 Fitur Utama**

### **1. Katalog Produk Unggulan**
![Daftar Produk](/assets/img/danus-matics2.png)
Menampilkan daftar aplikasi premium lengkap dengan deskripsi singkat, label kategori (Music, Video, Editing), dan harga yang jelas. Tampilan dibuat *Grid* agar mudah di-skimming oleh pengunjung.

### **2. Integrasi WhatsApp (One-Click Order)**
Ini adalah fitur kunci dari website ini. Pengguna tidak perlu mengetik pesan manual. Saat tombol **"Beli Sekarang"** atau **"Lihat Paket"** diklik, sistem akan:
1.  Membuka aplikasi WhatsApp.
2.  Mengarah ke nomor Admin Danus.
3.  **Otomatis mengisi pesan** sesuai produk yang dipilih.

**Contoh Pesan Otomatis:**
> *"Halo, saya ingin beli Alight Motion Sharing 1 Bulan harga 8K. Masih tersedia?"*

---

## **📝 Bedah Kode (JavaScript Logic)**

Berikut adalah potongan kode JavaScript yang saya gunakan untuk membuat fitur *template chat* dinamis tersebut. Kode ini mengambil data nama produk dan harga, lalu mengubahnya menjadi URL WhatsApp API.

```javascript
function orderProduct(productName, productPrice) {
    // Nomor WhatsApp Admin (Format 62...)
    const phoneNumber = "62821xxxxxxxx"; 
    
    // Template pesan dinamis
    const message = `Halo, saya ingin beli ${productName} harga ${productPrice}. Masih tersedia?`;
    
    // Encode pesan agar aman untuk URL
    const encodedMessage = encodeURIComponent(message);
    
    // Buka WhatsApp di tab baru
    const waUrl = `https://wa.me/${phoneNumber}?text=${encodedMessage}`;
    window.open(waUrl, '_blank');
}

```

Pada tombol HTML, fungsi ini dipanggil seperti ini:

```html
<button 
    onclick="orderProduct('Alight Motion Sharing 1 Bulan', '8K')"
    class="bg-green-500 hover:bg-green-600 text-white font-bold py-2 px-4 rounded">
    Beli Sekarang
</button>

```

---

## **🚀 Tautan Proyek**

Website ini sudah *live* dan digunakan untuk operasional penjualan. Anda dapat mencobanya atau melihat kode sumbernya di bawah ini:

* 🌐 **Live Demo:** [danus-matics.vercel.app](https://danus-matics.vercel.app/)
* 📂 **Source Code:** [GitHub Repository](https://github.com/NurulWahdania/danus-matics)

