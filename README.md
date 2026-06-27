# 🗞️ NewsHub – Aplikasi Portal Berita
> Praktikum Pemrograman Web 2  
> CodeIgniter 4 + Vue.js 3 | Universitas Pelita Bangsa, Bekasi  
> Dosen Pengampu: Agung Nugroho | Tahun Akademik 2024/2025

---

**Nama  :** Anthonius Dale Fernando
**NIM   :** 312410162  
**Kelas :** I241A  

---

## 📑 Daftar Modul Praktikum

| # | Modul | Materi |
|---|-------|--------|
| 01 | [Modul 1](#modul-1--mvc-dan-routing-dasar) | MVC & Routing Dasar |
| 02 | [Modul 2](#modul-2--operasi-crud-artikel) | Operasi CRUD Artikel |
| 03 | [Modul 3](#modul-3--layout-tampilan--view-cell) | Layout Tampilan & View Cell |
| 04 | [Modul 4](#modul-4--sistem-login--filter-autentikasi) | Sistem Login & Filter Autentikasi |
| 05 | [Modul 5](#modul-5--pagination--fitur-pencarian) | Pagination & Fitur Pencarian |
| 06 | [Modul 6](#modul-6--relasi-antar-tabel--query-builder) | Relasi Antar Tabel & Query Builder |
| 07 | [Modul 7](#modul-7--manajemen-upload-gambar) | Manajemen Upload Gambar |
| 08 | [Modul 8](#modul-8--implementasi-ajax) | Implementasi AJAX |
| 09 | [Modul 9](#modul-9--ajax-dinamis-pagination--pencarian) | AJAX Dinamis: Pagination & Pencarian |
| 10 | [Modul 10](#modul-10--pengembangan-restful-api) | Pengembangan RESTful API |
| 11 | [Modul 11](#modul-11--integrasi-vue-js-3) | Integrasi Vue.js 3 |
| 12 | [Modul 12](#modul-12--spa-dengan-vue-router) | SPA dengan Vue Router |
| 13 | [Modul 13](#modul-13--autentikasi-pada-spa) | Autentikasi pada SPA |
| 14 | [Modul 14](#modul-14--keamanan-api-berbasis-token) | Keamanan API Berbasis Token |

---

## 🔧 Stack Teknologi

![PHP](https://img.shields.io/badge/PHP-8.x-777BB4?logo=php&logoColor=white)
![CodeIgniter](https://img.shields.io/badge/CodeIgniter-4.x-EF4223?logo=codeigniter&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-8.x-4479A1?logo=mysql&logoColor=white)
![Vue.js](https://img.shields.io/badge/Vue.js-3.x-4FC08D?logo=vue.js&logoColor=white)
![jQuery](https://img.shields.io/badge/jQuery-3.6-0769AD?logo=jquery&logoColor=white)
![Axios](https://img.shields.io/badge/Axios-1.x-5A29E4?logo=axios&logoColor=white)

---

## 💻 Kebutuhan Sistem

- PHP versi 8.0 atau lebih baru
- MySQL / MariaDB
- XAMPP (Apache + MySQL)
- Composer
- Node.js *(opsional, untuk tooling frontend)*
- Postman *(untuk pengujian API)*

---

## 🚀 Panduan Instalasi

### Langkah 1 – Clone Repositori
```bash
git clone https://github.com/<username>/<repo-name>.git
cd <repo-name>
```

### Langkah 2 – Konfigurasi Environment
```bash
# Duplikat file env
cp env .env

# Buka .env lalu ubah baris berikut:
CI_ENVIRONMENT = development
```

### Langkah 3 – Konfigurasi Koneksi Database
Edit bagian ini di file `.env`:
```
database.default.hostname = localhost
database.default.database = db_newshub
database.default.username = root
database.default.password =
database.default.DBDriver = MySQLi
```

### Langkah 4 – Siapkan Database
```sql
CREATE DATABASE db_newshub;
```
```bash
php spark db:seed UserSeeder
```

### Langkah 5 – Jalankan Development Server
```bash
php spark serve
```
Akses di browser: `http://localhost:8080`

---

## 🗂️ Struktur Proyek

```
newshub/
├── app/
│   ├── Controllers/
│   │   ├── Artikel.php
│   │   ├── Page.php
│   │   ├── User.php
│   │   ├── AjaxController.php
│   │   └── Api/
│   │       ├── Post.php
│   │       └── Auth.php
│   ├── Models/
│   │   ├── ArtikelModel.php
│   │   ├── UserModel.php
│   │   └── KategoriModel.php
│   ├── Views/
│   │   ├── layout/
│   │   │   └── main.php
│   │   ├── template/
│   │   │   ├── header.php
│   │   │   └── footer.php
│   │   ├── artikel/
│   │   │   ├── index.php
│   │   │   ├── detail.php
│   │   │   ├── admin_index.php
│   │   │   ├── form_add.php
│   │   │   └── form_edit.php
│   │   ├── user/
│   │   │   └── login.php
│   │   ├── components/
│   │   │   └── artikel_terkini.php
│   │   └── ajax/
│   │       └── index.php
│   ├── Cells/
│   │   └── ArtikelTerkini.php
│   ├── Filters/
│   │   ├── Auth.php
│   │   └── ApiAuthFilter.php
│   └── Config/
│       ├── Routes.php
│       └── Filters.php
├── public/
│   ├── index.php
│   ├── style.css
│   ├── gambar/
│   └── assets/
│       └── js/
│           └── jquery-3.6.0.min.js
├── frontend-vue/              ← Aplikasi Vue.js SPA
│   ├── index.html
│   └── assets/
│       ├── css/
│       │   └── style.css
│       └── js/
│           ├── app.js
│           └── components/
│               ├── Home.js
│               ├── Artikel.js
│               ├── Login.js
│               └── About.js
├── .env
└── spark
```

---

## 📘 Dokumentasi Modul

### Modul 1 – MVC dan Routing Dasar

**Tujuan:** Memahami arsitektur MVC dan cara kerja routing pada CodeIgniter 4.

**Konsep Inti:**
- **Model** – lapisan data dan logika bisnis aplikasi
- **View** – lapisan antarmuka yang dilihat pengguna
- **Controller** – penghubung antara Model dan View

**Yang Dikerjakan:**
- Instalasi dan konfigurasi awal CI4
- Pembuatan routing manual dan auto-routing
- Controller `Page` untuk halaman statis (about, contact, faqs)
- Pembuatan template global: `header.php` & `footer.php`

---

### Modul 2 – Operasi CRUD Artikel

**Tujuan:** Membangun fitur Create, Read, Update, Delete untuk data artikel.

**Struktur Tabel:**
```sql
CREATE TABLE artikel (
    id      INT(11) AUTO_INCREMENT PRIMARY KEY,
    judul   VARCHAR(200) NOT NULL,
    isi     TEXT,
    gambar  VARCHAR(200),
    status  TINYINT(1) DEFAULT 0,
    slug    VARCHAR(200)
);
```

**Yang Dikerjakan:**
- `ArtikelModel` menggunakan fitur bawaan CI4
- Halaman daftar artikel untuk pengunjung umum
- Halaman detail artikel berbasis slug URL
- Panel admin: tambah, edit, dan hapus artikel

---

### Modul 3 – Layout Tampilan & View Cell

**Tujuan:** Memusatkan pengelolaan tampilan menggunakan sistem Layout dan membuat komponen modular dengan View Cell.

**Perbandingan Pendekatan:**

| Aspek | Partial Include | View Layout |
|-------|-----------------|-------------|
| Cara kerja | Menyisipkan potongan file | View anak mewarisi template induk |
| Kemudahan perawatan | Perlu ubah banyak file | Cukup ubah satu file layout |

**Yang Dikerjakan:**
- File layout utama `app/Views/layout/main.php`
- Penggunaan `extend()`, `section()`, dan `endSection()`
- Class `ArtikelTerkini` sebagai View Cell untuk widget sidebar

---

### Modul 4 – Sistem Login & Filter Autentikasi

**Tujuan:** Melindungi halaman admin dengan sistem autentikasi berbasis sesi.

**Alur Autentikasi:**
```
Akses /admin → Filter periksa sesi → Belum login → Redirect ke /user/login
                                   → Sudah login → Lanjut ke Controller
```

**Yang Dikerjakan:**
- Tabel `user` dengan password di-hash (`password_hash`)
- `UserModel` dan Controller `User`
- Auth Filter sebagai middleware pelindung rute admin
- Database Seeder untuk membuat akun awal
- Fitur logout yang menghancurkan sesi aktif

---

### Modul 5 – Pagination & Fitur Pencarian

**Tujuan:** Memecah daftar artikel menjadi beberapa halaman dan menambahkan fungsionalitas pencarian.

**Implementasi Utama:**
```php
// Pagination + Search dalam satu pemanggilan
$artikel = $model->like('judul', $q)->paginate(10);
$pager   = $model->pager;
```

**Yang Dikerjakan:**
- Pagination dengan 10 artikel per halaman
- Form pencarian berdasarkan judul artikel
- Kata kunci pencarian tetap dipertahankan saat berpindah halaman

---

### Modul 6 – Relasi Antar Tabel & Query Builder

**Tujuan:** Menerapkan relasi One-to-Many antara tabel kategori dan artikel.

**Diagram Relasi:**
```
kategori (1) ───────────── (Many) artikel
id_kategori (PK)           id_kategori (FK)
```

**Yang Dikerjakan:**
- Tabel `kategori` dengan foreign key di tabel `artikel`
- `KategoriModel`
- Query JOIN menggunakan Query Builder CI4
- Filter artikel berdasarkan kategori di panel admin

---

### Modul 7 – Manajemen Upload Gambar

**Tujuan:** Menambahkan fitur upload gambar pada form input artikel.

**Alur Upload:**
```
Form (enctype multipart) → getFile() → move() → Simpan nama ke DB → Tampilkan via base_url
```

**Aturan Validasi File:**
```php
'gambar' => 'uploaded[gambar]|is_image[gambar]|max_size[gambar,2048]'
```

**Pertimbangan Keamanan:**

| Risiko | Solusi |
|--------|--------|
| File berbahaya diunggah | Validasi tipe MIME & ekstensi |
| Nama file tabrakan | Gunakan metode `$file->store()` |
| Ukuran file terlalu besar | Terapkan validasi `max_size` |

---

### Modul 8 – Implementasi AJAX

**Tujuan:** Melakukan operasi data tanpa reload halaman menggunakan AJAX dan jQuery.

**Cara Kerja:**
```
Event (klik/input) → Request JS (GET/POST) → Server Proses → Response JSON → DOM Diperbarui
```

**Yang Dikerjakan:**
- `AjaxController` dengan endpoint `getData()` dan `delete()`
- jQuery AJAX untuk load, tambah, edit, dan hapus data secara real-time

---

### Modul 9 – AJAX Dinamis: Pagination & Pencarian

**Tujuan:** Mengintegrasikan pagination dan pencarian secara asinkron tanpa reload.

**Yang Dikerjakan:**
- Backend mendeteksi request AJAX via `isAJAX()` dan mengembalikan JSON
- Frontend merender tabel dan navigasi pagination secara dinamis
- Pencarian dan filter kategori langsung tanpa reload halaman
- Indikator loading saat proses pengambilan data

---

### Modul 10 – Pengembangan RESTful API

**Tujuan:** Membangun REST API yang dapat diakses oleh berbagai jenis client.

**Daftar Endpoint:**

| Method | Endpoint | Fungsi |
|--------|----------|--------|
| GET | `/post` | Mengambil semua artikel |
| GET | `/post/{id}` | Mengambil artikel berdasarkan ID |
| POST | `/post` | Menambahkan artikel baru |
| PUT | `/post/{id}` | Memperbarui artikel |
| DELETE | `/post/{id}` | Menghapus artikel |

Pendaftaran rute cukup satu baris:
```php
$routes->resource("post");
```

---

### Modul 11 – Integrasi Vue.js 3

**Tujuan:** Membangun frontend interaktif yang mengonsumsi REST API menggunakan Vue.js 3.

**Yang Dikerjakan:**
- Mengambil dan menampilkan daftar artikel dari API via Axios
- Modal form untuk menambah dan mengedit artikel
- Konfirmasi dan proses hapus artikel

---

### Modul 12 – SPA dengan Vue Router

**Tujuan:** Mengembangkan Single Page Application (SPA) menggunakan Vue Router.

**Peta Komponen:**
```
index.html
└── #app
    ├── <nav> (router-link)
    └── <router-view>
        ├── Home.js     → path: "/"
        ├── Artikel.js  → path: "/artikel"
        └── About.js    → path: "/about"
```

**Yang Dikerjakan:**
- Vue Router dengan `createWebHashHistory`
- Navigasi antar halaman tanpa reload browser
- Halaman About berisi profil mahasiswa

---

### Modul 13 – Autentikasi pada SPA

**Tujuan:** Melindungi halaman SPA menggunakan sistem login dan Navigation Guards.

**Alur Autentikasi:**
```
Login → Terima Token → Simpan di localStorage
      → Akses /artikel → Guard periksa isLoggedIn
                        → Belum login → Redirect /login
                        → Sudah login → Tampilkan halaman
```

**Yang Dikerjakan:**
- Komponen `Login.js` dengan form autentikasi
- Penyimpanan token dan status login di `localStorage`
- `router.beforeEach()` sebagai Navigation Guard
- Tombol logout kondisional di navbar

---

### Modul 14 – Keamanan API Berbasis Token

**Tujuan:** Mengamankan endpoint API di sisi server dan mengotomatisasi pengiriman token dari frontend.

**Arsitektur Keamanan End-to-End:**
```
[Vue.js] Login → Terima Token → Simpan di localStorage
               ↓
[Axios Interceptor] Sisipkan Header: Authorization: Bearer <token>
               ↓
[CI4 ApiAuthFilter] Validasi token → Izinkan / Tolak (401 Unauthorized)
```

**Perbandingan Keamanan Client vs Server:**

| Aspek | Vue Router Guards | CI4 API Filter |
|-------|-------------------|----------------|
| Lokasi eksekusi | Browser (sisi client) | Server |
| Objek perlindungan | Halaman/tampilan | Endpoint & data API |
| Bisa dibobol? | Ya (via DevTools) | Tidak |
| Fungsi utama | UX – mencegah akses halaman | Keamanan nyata – mencegah akses data |

---

## 🗄️ Skema Database Lengkap

```sql
-- Tabel Artikel
CREATE TABLE artikel (
    id           INT(11) AUTO_INCREMENT PRIMARY KEY,
    judul        VARCHAR(200) NOT NULL,
    isi          TEXT,
    gambar       VARCHAR(200),
    status       TINYINT(1) DEFAULT 0,
    slug         VARCHAR(200),
    id_kategori  INT(11),
    CONSTRAINT fk_kategori_artikel
        FOREIGN KEY (id_kategori) REFERENCES kategori(id_kategori)
);

-- Tabel Kategori
CREATE TABLE kategori (
    id_kategori   INT(11) AUTO_INCREMENT PRIMARY KEY,
    nama_kategori VARCHAR(100) NOT NULL,
    slug_kategori VARCHAR(100)
);

-- Tabel User
CREATE TABLE user (
    id           INT(11) AUTO_INCREMENT PRIMARY KEY,
    username     VARCHAR(200) NOT NULL,
    useremail    VARCHAR(200),
    userpassword VARCHAR(200)
);
```

---

## 🔑 Akun Default

| Field | Value |
|-------|-------|
| Email | `admin@email.com` |
| Password | `admin123` |

> ⚠️ Password disimpan dalam format hash menggunakan fungsi `password_hash()`.

---

## 📄 Lisensi

Proyek ini dikembangkan semata-mata untuk keperluan akademik dalam rangka Praktikum Pemrograman Web 2.  
**Universitas Pelita Bangsa, Bekasi** © 2024/2025
