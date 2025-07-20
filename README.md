# Dokumentasi Praktikum CodeIgniter 4

## Praktikum 1: Pengenalan PHP Framework (CodeIgniter 4)

### Proses Instalasi dan Konfigurasi

**Persiapan Lingkungan:**
- Mengaktivasi ekstensi PHP yang diperlukan untuk menjalankan CodeIgniter 4
- Mengunduh framework CodeIgniter 4 dan melakukan ekstraksi file

**Konfigurasi Dasar:**
- Menjalankan aplikasi melalui Command Line Interface (CLI)
- Mengkonfigurasi mode debugging dengan mengubah file `env` menjadi `.env`
- Membuat routing baru di file `Routes.php`

**Pengembangan Komponen:**
- Pembuatan controller `Page.php` untuk menangani logika aplikasi
- Pembuatan view `about.php` untuk tampilan halaman
- Implementasi layout web menggunakan CSS dengan template header dan footer

**Hasil Implementasi:**
- Halaman About, Contact, FAQ, dan Terms of Service telah dibuat
- Semua halaman menggunakan layout yang konsisten
- Navigasi header berfungsi dengan baik untuk semua menu

---

## Praktikum 2: Operasi CRUD (Create, Read, Update, Delete)

### Pengaturan Database

**Konfigurasi Database:**
- Pembuatan database `lab_ci4` dan tabel `artikel`
- Konfigurasi koneksi database di file `.env`

**Pengembangan Komponen MVC:**
- Pembuatan model `ArtikelModel.php` untuk operasi database
- Pembuatan controller `Artikel.php` untuk logika bisnis
- Pembuatan view `index.php` untuk menampilkan data

**Fitur yang Diimplementasikan:**
- Menampilkan daftar artikel
- Melihat detail artikel dengan routing khusus
- Panel admin untuk mengelola artikel
- Fungsi tambah, edit, dan hapus artikel

**Pengembangan Tambahan:**
- Penambahan CSS untuk mempercantik admin panel
- Implementasi fitur upload gambar
- Fitur pencarian artikel

---

## Praktikum 3: Layout dan View Cell

### Sistem Layout

**Implementasi Layout:**
- Pembuatan layout utama di folder `layout/main.php`
- Modifikasi semua file view untuk menggunakan layout terpusat
- Penambahan field tanggal (`created_at`) pada database

**View Cell untuk Komponen:**
- Pembuatan class `ArtikelTerkini.php` di folder `Cells`
- Pembuatan view cell `artikel_terkini.php` di folder `components`
- Implementasi sistem kategori artikel dengan filter

**Analisis Konsep:**

*Manfaat View Layout:*
- Konsistensi tampilan di seluruh aplikasi
- Pemisahan yang jelas antara konten dan struktur
- Kemudahan maintenance dan pengembangan
- Reusability kode yang tinggi

*Perbedaan View Cell vs View Biasa:*
- View Cell: Komponen modular dengan logika bisnis tersendiri
- View Biasa: Template sederhana untuk menampilkan data
- View Cell lebih cocok untuk komponen yang sering digunakan ulang

---

## Praktikum 4: Sistem Autentikasi

### Implementasi Login System

**Persiapan Database:**
- Pembuatan tabel `user` dengan field yang diperlukan
- Pembuatan model `UserModel.php` untuk operasi user

**Komponen Autentikasi:**
- Controller `User.php` dengan method login dan logout
- View `login.php` dengan form autentikasi
- Database seeder untuk data pengguna dummy

**Sistem Keamanan:**
- Implementasi Auth Filter untuk proteksi halaman admin
- Konfigurasi filter di file konfigurasi
- Tombol logout untuk mengakhiri sesi

**Fitur Tambahan:**
- Halaman registrasi untuk pengguna baru
- Dashboard admin dengan statistik
- Perbaikan tampilan dengan CSS yang lebih menarik

---

## Praktikum 5: Pagination dan Pencarian

### Sistem Pagination

