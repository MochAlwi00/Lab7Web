# Panduan Praktikum CodeIgniter 4 - Framework PHP

## Lab 1: Pengenalan Framework CodeIgniter

### Tahapan Implementasi

#### A. Setup Awal
- Aktivasi extension PHP yang diperlukan
  ![Setup Extensions](screenshots/1.png)
- Download dan ekstraksi CodeIgniter 4
  ![Download CodeIgniter](screenshots/2.png)
- Penggunaan Command Line Interface (CLI)
  ![CLI Usage](screenshots/3.png)
- Konfigurasi mode development dengan mengubah file env ke .env
  ![Environment Config](screenshots/4.png)

#### B. Implementasi MVC Pattern
- Pembuatan routing baru pada file Routes.php
  ![Routes Configuration](screenshots/5.png)
- Pengembangan Controller Page.php
  ![Controller Creation](screenshots/6.png)
- Pembuatan View about.php
  ![View Creation](screenshots/7.png)
- Design layout web menggunakan CSS dengan template header dan footer
  ![Layout Design](screenshots/81.png)
  ![Header Template](screenshots/82.png)
  ![Footer Template](screenshots/83.png)

#### C. Pengembangan Navigasi
Implementasi lengkap untuk menu navigasi meliputi:
- Halaman About
  ![About Page](screenshots/9.png)
- Halaman Contact
  ![Contact Page](screenshots/10.png)
- Halaman FAQ
  ![FAQ Page](screenshots/11.png)
- Halaman Terms of Service
  ![Terms Page](screenshots/12.png)
- Modifikasi controller untuk menangani semua halaman
  ![Controller Modification](screenshots/13.png)

#### Hasil Akhir Lab 1
![Final Result Lab 1](screenshots/14.png)

## Lab 2: Operasi CRUD dengan Database

### Implementasi Database
- Setup database lab_ci4 dan tabel artikel
  ![Database Creation](screenshots/praktikum2/1.png)
- Konfigurasi koneksi database melalui file .env
  ![Database Configuration](screenshots/praktikum2/2.png)
- Pembuatan Model ArtikelModel.php
  ![Model Creation](screenshots/praktikum2/3.png)
- Development Controller Artikel.php
  ![Controller Development](screenshots/praktikum2/4.png)
- Design View index.php untuk folder artikel
  ![View Design](screenshots/praktikum2/5.png)

### Fitur Manajemen Artikel
- Input data artikel via SQL
  ![Data Input](screenshots/praktikum2/6.png)
- Implementasi detail artikel dengan routing khusus
  ![Detail View Method](screenshots/praktikum2/71.png)
  ![Detail Template](screenshots/praktikum2/72.png)
  ![Detail Result](screenshots/praktikum2/73.png)
- Pembuatan panel admin dengan method admin_index()
  ![Admin Method](screenshots/praktikum2/81.png)
  ![Admin View](screenshots/praktikum2/82.png)
  ![Admin Interface](screenshots/praktikum2/83.png)
  ![Admin Panel](screenshots/praktikum2/84.png)
  ![Admin Result](screenshots/praktikum2/85.png)
- Fungsi tambah artikel dengan method add() dan form_add.php
  ![Add Method](screenshots/praktikum2/91.png)
  ![Add Form](screenshots/praktikum2/92.png)
- Fitur edit data dengan method edit() dan form_edit.php
  ![Edit Method](screenshots/praktikum2/101.png)
  ![Edit Form](screenshots/praktikum2/102.png)
- Implementasi hapus data dengan method delete()
  ![Delete Method](screenshots/praktikum2/11.png)

### Enhancement Tambahan
1. Styling CSS untuk Admin Panel
   ![CSS Styling](screenshots/praktikum2/css.png)
2. Feature upload gambar
   ![Upload Feature](screenshots/praktikum2/fitur1.png)
3. Sistem pencarian artikel
   ![Search Feature](screenshots/praktikum2/fitur2.png)

