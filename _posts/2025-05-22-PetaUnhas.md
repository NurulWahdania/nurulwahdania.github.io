---
layout: post
date: 2025-05-22
author: "Nurul Wahdania"
title: "Peta Digital Unhas: Visualisasi Lokasi dengan GeoJSON"
categories: [Web Development, GIS, Sistem Informasi Geografis]
description: Proyek pemetaan interaktif Universitas Hasanuddin menggunakan Leaflet.js dan data spasial GeoJSON untuk memvisualisasikan lokasi kampus.
tags: [GeoJSON, Leaflet.js, JavaScript, GIS, Tailwind CSS, Web Mapping]
image: /assets/img/peta-unhas.png
---

# **Peta Digital Universitas Hasanuddin**

Dalam era informasi spasial, kemampuan memvisualisasikan data lokasi menjadi sangat penting. Proyek **Peta Unhas** ini adalah implementasi sederhana dari Sistem Informasi Geografis (SIG) berbasis web.

Tujuannya adalah untuk memetakan lokasi-lokasi penting kampus Universitas Hasanuddin (seperti Kampus Tamalanrea dan Kampus Gowa) menggunakan format data standar **GeoJSON** dan menampilkannya secara interaktif.

> **Misi Proyek:** Membangun peta interaktif yang ringan dan informatif untuk menampilkan sebaran lokasi kampus Universitas Hasanuddin menggunakan teknologi *open-source*.

---

## **🛠️ Tech Stack & Tools**

Proyek ini dibangun dengan kombinasi teknologi web modern dan *library* pemetaan:

* **Leaflet.js:** Library JavaScript *open-source* terkemuka untuk peta interaktif yang ramah seluler.
* **GeoJSON:** Format standar berbasis JSON untuk merepresentasikan fitur geografis (titik lokasi, deskripsi, dan atribut lainnya).
* **Tailwind CSS:** Digunakan untuk mempercantik antarmuka pengguna (UI) dengan konfigurasi warna kustom khas Unhas.
* **HTML5 & JavaScript:** Fondasi struktur dan logika peta.

---

## **📍 Fitur Utama**

1.  **Visualisasi Multi-Kampus:** Menampilkan *marker* (penanda) untuk lokasi Kampus Pusat (Tamalanrea) dan Kampus Teknik (Gowa).
2.  **Popup Informasi:** Saat marker diklik, pengguna dapat melihat detail lokasi, deskripsi singkat, dan ikon terkait.
3.  **Custom Styling:** Antarmuka disesuaikan dengan identitas warna Unhas (Merah Maroon) menggunakan konfigurasi Tailwind.

---

## **📝 Bedah Kode (Code Snippet)**

Bagian paling krusial dari proyek ini adalah bagaimana data lokasi disimpan dalam format **GeoJSON**. Berikut adalah struktur data yang saya gunakan untuk mendefinisikan titik koordinat kampus:

```json
/* unhas.geojson */
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "name": "Kampus Tamalanrea (Pusat)",
        "description": "Kampus utama Universitas Hasanuddin, terletak di Tamalanrea, Makassar.",
        "icon": "unhas"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [
          119.48880634715168,
          -5.1317877938445315
        ]
      }
    },
    {
      "type": "Feature",
      "properties": {
        "name": "Kampus Gowa (Teknik)",
        "description": "Kampus Fakultas Teknik Universitas Hasanuddin di Gowa.",
        "icon": "teknik"
      }
      /* ... coordinates lainnya ... */
    }
  ]
}

```

Selain itu, saya juga mengonfigurasi **Tailwind CSS** secara langsung di dalam file HTML untuk mencocokkan palet warna resmi universitas:

```html
<script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            unhas: {
              red: '#A91B0D',       /* Merah Unhas */
              darkred: '#851208',
              lightred: '#D92919',
              yellow: '#FFBE3C'     /* Kuning Emas */
            }
          }
        }
      }
    }
</script>

```

---

## **💡 Tantangan & Pembelajaran**

Mengerjakan proyek SIG ini memberikan wawasan baru, terutama dalam hal:

* **Koordinat Geografis:** Memahami sistem koordinat Latitude/Longitude dan cara menerapkannya dalam format Array JSON.
* **Asynchronous Loading:** Mempelajari cara memuat file eksternal `.geojson` menggunakan `fetch()` API agar dapat dirender oleh Leaflet.
* **Data Binding:** Menghubungkan data properti (seperti nama dan deskripsi) ke dalam elemen popup peta.

---

## **🚀 Tautan Proyek**

Ingin melihat peta interaktif ini atau mempelajari kode sumbernya? Silakan kunjungi tautan di bawah ini:

*[Link Repository Akan Segera Tersedia]*
