# 🛍️ Mochimo — Mini E-Commerce Web App

Mochimo adalah aplikasi web e-commerce sederhana berbasis PHP & MySQL untuk menjual produk lucu dan estetik. Dilengkapi dengan panel admin dan fitur lengkap untuk pelanggan mulai dari keranjang belanja hingga tracking pesanan.

---

## 🗂️ Struktur Direktori

```
mochimo/
├── admin/          # Panel manajemen (dashboard, produk, pesanan, dll.)
├── auth/           # Login & register customer
├── config/         # Konfigurasi koneksi database
├── customer/       # Halaman-halaman untuk pelanggan
├── database/       # File SQL (mochimo.sql)
├── pengunjung/     # Halaman untuk pengunjung (belum login)
├── proses/         # Script proses backend (add cart, dll.)
├── template/       # Header, footer, navbar
├── assets/css/     # File stylesheet
├── index.php       # Halaman utama (beranda)
└── about.php       # Halaman tentang
```

---

## ✨ Fitur Utama

### 👤 Customer
- Register & login akun
- Browsing produk dengan fitur pencarian
- Filter produk per kategori
- Lihat detail produk (varian, galeri foto, ukuran)
- Wishlist produk
- Keranjang belanja (cart)
- Checkout dengan dukungan voucher diskon
- Upload bukti pembayaran (QR / simulasi)
- Tracking status pesanan
- Riwayat pesanan
- Edit profil & ganti password
- Notifikasi pesanan

### 🔧 Admin
- Dashboard ringkasan (penjualan, pesanan, dll.)
- Manajemen produk (tambah, edit, hapus + varian & galeri)
- Manajemen kategori
- Manajemen voucher diskon
- Lihat & kelola pesanan masuk
- Verifikasi pembayaran
- Tambah tracking pengiriman
- Manajemen data customer
- Laporan pemasukan

---

## 🗄️ Struktur Database

Database: `mochimo` (MySQL)

| Tabel | Keterangan |
|---|---|
| `users` | Data akun customer & admin |
| `produk` | Data produk |
| `kategori` | Kategori produk |
| `varian_produk` | Varian warna/tipe produk |
| `ukuran_produk` | Pilihan ukuran produk |
| `galeri_produk` | Foto galeri produk |
| `gambar_produk` | Gambar utama produk |
| `cart` | Keranjang belanja |
| `pesanan` | Header pesanan |
| `detail_pesanan` | Item per pesanan |
| `pembayaran` | Data pembayaran |
| `konfirmasi_pembayaran` | Bukti upload pembayaran |
| `tracking` | Status pengiriman |
| `voucher` | Kode voucher diskon |
| `wishlist` | Daftar wishlist customer |
| `review` | Ulasan produk |
| `notifikasi` | Notifikasi untuk customer |
| `banner` | Banner promosi beranda |

---

## ⚙️ Instalasi

### Prasyarat
- PHP >= 8.1
- MySQL >= 8.0
- Web server (Apache/Nginx) — disarankan pakai **XAMPP** atau **Laragon**

### Langkah-langkah

1. **Clone / ekstrak project** ke folder htdocs (XAMPP) atau www (Laragon):
   ```
   htdocs/mochimo/
   ```

2. **Import database**
   - Buka phpMyAdmin
   - Buat database baru bernama `mochimo`
   - Import file `database/mochimo.sql`

3. **Konfigurasi koneksi** — edit file `config/koneksi.php`:
   ```php
   $host = "localhost";
   $user = "root";
   $pass = "";          // sesuaikan password MySQL kamu
   $db   = "mochimo";
   ```

4. **Jalankan aplikasi** di browser:
   ```
   http://localhost/mochimo/
   ```

---

## 🔐 Akun Default

> Cek data di tabel `users` pada file SQL untuk akun admin dan customer yang sudah tersedia.

| Role | Halaman Login |
|---|---|
| Admin | `http://localhost/mochimo/admin/login.php` |
| Customer | `http://localhost/mochimo/auth/login.php` |

---

## 🛠️ Tech Stack

| Layer | Teknologi |
|---|---|
| Backend | PHP (Native / Procedural) |
| Database | MySQL via MySQLi |
| Frontend | HTML, CSS, Bootstrap |
| Server | Apache (XAMPP/Laragon) |

---

## 📝 Catatan

- Folder `admin/upload/` digunakan untuk menyimpan gambar produk yang diupload. Pastikan folder ini memiliki izin tulis (`writable`).
- Aplikasi ini menggunakan sesi PHP (`session_start`) untuk autentikasi, pastikan PHP session aktif.
- Belum menggunakan framework; cocok sebagai proyek pembelajaran atau tugas kuliah.