#### Hasil Akhir Lab 2
![Final Result 1](screenshots/praktikum2/ss1.png)
![Final Result 2](screenshots/praktikum2/ss2.png)
![Final Result 3](screenshots/praktikum2/ss3.png)

## Lab 3: Template Layout dan Komponen View

### Arsitektur Layout
- Pembuatan folder layout dengan file main.php sebagai template utama
  ![Layout Creation](screenshots/praktikum3/1.png)
- Refactoring seluruh view (home.php, about.php, contact.php, index.php, detail.php) untuk menggunakan layout terpusat
  ![Home View](screenshots/praktikum3/21.png)
  ![About View](screenshots/praktikum3/22.png)
  ![Contact View](screenshots/praktikum3/23.png)
  ![Index View](screenshots/praktikum3/24.png)
  ![Detail View](screenshots/praktikum3/25.png)

### Database Enhancement
- Penambahan field timestamp (created_at) pada tabel artikel
  ![Database Enhancement](screenshots/praktikum3/3.png)

### View Cell Implementation
- Pembuatan folder Cells dengan class ArtikelTerkini.php
  ![View Cell Class](screenshots/praktikum3/4.png)
- Development view komponen di folder components/artikel_terkini.php
  ![View Component](screenshots/praktikum3/5.png)
- Implementasi sistem kategorisasi artikel dengan filter
  ![Category Implementation](screenshots/praktikum3/61.png)
  ![Category Filter](screenshots/praktikum3/62.png)
  ![Category View](screenshots/praktikum3/63.png)
  ![Category Display](screenshots/praktikum3/64.png)
  ![Category Result](screenshots/praktikum3/65.png)

### Modifikasi View Cell dengan Parameter Kategori
- Modifikasi method render() untuk menerima parameter kategori
  ![View Cell Modification](screenshots/praktikum3/331.png)
- Pemanggilan View Cell dengan parameter kategori
  ![View Cell Call](screenshots/praktikum3/332.png)

#### Hasil Akhir Lab 3
![Final Result Lab 3](screenshots/praktikum3/ss3.png)

### Analisis Konseptual

**Keunggulan View Layout:**
1. **Uniformitas Interface**: Menjamin konsistensi tampilan di seluruh aplikasi
2. **Separation of Concerns**: Memisahkan struktur layout dari konten spesifik
3. **Code Reusability**: Template dapat digunakan berulang tanpa duplikasi
4. **Maintenance Efficiency**: Update layout hanya perlu dilakukan di satu lokasi
5. **Development Speed**: Fokus pengembangan pada konten tanpa mengulang struktur

**Perbandingan View Cell vs View Konvensional:**

| Aspek | View Konvensional | View Cell |
|-------|------------------|-----------|
| **Fungsi Utama** | Rendering halaman lengkap | Komponen UI modular |
| **Pemanggilan** | `return view()` | `view_cell()` |
| **Logic Business** | Minimal, data dari controller | Dapat memiliki logic sendiri |
| **Reusability** | Terbatas | Sangat fleksibel |
| **Isolation** | Share context | Konteks terpisah |

## Lab 4: Sistem Autentikasi

### Infrastructure Authentication
- Pembuatan tabel user di database
  ![User Table](screenshots/praktikum4/1.png)
- Development UserModel.php
  ![User Model](screenshots/praktikum4/2.png)
- Controller User.php dengan method login/logout
  ![User Controller](screenshots/praktikum4/3.png)
- Design interface login.php
  ![Login Interface](screenshots/praktikum4/41.png)
  ![Login View](screenshots/praktikum4/42.png)

### Security Implementation
- Database seeder untuk data dummy user
  ![User Seeder](screenshots/praktikum4/51.png)
  ![Seeder Configuration](screenshots/praktikum4/52.png)
  ![Seeder Execution](screenshots/praktikum4/53.png)
- Auth Filter untuk proteksi halaman admin
  ![Auth Filter](screenshots/praktikum4/61.png)
  ![Filter Configuration](screenshots/praktikum4/62.png)
  ![Filter Implementation](screenshots/praktikum4/63.png)
