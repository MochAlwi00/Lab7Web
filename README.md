# Panduan Praktikum CodeIgniter 4 - Framework PHP

[![CodeIgniter](https://img.shields.io/badge/CodeIgniter-4.x-orange.svg)](https://codeigniter.com/)
[![PHP](https://img.shields.io/badge/PHP-7.4%2B-blue.svg)](https://php.net/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

## 📋 Daftar Isi

- [Lab 1: Pengenalan Framework CodeIgniter](#lab-1-pengenalan-framework-codeigniter)
- [Lab 2: Operasi CRUD dengan Database](#lab-2-operasi-crud-dengan-database)
- [Lab 3: Template Layout dan Komponen View](#lab-3-template-layout-dan-komponen-view)
- [Lab 4: Sistem Autentikasi](#lab-4-sistem-autentikasi)
- [Lab 5: Pagination dan Search System](#lab-5-pagination-dan-search-system)
- [Lab 6: File Upload Management](#lab-6-file-upload-management)
- [Lab 7: Database Relations dan Query Builder](#lab-7-database-relations-dan-query-builder)
- [Lab 8: AJAX Integration](#lab-8-ajax-integration)
- [Lab 9: Advanced AJAX Features](#lab-9-advanced-ajax-features)
- [Lab 10: REST API Development](#lab-10-rest-api-development)

## 🎯 Tujuan Pembelajaran

Setelah menyelesaikan praktikum ini, mahasiswa diharapkan mampu:
- Memahami konsep MVC (Model-View-Controller) dalam CodeIgniter 4
- Mengimplementasikan operasi CRUD dengan database
- Menerapkan sistem autentikasi dan autorisasi
- Menggunakan AJAX untuk interaksi dinamis
- Membangun REST API yang RESTful
- Mengelola file upload dan relasi database

## ⚙️ Persyaratan Sistem

- PHP 7.4 atau lebih tinggi
- Composer
- MySQL/MariaDB
- Web Server (Apache/Nginx)
- Browser modern dengan developer tools
- Postman (untuk testing API)

---

## Lab 1: Pengenalan Framework CodeIgniter

### 🎯 Objective
Memahami struktur dasar CodeIgniter 4 dan implementasi pattern MVC.

### 📝 Langkah-langkah

#### A. Setup Awal

1. **Aktivasi Extension PHP**
   ```bash
   # Pastikan extension berikut aktif di php.ini:
   extension=intl
   extension=mbstring
   extension=mysqli
   extension=curl
   ```
   ![Setup Extensions](screenshots/1.png)

2. **Download dan Instalasi CodeIgniter 4**
   ```bash
   composer create-project codeigniter4/appstarter lab_ci4
   cd lab_ci4
   ```
   ![Download CodeIgniter](screenshots/2.png)

3. **Konfigurasi Environment**
   ```bash
   # Rename file env menjadi .env
   cp env .env
   
   # Edit .env file
   CI_ENVIRONMENT = development
   ```
   ![Environment Config](screenshots/4.png)

4. **Menjalankan Development Server**
   ```bash
   php spark serve
   ```
   ![CLI Usage](screenshots/3.png)

#### B. Implementasi MVC Pattern

1. **Konfigurasi Routing** (`app/Config/Routes.php`)
   ```php
   <?php
   $routes->get('/', 'Home::index');
   $routes->get('/about', 'Page::about');
   $routes->get('/contact', 'Page::contact');
   $routes->get('/faq', 'Page::faq');
   $routes->get('/tos', 'Page::tos');
   ```
   ![Routes Configuration](screenshots/5.png)

2. **Pembuatan Controller** (`app/Controllers/Page.php`)
   ```php
   <?php

   namespace App\Controllers;

   class Page extends BaseController
   {
       public function about()
       {
           return view('about', [
               'title' => 'Halaman About'
           ]);
       }

       public function contact()
       {
           return view('contact', [
               'title' => 'Halaman Kontak'
           ]);
       }

       public function faq()
       {
           return view('faq', [
               'title' => 'FAQ'
           ]);
       }

       public function tos()
       {
           return view('tos', [
               'title' => 'Terms of Service'
           ]);
       }
   }
   ```
   ![Controller Creation](screenshots/6.png)

3. **Pembuatan View Template**

   **Header Template** (`app/Views/template/header.php`)
   ```php
   <!DOCTYPE html>
   <html lang="id">
   <head>
       <meta charset="UTF-8">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <title><?= $title ?? 'CodeIgniter 4' ?></title>
       <link rel="stylesheet" href="<?= base_url('css/style.css') ?>">
   </head>
   <body>
       <nav class="navbar">
           <div class="nav-container">
               <a href="<?= base_url('/') ?>" class="nav-logo">Lab CI4</a>
               <ul class="nav-menu">
                   <li><a href="<?= base_url('/') ?>">Home</a></li>
                   <li><a href="<?= base_url('/about') ?>">About</a></li>
                   <li><a href="<?= base_url('/contact') ?>">Contact</a></li>
                   <li><a href="<?= base_url('/faq') ?>">FAQ</a></li>
                   <li><a href="<?= base_url('/tos') ?>">Terms</a></li>
               </ul>
           </div>
       </nav>
   ```

   **Footer Template** (`app/Views/template/footer.php`)
   ```php
       <footer class="footer">
           <div class="container">
               <p>&copy; <?= date('Y') ?> Lab CodeIgniter 4. All rights reserved.</p>
           </div>
       </footer>
   </body>
   </html>
   ```

4. **View Pages**
   
   **About Page** (`app/Views/about.php`)
   ```php
   <?= $this->include('template/header') ?>

   <main class="main-content">
       <div class="container">
           <h1><?= $title ?></h1>
           <div class="content-section">
               <p>Ini adalah halaman about yang menjelaskan tentang aplikasi CodeIgniter 4.</p>
               <ul>
                   <li>Framework: CodeIgniter 4</li>
                   <li>PHP Version: <?= PHP_VERSION ?></li>
                   <li>Environment: <?= ENVIRONMENT ?></li>
               </ul>
           </div>
       </div>
   </main>

   <?= $this->include('template/footer') ?>
   ```

### 📊 Hasil Lab 1
- ✅ Setup environment berhasil
- ✅ Routing konfigurasi selesai
- ✅ Controller dan View terintegrasi
- ✅ Template system implementasi
- ✅ Navigasi menu berfungsi

![Final Result Lab 1](screenshots/14.png)

---

## Lab 2: Operasi CRUD dengan Database

### 🎯 Objective
Mengimplementasikan operasi Create, Read, Update, Delete dengan database MySQL.

### 🗄️ Setup Database

1. **Buat Database**
   ```sql
   CREATE DATABASE lab_ci4;
   USE lab_ci4;
   
   CREATE TABLE artikel (
       id INT(11) AUTO_INCREMENT PRIMARY KEY,
       judul VARCHAR(200) NOT NULL,
       isi TEXT NOT NULL,
       gambar VARCHAR(200),
       status TINYINT(1) DEFAULT 1,
       slug VARCHAR(200),
       created_at DATETIME,
       updated_at DATETIME
   );
   ```
   ![Database Creation](screenshots/praktikum2/1.png)

2. **Konfigurasi Database** (`.env`)
   ```env
   database.default.hostname = localhost
   database.default.database = lab_ci4
   database.default.username = root
   database.default.password = 
   database.default.DBDriver = MySQLi
   ```
   ![Database Configuration](screenshots/praktikum2/2.png)

### 📋 Implementasi Model

**ArtikelModel** (`app/Models/ArtikelModel.php`)
```php
<?php

namespace App\Models;

use CodeIgniter\Model;

class ArtikelModel extends Model
{
    protected $table = 'artikel';
    protected $primaryKey = 'id';
    protected $allowedFields = ['judul', 'isi', 'gambar', 'status', 'slug'];
    protected $useTimestamps = true;

    // Method untuk mendapatkan artikel yang published
    public function getPublishedArtikel()
    {
        return $this->where('status', 1)->findAll();
    }

    // Method untuk mendapatkan artikel by slug
    public function getArtikelBySlug($slug)
    {
        return $this->where('slug', $slug)->first();
    }
}
```
![Model Creation](screenshots/praktikum2/3.png)

### 🎮 Controller Development

**ArtikelController** (`app/Controllers/Artikel.php`)
```php
<?php

namespace App\Controllers;

use App\Models\ArtikelModel;
use CodeIgniter\Exceptions\PageNotFoundException;

class Artikel extends BaseController
{
    protected $artikelModel;

    public function __construct()
    {
        $this->artikelModel = new ArtikelModel();
    }

    public function index()
    {
        $data = [
            'title' => 'Daftar Artikel',
            'artikel' => $this->artikelModel->getPublishedArtikel()
        ];

        return view('artikel/index', $data);
    }

    public function view($slug)
    {
        $artikel = $this->artikelModel->getArtikelBySlug($slug);
        
        if (!$artikel) {
            throw PageNotFoundException::forPageNotFound();
        }

        $data = [
            'title' => $artikel['judul'],
            'artikel' => $artikel
        ];

        return view('artikel/detail', $data);
    }

    public function admin_index()
    {
        $data = [
            'title' => 'Kelola Artikel',
            'artikel' => $this->artikelModel->findAll()
        ];

        return view('artikel/admin_index', $data);
    }

    public function add()
    {
        if ($this->request->getMethod() === 'post') {
            $validation = \Config\Services::validation();
            
            $validation->setRules([
                'judul' => 'required|min_length[10]',
                'isi' => 'required|min_length[20]'
            ]);

            if ($validation->withRequest($this->request)->run()) {
                $slug = url_title($this->request->getPost('judul'), '-', true);
                
                $this->artikelModel->insert([
                    'judul' => $this->request->getPost('judul'),
                    'isi' => $this->request->getPost('isi'),
                    'slug' => $slug,
                    'status' => $this->request->getPost('status') ? 1 : 0
                ]);

                return redirect()->to('/artikel/admin')->with('success', 'Artikel berhasil ditambahkan');
            }
        }

        $data = [
            'title' => 'Tambah Artikel',
            'validation' => \Config\Services::validation()
        ];

        return view('artikel/form_add', $data);
    }

    public function edit($id)
    {
        $artikel = $this->artikelModel->find($id);
        
        if (!$artikel) {
            throw PageNotFoundException::forPageNotFound();
        }

        if ($this->request->getMethod() === 'post') {
            $validation = \Config\Services::validation();
            
            $validation->setRules([
                'judul' => 'required|min_length[10]',
                'isi' => 'required|min_length[20]'
            ]);

            if ($validation->withRequest($this->request)->run()) {
                $slug = url_title($this->request->getPost('judul'), '-', true);
                
                $this->artikelModel->update($id, [
                    'judul' => $this->request->getPost('judul'),
                    'isi' => $this->request->getPost('isi'),
                    'slug' => $slug,
                    'status' => $this->request->getPost('status') ? 1 : 0
                ]);

                return redirect()->to('/artikel/admin')->with('success', 'Artikel berhasil diupdate');
            }
        }

        $data = [
            'title' => 'Edit Artikel',
            'artikel' => $artikel,
            'validation' => \Config\Services::validation()
        ];

        return view('artikel/form_edit', $data);
    }

    public function delete($id)
    {
        $artikel = $this->artikelModel->find($id);
        
        if (!$artikel) {
            throw PageNotFoundException::forPageNotFound();
        }

        $this->artikelModel->delete($id);
        
        return redirect()->to('/artikel/admin')->with('success', 'Artikel berhasil dihapus');
    }
}
```

### 🎨 View Implementation

**Admin Index** (`app/Views/artikel/admin_index.php`)
```php
<?= $this->include('template/header') ?>

<main class="main-content">
    <div class="container">
        <div class="admin-header">
            <h1><?= $title ?></h1>
            <a href="<?= base_url('/artikel/add') ?>" class="btn btn-primary">
                <i class="fas fa-plus"></i> Tambah Artikel
            </a>
        </div>

        <?php if (session()->getFlashdata('success')): ?>
            <div class="alert alert-success">
                <?= session()->getFlashdata('success') ?>
            </div>
        <?php endif; ?>

        <div class="table-responsive">
            <table class="table">
                <thead>
                    <tr>
                        <th>No</th>
                        <th>Judul</th>
                        <th>Status</th>
                        <th>Created</th>
                        <th>Aksi</th>
                    </tr>
                </thead>
                <tbody>
                    <?php if (!empty($artikel)): ?>
                        <?php foreach ($artikel as $key => $item): ?>
                            <tr>
                                <td><?= $key + 1 ?></td>
                                <td>
                                    <strong><?= esc($item['judul']) ?></strong>
                                    <br>
                                    <small class="text-muted"><?= esc($item['slug']) ?></small>
                                </td>
                                <td>
                                    <span class="badge <?= $item['status'] ? 'badge-success' : 'badge-warning' ?>">
                                        <?= $item['status'] ? 'Published' : 'Draft' ?>
                                    </span>
                                </td>
                                <td><?= date('d M Y H:i', strtotime($item['created_at'])) ?></td>
                                <td>
                                    <div class="btn-group">
                                        <a href="<?= base_url('/artikel/' . $item['slug']) ?>" class="btn btn-sm btn-info" target="_blank">
                                            <i class="fas fa-eye"></i>
                                        </a>
                                        <a href="<?= base_url('/artikel/edit/' . $item['id']) ?>" class="btn btn-sm btn-warning">
                                            <i class="fas fa-edit"></i>
                                        </a>
                                        <a href="<?= base_url('/artikel/delete/' . $item['id']) ?>" class="btn btn-sm btn-danger" 
                                           onclick="return confirm('Yakin ingin menghapus artikel ini?')">
                                            <i class="fas fa-trash"></i>
                                        </a>
                                    </div>
                                </td>
                            </tr>
                        <?php endforeach; ?>
                    <?php else: ?>
                        <tr>
                            <td colspan="5" class="text-center">Belum ada artikel</td>
                        </tr>
                    <?php endif; ?>
                </tbody>
            </table>
        </div>
    </div>
</main>

<?= $this->include('template/footer') ?>
```

### 🎨 CSS Enhancement

**Style CSS** (`public/css/admin.css`)
```css
/* Admin Panel Styling */
.admin-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 2rem;
    padding-bottom: 1rem;
    border-bottom: 2px solid #e9ecef;
}

.table-responsive {
    background: white;
    border-radius: 8px;
    box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    overflow: hidden;
}

.table {
    margin-bottom: 0;
}

.table th {
    background-color: #f8f9fa;
    font-weight: 600;
    border: none;
    padding: 1rem;
}

.table td {
    padding: 1rem;
    vertical-align: middle;
}

.btn {
    padding: 0.5rem 1rem;
    border-radius: 4px;
    text-decoration: none;
    display: inline-block;
    font-weight: 500;
    text-align: center;
    transition: all 0.2s;
}

.btn-primary {
    background-color: #007bff;
    color: white;
    border: 1px solid #007bff;
}

.btn-primary:hover {
    background-color: #0056b3;
}

.badge {
    padding: 0.25em 0.6em;
    font-size: 0.75em;
    font-weight: 500;
    border-radius: 0.375rem;
}

.badge-success {
    background-color: #28a745;
    color: white;
}

.badge-warning {
    background-color: #ffc107;
    color: #212529;
}

.alert {
    padding: 0.75rem 1.25rem;
    margin-bottom: 1rem;
    border: 1px solid transparent;
    border-radius: 0.375rem;
}

.alert-success {
    color: #155724;
    background-color: #d4edda;
    border-color: #c3e6cb;
}
```

### 🚀 Fitur Enhancement

1. **Upload Gambar**
2. **Pencarian Artikel**
3. **Filter Status**
4. **Bulk Actions**

### 📊 Hasil Lab 2
![Final Result 1](screenshots/praktikum2/ss1.png)
![Final Result 2](screenshots/praktikum2/ss2.png)
![Final Result 3](screenshots/praktikum2/ss3.png)

---

## Lab 3: Template Layout dan Komponen View

### 🎯 Objective
Mengimplementasikan sistem template layout terpusat dan komponen view yang reusable.

### 🏗️ Arsitektur Layout

**Main Layout** (`app/Views/layout/main.php`)
```php
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title><?= $title ?? 'CodeIgniter 4' ?></title>
    <link rel="stylesheet" href="<?= base_url('css/bootstrap.min.css') ?>">
    <link rel="stylesheet" href="<?= base_url('css/style.css') ?>">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <?= $this->renderSection('head') ?>
</head>
<body>
    <!-- Navigation -->
    <nav class="navbar navbar-expand-lg navbar-dark bg-primary">
        <div class="container">
            <a class="navbar-brand" href="<?= base_url('/') ?>">
                <i class="fas fa-newspaper"></i> Portal Berita
            </a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarNav">
                <ul class="navbar-nav me-auto">
                    <li class="nav-item">
                        <a class="nav-link" href="<?= base_url('/') ?>">Home</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="<?= base_url('/artikel') ?>">Artikel</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="<?= base_url('/about') ?>">About</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" href="<?= base_url('/contact') ?>">Contact</a>
                    </li>
                </ul>
                <ul class="navbar-nav">
                    <li class="nav-item">
                        <a class="nav-link" href="<?= base_url('/admin') ?>">
                            <i class="fas fa-user-shield"></i> Admin
                        </a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>

    <!-- Main Content -->
    <main class="main-content">
        <?= $this->renderSection('content') ?>
    </main>

    <!-- Sidebar untuk artikel terkini -->
    <?php if (!empty($showSidebar)): ?>
        <aside class="sidebar">
            <div class="container">
                <div class="row">
                    <div class="col-md-4">
                        <?= view_cell('ArtikelTerkini::render', ['limit' => 5]) ?>
                    </div>
                </div>
            </div>
        </aside>
    <?php endif; ?>

    <!-- Footer -->
    <footer class="bg-dark text-light py-4 mt-5">
        <div class="container">
            <div class="row">
                <div class="col-md-6">
                    <h5>Portal Berita CodeIgniter 4</h5>
                    <p>Platform berita modern dengan teknologi terdepan.</p>
                </div>
                <div class="col-md-6 text-md-end">
                    <p>&copy; <?= date('Y') ?> All rights reserved.</p>
                    <div class="social-links">
                        <a href="#" class="text-light me-3"><i class="fab fa-facebook"></i></a>
                        <a href="#" class="text-light me-3"><i class="fab fa-twitter"></i></a>
                        <a href="#" class="text-light"><i class="fab fa-instagram"></i></a>
                    </div>
                </div>
            </div>
        </div>
    </footer>

    <script src="<?= base_url('js/bootstrap.bundle.min.js') ?>"></script>
    <?= $this->renderSection('scripts') ?>
</body>
</html>
```

### 🧩 View Cell Implementation

**ArtikelTerkini View Cell** (`app/Cells/ArtikelTerkini.php`)
```php
<?php

namespace App\Cells;

use CodeIgniter\View\Cells\Cell;
use App\Models\ArtikelModel;

class ArtikelTerkini extends Cell
{
    protected $artikelModel;

    public function __construct()
    {
        $this->artikelModel = new ArtikelModel();
    }

    public function render(array $params = []): string
    {
        $limit = $params['limit'] ?? 5;
        $kategori = $params['kategori'] ?? null;

        $query = $this->artikelModel->where('status', 1)
                                   ->orderBy('created_at', 'DESC');

        if ($kategori) {
            $query->where('kategori', $kategori);
        }

        $artikel = $query->limit($limit)->findAll();

        return view('components/artikel_terkini', [
            'artikel' => $artikel,
            'title' => $kategori ? "Artikel {$kategori} Terkini" : 'Artikel Terkini'
        ]);
    }
}
```

**View Component** (`app/Views/components/artikel_terkini.php`)
```php
<div class="card">
    <div class="card-header">
        <h5 class="card-title mb-0">
            <i class="fas fa-clock"></i> <?= $title ?>
        </h5>
    </div>
    <div class="card-body">
        <?php if (!empty($artikel)): ?>
            <div class="list-group list-group-flush">
                <?php foreach ($artikel as $item): ?>
                    <div class="list-group-item border-0 px-0">
                        <div class="d-flex">
                            <?php if (!empty($item['gambar'])): ?>
                                <img src="<?= base_url('uploads/' . $item['gambar']) ?>" 
                                     alt="<?= esc($item['judul']) ?>"
                                     class="rounded me-3" style="width: 60px; height: 60px; object-fit: cover;">
                            <?php endif; ?>
                            <div class="flex-grow-1">
                                <a href="<?= base_url('/artikel/' . $item['slug']) ?>" 
                                   class="text-decoration-none">
                                    <h6 class="mb-1"><?= esc($item['judul']) ?></h6>
                                </a>
                                <small class="text-muted">
                                    <i class="fas fa-calendar-alt"></i>
                                    <?= date('d M Y', strtotime($item['created_at'])) ?>
                                </small>
                            </div>
                        </div>
                    </div>
                <?php endforeach; ?>
            </div>
        <?php else: ?>
            <p class="text-muted">Belum ada artikel.</p>
        <?php endif; ?>
    </div>
</div>
```

### 📊 Database Enhancement

```sql
-- Menambahkan field timestamp dan kategori
ALTER TABLE artikel 
ADD COLUMN kategori VARCHAR(50) DEFAULT 'umum',
ADD INDEX idx_kategori (kategori),
ADD INDEX idx_status_created (status, created_at);
```

### 🎨 Refactoring Views

**Home View** (`app/Views/home.php`)
```php
<?= $this->extend('layout/main') ?>

<?= $this->section('content') ?>
<div class="container py-5">
    <!-- Hero Section -->
    <div class="row mb-5">
        <div class="col-12">
            <div class="hero-section bg-primary text-white rounded p-5 text-center">
                <h1 class="display-4 fw-bold mb-3">Selamat Datang di Portal Berita</h1>
                <p class="lead">Platform berita terpercaya dengan informasi terkini dan akurat</p>
                <a href="<?= base_url('/artikel') ?>" class="btn btn-light btn-lg">
                    <i class="fas fa-newspaper"></i> Baca Artikel
                </a>
            </div>
        </div>
    </div>

    <!-- Latest Articles -->
    <div class="row">
        <div class="col-md-8">
            <h2 class="mb-4">
                <i class="fas fa-fire text-danger"></i> Artikel Terpopuler
            </h2>
            <?= view_cell('ArtikelTerkini::render', ['limit' => 6]) ?>
        </div>
        <div class="col-md-4">
            <h3 class="mb-4">Kategori Populer</h3>
            <?= view_cell('ArtikelTerkini::render', ['kategori' => 'teknologi', 'limit' => 3]) ?>
            
            <div class="mt-4">
                <?= view_cell('ArtikelTerkini::render', ['kategori' => 'olahraga', 'limit' => 3]) ?>
            </div>
        </div>
    </div>
</div>
<?= $this->endSection() ?>

<?= $this->section('scripts') ?>
<script>
    // Custom JavaScript untuk home page
    console.log('Home page loaded successfully');
</script>
<?= $this->endSection() ?>
```

### 📋 Analisis Konseptual

#### Keunggulan View Layout:
1. **Konsistensi Interface** - Tampilan seragam di seluruh aplikasi
2. **DRY Principle** - Tidak ada duplikasi kode template
3. **Maintainability** - Perubahan layout hanya di satu tempat
4. **Flexibility** - Mudah menambah section baru
5. **Performance** - Caching template yang optimal

#### Perbandingan View Cell vs View Konvensional:

| Aspek | View Konvensional | View Cell |
|-------|------------------|-----------|
| **Reusability** | Terbatas pada satu halaman | Dapat digunakan dimana saja |
| **Logic Separation** | Logic di controller | Logic terpisah di cell |
| **Parameter Handling** | Manual via data array | Parameter method yang clean |
| **Caching** | Manual implementation | Built-in caching support |
| **Testing** | Sulit untuk unit test | Easy unit testing |

### 📊 Hasil Lab 3
![Final Result Lab 3](screenshots/praktikum3/ss3.png)

---

## Lab 4: Sistem Autentikasi

### 🎯 Objective
Mengimplementasikan sistem login/logout, proteksi halaman admin, dan manajemen session.

### 🗄️ Database Setup

```sql
CREATE TABLE users (
    id INT(11
