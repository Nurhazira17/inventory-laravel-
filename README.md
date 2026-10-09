# Inventory Management System — Web 5 Laravel Fundamental

Project ini adalah contoh implementasi Laravel untuk tugas Pertemuan 5. Fitur meliputi CRUD produk dan kategori, validasi form, pencarian, filter stok/kategori, pengurutan, pagination, migration, seeder, factory, dan relationship Eloquent.

## Persyaratan
- PHP 8.2 atau lebih baru
- Composer
- Ekstensi PHP yang dibutuhkan Laravel, termasuk PDO SQLite (untuk konfigurasi bawaan)
- Git (untuk mengunggah ke GitHub)

## Menjalankan project di komputer
1. Ekstrak folder project.
2. Jalankan `composer install`.
3. Salin `.env.example` menjadi `.env`.
4. Jalankan `php artisan key:generate`.
5. Buat file SQLite kosong `database/database.sqlite`.
6. Jalankan `php artisan migrate:fresh --seed`.
7. Jalankan `php artisan serve`.
8. Buka `http://127.0.0.1:8000`.

Project menggunakan SQLite sebagai konfigurasi awal supaya tidak perlu menyiapkan MySQL. Jika dosen mengharuskan MySQL, ubah konfigurasi `DB_*` di `.env` dan siapkan database `inventory_db`.

## Fitur utama
- Produk: daftar, detail, tambah, edit, hapus.
- Kategori: daftar, tambah, edit, hapus (kategori dengan produk tidak dapat dihapus).
- Validasi data di server.
- Pencarian berdasarkan nama/SKU.
- Filter berdasarkan kategori dan stok habis/menipis.
- Pengurutan nama/harga dan pagination.
- Relasi `Category hasMany Product` dan `Product belongsTo Category`.
- Status stok: Habis, Stok menipis, atau Tersedia.
- Blade layout, reusable form, CSRF token, dan escaping output.

## Struktur arsitektur
- `routes/web.php`: mendefinisikan URL dan resource routes.
- `app/Http/Controllers`: mengelola request, validasi, dan response.
- `app/Models`: model Eloquent dan relasi database.
- `database/migrations`: struktur tabel.
- `database/seeders`: data contoh awal.
- `database/factories`: generator data dummy.
- `resources/views`: tampilan Blade.

Alur aplikasi: **Request → Route → Controller → Model → Database → Response/View**.

## Mengunggah ke GitHub dari HP
1. Ekstrak ZIP project jika aplikasi file manager mendukungnya.
2. Buka GitHub di browser dan masuk ke akun.
3. Tekan `+` → `New repository`. Beri nama `inventory-laravel`, pilih Public/Private sesuai arahan dosen, lalu buat repository kosong (jangan centang README bila ingin mengunggah file yang sudah ada).
4. Buka repository → `Add file` → `Upload files`.
5. Pilih file dan folder project yang sudah diekstrak. Jika GitHub mobile tidak memungkinkan unggah banyak file/folder, buka GitHub dalam mode Desktop di browser atau gunakan GitHub Codespaces.
6. Tekan `Commit changes`.
7. Salin URL repository dan kirimkan sesuai instruksi pengumpulan.

**Catatan penting:** jangan mengunggah file `.env` asli atau folder `vendor`. Unggah `.env.example`, bukan kredensial lokal.

## Screenshot yang perlu disiapkan untuk pengumpulan
Sesuai instruksi tugas, ambil screenshot:
1. `php artisan route:list`
2. Halaman daftar produk dengan data contoh
3. Form tambah produk dan validasi input
4. Halaman kategori
5. Penjelasan struktur MVC/arsitektur project

## Catatan tentang P4
Materi menyebut P5 sebagai migrasi dari project P4. Karena source code P4 tidak disertakan bersama file materi yang diterima, project ini merupakan implementasi Inventory Management System Laravel yang berdiri sendiri dengan fitur inti yang sesuai materi. Jika dosen menuntut migrasi persis dari P4, sesuaikan field dan business rule dengan source code P4 asli.