- Implementasi fungsi logout dengan session management
  ![Logout Function](screenshots/praktikum4/71.png)

### Feature Extension
1. Halaman registrasi user baru
   ![Register Page 1](screenshots/praktikum4/im11.png)
   ![Register Page 2](screenshots/praktikum4/im12.png)
   ![Register Page 3](screenshots/praktikum4/im13.png)

2. Dashboard admin dengan statistik
   ![Admin Dashboard 1](screenshots/praktikum4/im21.png)
   ![Admin Dashboard 2](screenshots/praktikum4/im22.png)
   ![Admin Dashboard 3](screenshots/praktikum4/im23.png)
   ![Admin Dashboard 4](screenshots/praktikum4/im24.png)

3. Enhancement UI dengan styling CSS
   ![CSS Enhancement](screenshots/praktikum4/im31.png)

#### Hasil Akhir Lab 4
![Final Result 1](screenshots/praktikum4/ss1.png)
![Final Result 2](screenshots/praktikum4/ss2.png)
![Final Result 3](screenshots/praktikum4/ss3.png)

## Lab 5: Pagination dan Search System

### Pagination Implementation
- Modifikasi Controller Artikel untuk pagination
  ![Pagination Controller](screenshots/praktikum5/1.png)
  ![Pagination Method](screenshots/praktikum5/2.png)
- Update view admin_index.php dengan navigasi halaman
  ![Pagination View](screenshots/praktikum5/3.png)

### Search Functionality
- Enhancement method `admin_index` dengan fitur pencarian
  ![Search Controller](screenshots/praktikum5/4.png)
  ![Search Method](screenshots/praktikum5/5.png)
- Implementasi form search di interface
  ![Search Form](screenshots/praktikum5/6.png)
  ![Search Interface](screenshots/praktikum5/7.png)
- Filter berdasarkan kategori dengan counter hasil
  ![Category Filter](screenshots/praktikum5/8.png)
  ![Search Enhancement](screenshots/praktikum5/9.png)

#### Hasil Akhir Lab 5
![Final Result Lab 5](screenshots/praktikum5/ss.png)

## Lab 6: File Upload Management

### Upload System
- Modifikasi method add() untuk handle file upload
  ![Upload Controller](screenshots/praktikum6/1.png)
- Update form_add.php dengan input file dan encryption type
  ![Upload Form](screenshots/praktikum6/2.png)
- Testing upload functionality dengan berbagai format gambar
  ![Upload Test 1](screenshots/praktikum6/31.png)
  ![Upload Test 2](screenshots/praktikum6/32.png)

#### Hasil Akhir Lab 6
![Final Result Lab 6](screenshots/praktikum6/ss6.png)

## Lab 7: Database Relations dan Query Builder

### Relational Database Design
- Pembuatan tabel kategori dengan struktur lengkap
  ![Category Table Creation](screenshots/praktikum7/1.png)
- Implementasi foreign key constraint ke tabel artikel
  ![Foreign Key Implementation](screenshots/praktikum7/2.png)
  ![Database Structure](screenshots/praktikum7/3.png)
  ![Relationship Setup](screenshots/praktikum7/4.png)
- Development KategoriModel.php
  ![Kategori Model](screenshots/praktikum7/5.png)

### Advanced Querying
- Modifikasi ArtikelModel dengan method JOIN
  ![Model Modification](screenshots/praktikum7/6.png)
- Update controller untuk menggunakan relasi tabel
  ![Controller Update](screenshots/praktikum7/7.png)
- Enhancement semua view untuk menampilkan data kategori
  ![View Enhancement 1](screenshots/praktikum7/8.png)
  ![View Enhancement 2](screenshots/praktikum7/9.png)
  ![View Enhancement 3](screenshots/praktikum7/10.png)
  ![View Enhancement 4](screenshots/praktikum7/11.png)
  ![View Enhancement 5](screenshots/praktikum7/12.png)
  ![View Enhancement 6](screenshots/praktikum7/13.png)
  ![View Enhancement 7](screenshots/praktikum7/14.png)

