# Lab CodeIgniter 4 - Dokumentasi Praktikum

[![CodeIgniter 4](https://img.shields.io/badge/CodeIgniter-4.x-red.svg)](https://codeigniter.com/)
[![PHP](https://img.shields.io/badge/PHP-7.4%2B-blue.svg)](https://php.net/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

Repositori ini berisi dokumentasi lengkap dan implementasi praktikum pengembangan web menggunakan framework CodeIgniter 4. Praktikum ini dirancang untuk memberikan pemahaman komprehensif tentang pengembangan aplikasi web modern dengan arsitektur MVC.

## 📸 Preview Aplikasi

### Homepage
![Homepage](screenshots/homepage.png)
*Tampilan halaman utama dengan navigasi dan artikel terbaru*

### Admin Dashboard
![Admin Dashboard](screenshots/admin-dashboard.png)
*Dashboard admin dengan statistik dan manajemen konten*

### Artikel Management
![Artikel Management](screenshots/artikel-management.png)
*Interface manajemen artikel dengan fitur CRUD lengkap*

### Login Page
![Login Page](screenshots/login.png)
*Halaman login dengan form authentication*

### API Testing
![API Testing](screenshots/api-testing.png)
*Testing REST API menggunakan Postman*

## 📚 Daftar Isi

- [Preview Aplikasi](#-preview-aplikasi)
- [Persyaratan Sistem](#-persyaratan-sistem)
- [Instalasi](#-instalasi)
- [Struktur Praktikum](#-struktur-praktikum)
- [Fitur Utama](#-fitur-utama)
- [Penggunaan](#-penggunaan)
- [Screenshots](#-screenshots)
- [API Documentation](#-api-documentation)
- [Demo Video](#-demo-video)
- [Kontribusi](#-kontribusi)
- [Lisensi](#-lisensi)

## 🔧 Persyaratan Sistem

- **PHP**: 7.4 atau lebih tinggi
- **Database**: MySQL 5.7+ / PostgreSQL / SQLite
- **Web Server**: Apache/Nginx (opsional, bisa menggunakan built-in server)
- **Composer**: untuk dependency management
- **Node.js & NPM**: untuk asset management (opsional)

### Ekstensi PHP yang Diperlukan:
- `php-json`
- `php-mbstring`
- `php-mysqlnd`
- `php-xml`
- `php-intl`
- `php-curl`

## 🚀 Instalasi

### 1. Clone Repository
```bash
git clone https://github.com/username/lab-codeigniter4.git
cd lab-codeigniter4
```

### 2. Install Dependencies
```bash
composer install
```

### 3. Konfigurasi Environment
```bash
# Copy file environment
cp env .env

# Edit konfigurasi database
nano .env
```

### 4. Konfigurasi Database
```env
# Database Configuration
database.default.hostname = localhost
database.default.database = lab_ci4
database.default.username = root
database.default.password = 
database.default.DBDriver = MySQLi
```

### 5. Migrasi Database
```bash
# Jalankan migrasi
php spark migrate

# Seed data dummy (opsional)
php spark db:seed DatabaseSeeder
```

### 6. Menjalankan Aplikasi
```bash
# Development server
php spark serve

# Atau dengan port custom
php spark serve --port 8080
```

Aplikasi akan berjalan di `http://localhost:8080`

## 📖 Struktur Praktikum

### Praktikum 1: Pengenalan Framework
**Tujuan**: Memahami dasar-dasar CodeIgniter 4
- ✅ Instalasi dan konfigurasi
- ✅ Routing dan controller
- ✅ View dan layout dasar
- ✅ Template integration

![Praktikum 1](screenshots/praktikum1-homepage.png)

**Halaman yang dibuat**:
- Home
- About
- Contact
- FAQ
- Terms of Service

### Praktikum 2: Operasi CRUD
**Tujuan**: Implementasi Create, Read, Update, Delete
- ✅ Model dan database interaction
- ✅ Form handling
- ✅ Data validation
- ✅ Admin panel

![CRUD Operations](screenshots/praktikum2-crud.png)

**Fitur**:
- Manajemen artikel
- Upload gambar
- Pencarian artikel

### Praktikum 3: Layout & View Cell
**Tujuan**: Optimasi struktur view
- ✅ Layout template system
- ✅ View cells untuk komponen
- ✅ Sistem kategori

![Layout System](screenshots/praktikum3-layout.png)

**Komponen**:
- Main layout
- Artikel terkini widget
- Kategori filter

### Praktikum 4: Sistem Autentikasi
**Tujuan**: Implementasi login/logout
- ✅ User management
- ✅ Session handling
- ✅ Authentication filter
- ✅ Role-based access

![Authentication](screenshots/praktikum4-auth.png)

**Fitur**:
- Login/logout
- User registration
- Protected routes
- Admin dashboard

### Praktikum 5: Pagination & Search
**Tujuan**: Optimasi performa data
- ✅ Database pagination
- ✅ Advanced search
- ✅ Filter integration

![Pagination](screenshots/praktikum5-pagination.png)

**Fitur**:
- Pagination dengan navigasi
- Real-time search
- Category filtering

### Praktikum 6: File Upload
**Tujuan**: Manajemen file
- ✅ Image upload
- ✅ File validation
- ✅ Storage management

![File Upload](screenshots/praktikum6-upload.png)

**Fitur**:
- Multiple file formats
- File size validation
- Secure upload

### Praktikum 7: Database Relations
**Tujuan**: Relasi antar tabel
- ✅ Foreign key implementation
- ✅ JOIN queries
- ✅ Normalized database

![Database Relations](screenshots/praktikum7-relations.png)

**Struktur**:
- Tabel artikel
- Tabel kategori
- Tabel user
- Relasi One-to-Many

### Praktikum 8: Teknologi AJAX
**Tujuan**: Interaksi dinamis
- ✅ jQuery integration
- ✅ Asynchronous requests
- ✅ JSON responses

![AJAX Implementation](screenshots/praktikum8-ajax.png)

**Fitur**:
- Dynamic content loading
- Form submission tanpa reload
- Real-time updates

### Praktikum 9: AJAX Pagination
**Tujuan**: Pagination dinamis
- ✅ Seamless navigation
- ✅ Search integration
- ✅ Performance optimization

![AJAX Pagination](screenshots/praktikum9-ajax-pagination.png)

### Praktikum 10: REST API
**Tujuan**: API development
- ✅ RESTful endpoints
- ✅ JSON API responses
- ✅ HTTP methods (GET, POST, PUT, DELETE)

![REST API](screenshots/praktikum10-api.png)

## 🎯 Fitur Utama

### Frontend
- 📱 Responsive design
- 🎨 Modern CSS styling
- ⚡ AJAX interactions
- 🔍 Real-time search
- 📄 Pagination

### Backend
- 🏗️ MVC Architecture
- 🔐 Authentication system
- 📊 Database relationships
- 📁 File upload management
- 🔌 REST API endpoints

### Admin Panel
- 👤 User management
- 📝 Content management
- 📈 Dashboard analytics
- 🏷️ Category management
- 🔍 Advanced search

## 💻 Penggunaan

### Akses Aplikasi
- **Frontend**: `http://localhost:8080`
- **Admin Panel**: `http://localhost:8080/admin`

### Default Login Credentials
```
Username: admin
Password: admin123
```

### API Endpoints

#### Artikel API
```http
GET    /api/posts       # Get all articles
GET    /api/posts/{id}  # Get specific article
POST   /api/posts       # Create new article
PUT    /api/posts/{id}  # Update article
DELETE /api/posts/{id}  # Delete article
```

#### User API
```http
POST   /api/auth/login    # User login
POST   /api/auth/logout   # User logout
POST   /api/auth/register # User registration
```

### Testing API dengan Postman

1. Import collection dari `postman/Lab_CI4_API.postman_collection.json`
2. Set environment variables:
## 📸 Screenshots

### 🏠 Frontend Views

#### Homepage
![Homepage](screenshots/frontend/homepage.png)
*Halaman utama dengan artikel terbaru dan navigasi*

#### Detail Artikel
![Detail Artikel](screenshots/frontend/artikel-detail.png)
*Halaman detail artikel dengan konten lengkap*

#### About Page
![About Page](screenshots/frontend/about.png)
*Halaman about dengan informasi lengkap*

#### Contact Page
![Contact Page](screenshots/frontend/contact.png)
*Halaman kontak dengan form feedback*

### 🔐 Authentication

#### Login Form
![Login](screenshots/auth/login.png)
*Form login dengan validation*

#### Register Form
![Register](screenshots/auth/register.png)
*Form registrasi user baru*

#### Logout Success
![Logout](screenshots/auth/logout.png)
*Konfirmasi logout berhasil*

### 👨‍💼 Admin Panel

#### Dashboard
![Admin Dashboard](screenshots/admin/dashboard.png)
*Dashboard admin dengan statistik dan overview*

#### Artikel Management
![Artikel Management](screenshots/admin/artikel-list.png)
*Daftar artikel dengan fitur CRUD*

#### Add/Edit Artikel
![Add Artikel](screenshots/admin/artikel-add.png)
*Form tambah/edit artikel dengan upload gambar*

#### Kategori Management
![Kategori Management](screenshots/admin/kategori-list.png)
*Manajemen kategori artikel*

#### User Management
![User Management](screenshots/admin/user-management.png)
*Pengelolaan user dan role*

### 🔍 Search & Pagination

#### Search Results
![Search Results](screenshots/features/search-results.png)
*Hasil pencarian dengan highlight keyword*

#### Pagination
![Pagination](screenshots/features/pagination.png)
*Navigasi pagination dengan info halaman*

#### AJAX Pagination
![AJAX Pagination](screenshots/features/ajax-pagination.png)
*Pagination dinamis tanpa reload*

### 📁 File Upload

#### Upload Interface
![Upload Interface](screenshots/features/file-upload.png)
*Interface upload file dengan preview*

#### Upload Success
![Upload Success](screenshots/features/upload-success.png)
*Konfirmasi upload berhasil*

### 🔌 API Testing

#### Postman Collection
![Postman Collection](screenshots/api/postman-collection.png)
*Collection API endpoints di Postman*

#### GET Request
![GET Request](screenshots/api/get-request.png)
*Testing GET endpoint untuk mengambil data*

#### POST Request
![POST Request](screenshots/api/post-request.png)
*Testing POST endpoint untuk create data*

#### PUT Request
![PUT Request](screenshots/api/put-request.png)
*Testing PUT endpoint untuk update data*

#### DELETE Request
![DELETE Request](screenshots/api/delete-request.png)
*Testing DELETE endpoint untuk hapus data*

### 📱 Responsive Design

#### Mobile View
![Mobile View](screenshots/responsive/mobile-view.png)
*Tampilan mobile responsive*

#### Tablet View
![Tablet View](screenshots/responsive/tablet-view.png)
*Tampilan tablet landscape*

### ⚡ AJAX Features

#### Real-time Search
![Real-time Search](screenshots/ajax/realtime-search.png)
*Pencarian real-time dengan AJAX*

#### Dynamic Loading
![Dynamic Loading](screenshots/ajax/dynamic-loading.png)
*Loading konten dinamis*

#### Form Submission
![AJAX Form](screenshots/ajax/ajax-form.png)
*Submit form tanpa reload halaman*

## 📁 Struktur Direktori

```
lab-ci4/
├── app/
│   ├── Controllers/
│   │   ├── Home.php
│   │   ├── Page.php
│   │   ├── Artikel.php
│   │   ├── User.php
│   │   └── Api/
│   │       └── Post.php
│   ├── Models/
│   │   ├── ArtikelModel.php
│   │   ├── KategoriModel.php
│   │   └── UserModel.php
│   ├── Views/
│   │   ├── layout/
│   │   ├── artikel/
│   │   ├── admin/
│   │   └── auth/
│   ├── Cells/
│   │   └── ArtikelTerkini.php
│   └── Filters/
│       └── AuthFilter.php
├── public/
│   ├── css/
│   ├── js/
│   └── uploads/
├── database/
│   ├── migrations/
│   └── seeds/
└── README.md

## 📂 Screenshots Directory Structure

```
screenshots/
├── frontend/
│   ├── homepage.png
│   ├── artikel-detail.png
│   ├── about.png
│   └── contact.png
├── admin/
│   ├── dashboard.png
│   ├── artikel-list.png
│   ├── artikel-add.png
│   ├── kategori-list.png
│   └── user-management.png
├── auth/
│   ├── login.png
│   ├── register.png
│   └── logout.png
├── features/
│   ├── search-results.png
│   ├── pagination.png
│   ├── ajax-pagination.png
│   ├── file-upload.png
│   └── upload-success.png
├── api/
│   ├── postman-collection.png
│   ├── get-request.png
│   ├── post-request.png
│   ├── put-request.png
│   └── delete-request.png
├── responsive/
│   ├── mobile-view.png
│   └── tablet-view.png
├── ajax/
│   ├── realtime-search.png
│   ├── dynamic-loading.png
│   └── ajax-form.png
└── demo/
    └── demo-video-thumbnail.png
```
```

## 🧪 Testing

### Manual Testing
1. Test semua fitur CRUD
2. Verifikasi autentikasi
3. Test upload file
4. Validasi API endpoints

### Automated Testing
```bash
# Run PHPUnit tests
vendor/bin/phpunit

# Run with coverage
vendor/bin/phpunit --coverage-html coverage/
```

## 📋 TODO List

- [ ] Implementasi cache system
- [ ] Email verification
- [ ] Multi-language support
- [ ] Advanced logging
- [ ] Performance monitoring
- [ ] Unit testing coverage
- [ ] API rate limiting
- [ ] OAuth integration
- [ ] Real-time notifications
- [ ] Export data (PDF, Excel)
- [ ] Dark mode toggle
- [ ] Progressive Web App (PWA)

## 📊 Progress Tracking

### Development Status
![Progress](https://progress-bar.dev/95/?title=Overall%20Progress&color=green)

- ![100%](https://progress-bar.dev/100/?title=Basic%20Setup&color=success) Basic Setup & Configuration
- ![100%](https://progress-bar.dev/100/?title=CRUD&color=success) CRUD Operations
- ![100%](https://progress-bar.dev/100/?title=Auth&color=success) Authentication System  
- ![100%](https://progress-bar.dev/100/?title=Upload&color=success) File Upload
- ![100%](https://progress-bar.dev/100/?title=API&color=success) REST API
- ![90%](https://progress-bar.dev/90/?title=Testing&color=yellow) Testing Coverage
- ![80%](https://progress-bar.dev/80/?title=Documentation&color=blue) Documentation

## 🤝 Kontribusi

Kontribusi sangat diterima! Silakan buat issue atau pull request untuk:

1. Bug fixes
2. Feature enhancements
3. Documentation improvements
4. Code optimization

### Guidelines
1. Fork repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open Pull Request

## 📝 Changelog

### v1.0.0 (Latest)
- ✅ Complete CRUD operations
- ✅ Authentication system
- ✅ File upload functionality
- ✅ REST API implementation
- ✅ AJAX pagination
- ✅ Database relationships

## 📞 Support

Jika mengalami masalah atau memiliki pertanyaan:

1. 📋 Check [Issues](https://github.com/username/lab-ci4/issues)
2. 📖 Read [CodeIgniter Documentation](https://codeigniter.com/user_guide/)
3. 💬 Join [CodeIgniter Community](https://forum.codeigniter.com/)

## 📄 Lisensi

Project ini dilisensikan under MIT License - lihat file [LICENSE](LICENSE) untuk detail lengkap.

## 👨‍💻 Author

**Nama Developer**
- GitHub: [@username](https://github.com/username)
- Email: developer@example.com

## 🙏 Acknowledgments

- CodeIgniter Team untuk framework yang luar biasa
- Bootstrap untuk UI components
- jQuery untuk DOM manipulation
- Semua kontributor open source

---

**⭐ Jangan lupa untuk memberikan star jika project ini membantu!**