**Implementasi Pagination:**
- Modifikasi controller untuk mendukung pagination
- Konfigurasi jumlah data per halaman
- Pembuatan navigasi halaman di view

**Fitur Pencarian:**
- Form pencarian di admin panel
- Integrasi pencarian dengan pagination
- Pencarian berdasarkan judul dan konten artikel

**Pengembangan Lanjutan:**
- Filter pencarian berdasarkan kategori
- Tampilan jumlah data yang ditemukan
- Optimasi query untuk performa lebih baik

---

## Praktikum 6: Upload File

### Sistem Upload Gambar

**Konfigurasi Upload:**
- Modifikasi method `add()` untuk menangani file upload
- Penyesuaian form dengan `enctype="multipart/form-data"`
- Validasi file gambar dan ukuran file

**Implementasi:**
- Field input file di form tambah artikel
- Penyimpanan file ke direktori yang ditentukan
- Penyimpanan nama file di database

**Testing:**
- Ujicoba upload berbagai format gambar
- Verifikasi penyimpanan file dan database

---

## Praktikum 7: Relasi Database

### Konsep Relasi Tabel

**Perancangan Database:**
- Pembuatan tabel `kategori` dengan primary key
- Penambahan foreign key `id_kategori` di tabel `artikel`
- Implementasi relasi One-to-Many

**Model dan Query:**
- Pembuatan `KategoriModel.php`
- Modifikasi `ArtikelModel` dengan method JOIN
- Query builder untuk mengambil data berelasi

**Tampilan Data:**
- Modifikasi semua view untuk menampilkan kategori
- Widget kategori di sidebar
- Filter artikel berdasarkan kategori

---

## Praktikum 8: Teknologi AJAX

### Implementasi AJAX

**Persiapan Framework:**
- Integrasi pustaka jQuery ke proyek
- Pembuatan `AjaxController.php` untuk request AJAX
- Konfigurasi routing khusus AJAX

**Fitur AJAX:**
- Loading data tanpa refresh halaman
- Operasi CRUD dengan AJAX
- Response dalam format JSON

**Pengembangan Lanjutan:**
- Pencarian real-time dengan AJAX
- Filter kategori dinamis
- Indikator loading untuk user experience

---

## Praktikum 9: AJAX Pagination

### Pagination Dinamis

**Implementasi Lanjutan:**
- AJAX pagination tanpa reload halaman
- Search real-time dengan debouncing
- Filter kategori dengan AJAX

**Fitur Tambahan:**
- Sorting kolom tabel
- Export data dalam berbagai format
- Interface yang responsif dan user-friendly

**Optimasi:**
- Caching query untuk performa
- Lazy loading untuk data besar
- Error handling yang komprehensif

---

## Praktikum 10: REST API

### Pengembangan API

**Persiapan Tools:**
- Instalasi Postman untuk testing API
- Konfigurasi database untuk endpoint API

**Controller REST:**
- Pembuatan `Post.php` controller dengan resource routing
- Implementasi method GET, POST, PUT, DELETE
- Response dalam format JSON standar

**Testing Endpoint:**
- GET: Mengambil semua data dan data spesifik
- POST: Menambah data baru
- PUT: Mengubah data existing
- DELETE: Menghapus data

**Validasi API:**
- Testing dengan Postman menunjukkan semua endpoint berfungsi
- Response code yang sesuai standar HTTP
- Error handling untuk request yang tidak valid

---

## Kesimpulan Keseluruhan

Rangkaian praktikum ini memberikan pemahaman komprehensif tentang pengembangan web dengan CodeIgniter 4, mulai dari konsep dasar MVC, operasi CRUD, sistem autentikasi, hingga pengembangan API modern. Setiap praktikum membangun fondasi untuk praktikum selanjutnya, menciptakan aplikasi web yang lengkap dan fungsional.

**Keterampilan yang Dikuasai:**
- Arsitektur MVC dan routing
- Operasi database dan relasi tabel
- Sistem autentikasi dan otorisasi
- Teknologi modern seperti AJAX dan REST API
- Best practices dalam pengembangan web
