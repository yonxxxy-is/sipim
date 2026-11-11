# SIPIM

**Sistem Informasi dan Pengelolaan Inventaris Minimarket**

SIPIM adalah aplikasi berbasis web untuk membantu operasional toko atau minimarket. Aplikasi ini menyediakan pengelolaan produk dan stok, transaksi kasir, data pemasok, serta ringkasan penjualan dalam satu sistem.

## Fitur

- **Dashboard** — ringkasan dan grafik penjualan serta produk terlaris, dengan ekspor laporan PDF.
- **Kasir (POS)** — proses checkout dan pencatatan transaksi.
- **Produk dan kategori** — pengelolaan katalog dan informasi stok.
- **Transaksi** — melihat riwayat transaksi dan mengunduh data dalam format Excel.
- **Pemasok** — pengelolaan informasi pemasok.
- **Pengguna dan hak akses** — peran owner dan employee dengan akses fitur yang berbeda.
- **Pengaturan toko** — mengatur informasi toko dan mengimpor data menggunakan template.
- **Profil** — mengelola informasi akun dan foto profil.

## Teknologi

- PHP 8.2+, Laravel 11
- MySQL
- React 18, TypeScript, Inertia.js
- Tailwind CSS, Vite
- Laravel Excel, DomPDF

## Persiapan

Pastikan perangkat Anda telah memasang:

- PHP 8.2 atau lebih baru beserta ekstensi PHP yang dibutuhkan Laravel
- Composer
- Node.js 18 atau lebih baru dan npm
- MySQL

## Instalasi

1. Clone repository dan masuk ke folder project:

   ```bash
   git clone https://github.com/yonxxxy-is/sipim.git
   cd sipim
   ```

2. Pasang dependency:

   ```bash
   composer install
   npm install
   ```

3. Buat file `.env` di root project dan isi dengan konfigurasi minimum berikut. `APP_KEY` akan dibuat pada langkah selanjutnya:

   ```env
   APP_NAME=SIPIM
   APP_ENV=local
   APP_DEBUG=true
   APP_URL=http://localhost:8000
   APP_KEY=

   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=sipim
   DB_USERNAME=root
   DB_PASSWORD=
   ```

   Pastikan database `sipim` sudah dibuat di MySQL sebelum menjalankan migrasi.

4. Buat application key dan siapkan database:

   ```bash
   php artisan key:generate
   php artisan migrate --seed
   ```

5. Jalankan aplikasi. Buka dua terminal dari folder project:

   ```bash
   php artisan serve
   ```

   ```bash
   npm run dev
   ```

6. Buka [http://localhost:8000](http://localhost:8000).

## Akun demo lokal

Seeder menyediakan akun berikut untuk keperluan demonstrasi lokal:

| Peran | Email | Kata sandi |
|---|---|---|
| Owner | `owner@sipim.com` | `password` |
| Employee | `employee@sipim.com` | `password` |

Kredensial tersebut hanya untuk development/demo. Ganti atau hapus akun demo dan gunakan kata sandi yang kuat sebelum aplikasi dipakai di lingkungan bersama atau production.

## Perintah pengembangan

```bash
# Menjalankan server frontend
npm run dev

# Membuat asset frontend untuk production
npm run build

# Menjalankan migrasi database
php artisan migrate

# Mengisi data demo
php artisan db:seed
```

## Struktur project

```text
app/                 Controller, model, import, dan export
database/migrations/ Struktur tabel database
database/seeders/    Data awal dan data demo
resources/js/        Halaman dan komponen React/TypeScript
resources/views/     Template Blade, termasuk laporan PDF
routes/              Definisi route aplikasi
```

## Catatan

- Jangan membagikan file `.env` atau kredensial database.
- Data contoh dari seeder ditujukan untuk demonstrasi, bukan data operasional.
- Pastikan konfigurasi database dan environment telah disesuaikan sebelum deploy.
