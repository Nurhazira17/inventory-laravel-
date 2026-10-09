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

