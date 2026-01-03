---
layout: post
date: 2025-12-13
author: "Nurul Wahdania"
title: "Tukar Buku: Marketplace Aman untuk Literasi"
categories: [Web Development, Backend, Python]
description: Platform marketplace berbasis web untuk jual-beli dan tukar buku dengan keamanan JWT dan backend FastAPI yang cepat.
tags: [Python, FastAPI, MySQL, JWT, Backend, E-commerce, Team Project]
image: /assets/img/tukar-buku.png
---

# **Tukar Buku**

Buku bekas seringkali hanya menumpuk di rak, padahal ilmunya masih sangat berharga. **Tukar Buku** hadir sebagai solusi marketplace web yang memfasilitasi pengguna untuk tidak hanya membeli dan menjual, tetapi juga melakukan **tukar tambah (barter)** buku dengan aman dan mudah.

Proyek ini dikembangkan secara berkelompok dengan pembagian tugas yang terstruktur untuk menciptakan ekosistem aplikasi yang lengkap, mulai dari desain sistem hingga pengujian.

> **Konsep Utama:** Platform fleksibel di mana satu akun pengguna dapat berperan ganda sebagai Pembeli maupun Penjual, dilengkapi sistem keamanan transaksi yang terpercaya.

---

## **👥 Tim Pengembang**

Keberhasilan proyek ini adalah hasil kerja keras tim dengan spesialisasi masing-masing:

* **Nurul Wahdania:** Backend Developer & Integration
* **Frisilia Kiki:** Database Engineer
* **Fitriani Jaya:** Frontend Developer
* **Destin Kendenan:** Quality Assurance (Testing)
* **Kezia Dewanti Putri Ayu Tappi:** UI/UX Designer
* **Ahmad Rafly Putra Hasrun:** System Designer
* **Rohsilia Gratia Simak:** Technical Writer (Proposal, Laporan, Manual)

---

## **👩‍💻 Peran Saya: Backend & Security**

Sebagai **Backend Developer**, saya bertanggung jawab membangun "mesin" di balik layar yang memastikan data mengalir dengan cepat dan aman. Tugas utama saya meliputi:

1.  **API Development (FastAPI):** Mengembangkan RESTful API menggunakan Python dengan framework **FastAPI** untuk performa tinggi.
2.  **Keamanan (JWT):** Mengimplementasikan otentikasi menggunakan **JSON Web Tokens (JWT)** untuk melindungi rute transaksi dan data pengguna.
3.  **Integrasi Frontend:** Bekerja sama dengan tim Frontend untuk memastikan *endpoint* API dapat dikonsumsi dengan baik oleh antarmuka pengguna.
4.  **Logika Bisnis:** Menangani logika *role switching* (User ke Penjual) dan validasi transaksi.

---

## **🛠️ Tech Stack**

* **Bahasa:** Python
* **Framework Backend:** FastAPI
* **Database:** MySQL
* **Keamanan:** JWT (JSON Web Token), OAuth2 Password Bearer
* **Arsitektur:** REST API

---

## **💡 Fitur Unggulan**

### **1. Fleksibilitas Role (Dual-Role System)**
Sistem ini memiliki 3 aktor: **Admin**, **Penjual**, dan **Pembeli**. Keunikannya, seorang *User* biasa bisa mengaktifkan mode *Penjual* tanpa perlu membuat akun baru, dan *Penjual* tetap bisa berbelanja buku dari toko lain.

### **2. Sistem Kepercayaan (Trust System)**
Untuk mencegah penipuan yang marak di marketplace barang bekas, kami menerapkan:
* **Rating & Review Terverifikasi:** Pengguna hanya bisa memberikan rating/ulasan *setelah* transaksi dinyatakan selesai oleh sistem.
* **Pelaporan Penipuan:** Fitur *report* toko atau produk yang mencurigakan langsung ke Admin.

### **3. Mekanisme Tukar & Jual**
Mendukung transaksi konvensional (Jual-Beli) dan fitur unik **Tukar Buku** antar pengguna.

---

## **📝 Cuplikan Kode (Backend Snippet)**

Berikut adalah contoh implementasi endpoint di **FastAPI** yang saya buat, menunjukkan bagaimana dependensi JWT digunakan untuk mengamankan data pengguna saat ini:

```python
from fastapi import APIRouter, Depends, HTTPException
from app.auth import get_current_user
from app.schemas import UserSchema

router = APIRouter()

# Endpoint untuk mendapatkan profil pengguna (Terproteksi JWT)
@router.get("/users/me", response_model=UserSchema)
async def read_users_me(current_user: UserSchema = Depends(get_current_user)):
    """
    Mengambil data user yang sedang login.
    Membutuhkan token JWT yang valid di header Authorization.
    """
    if not current_user:
        raise HTTPException(status_code=401, detail="User tidak valid")
    
    return current_user

```

---

## **🚀 Tautan Proyek**

Seluruh kode sumber backend dan dokumentasi API dapat dilihat melalui repositori GitHub berikut:

**[📂 Buka Repository Tukar Buku](https://github.com/NurulWahdania/tukar-buku)**