### Features Enhancement
- Testing dan validasi semua fitur
  ![Testing Result 1](screenshots/praktikum7/15.png)
  ![Testing Result 2](screenshots/praktikum7/16.png)
  ![Testing Result 3](screenshots/praktikum7/17.png)
  ![Testing Result 4](screenshots/praktikum7/18.png)
  ![Testing Result 5](screenshots/praktikum7/19.png)

#### Hasil Akhir Lab 7
![Final Result Lab 7](screenshots/praktikum7/ss.png)

## Lab 8: AJAX Integration

### AJAX Infrastructure
- Integrasi pustaka jQuery ke project
  ![jQuery Integration](screenshots/praktikum8/1.png)
- Pembuatan AjaxController.php untuk request handling
  ![AJAX Controller](screenshots/praktikum8/2.png)
- Konfigurasi routing khusus AJAX
  ![AJAX Routes](screenshots/praktikum8/3.png)

### Dynamic Functionality
- Implementasi view dengan AJAX loading
  ![AJAX View 1](screenshots/praktikum8/4.png)
  ![AJAX View 2](screenshots/praktikum8/5.png)
- Fitur pencarian real-time
- Filter kategori tanpa reload halaman

### Advanced Features
- Fungsi tambah dan edit data via AJAX
- Enhancement dengan search dan filter kategori

#### Hasil Akhir Lab 8
![Final Result Lab 8](screenshots/praktikum8/ss.png)

## Lab 9: Advanced AJAX Features

### Data Management
- Preparasi dataset besar untuk testing pagination
  ![Data Preparation](screenshots/praktikum9/1.png)
- Refactoring method admin_index() untuk AJAX support
  ![AJAX Controller Refactoring](screenshots/praktikum9/2.png)

### Interactive Interface
- Implementasi interface AJAX dengan fitur lengkap:
  - Search real-time implementation
  - Dynamic category filtering
  - Pagination tanpa reload halaman
  - Column sorting functionality
  ![Advanced AJAX Interface](screenshots/praktikum9/3.png)

### User Experience Enhancement
- Response time optimization
- Responsive interface design
- Advanced sorting dan export features

#### Hasil Akhir Lab 9
![Final Result Lab 9](screenshots/praktikum9/ss.png)

## Lab 10: REST API Development

### API Infrastructure
- Setup environment dengan Postman
  ![Environment Setup](screenshots/praktikum10/1.png)
- Database configuration untuk API
- Development REST Controller Post.php
  ![REST Controller](screenshots/praktikum10/2.png)

### API Endpoints Implementation
- Resource routing configuration
  ![API Routes](screenshots/praktikum10/3.png)
- Verifikasi routing dengan command line
  ![Routes Verification](screenshots/praktikum10/4.png)

### API Testing Results
- **GET All Data**: Retrieval semua artikel
  ![GET All Data](screenshots/praktikum10/5.png)
- **POST**: Penambahan artikel baru
  ![POST Request](screenshots/praktikum10/6.png)
- **GET by ID**: Retrieval artikel spesifik
  ![GET by ID](screenshots/praktikum10/7.png)
- **PUT**: Update artikel existing
  ![PUT Request](screenshots/praktikum10/8.png)
- **DELETE**: Penghapusan artikel
  ![DELETE Request](screenshots/praktikum10/9.png)

### API Response Format
Semua endpoint menggunakan JSON response format dengan proper HTTP status codes untuk error handling dan success responses.

## Kesimpulan Praktikum

Serangkaian praktikum ini memberikan pemahaman komprehensif tentang:
- Arsitektur MVC dalam CodeIgniter 4
- Database operations dan relational design
- Modern web development techniques (AJAX, REST API)
- Security implementation dengan authentication system
- UI/UX enhancement dengan responsive design
- Performance optimization dengan pagination dan caching

Implementasi praktikum ini menghasilkan aplikasi web full-featured dengan admin panel, sistem kategorisasi, file upload, dan API endpoints yang siap untuk deployment production.
