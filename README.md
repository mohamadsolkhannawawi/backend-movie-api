# Backend Movie API

Proyek ini adalah sebuah REST API sederhana yang dibangun menggunakan Node.js dan Express.js untuk mengelola data film. API ini terhubung ke database MySQL untuk melakukan operasi CRUD (Create, Read, Update, Delete) pada data film.

## Teknologi yang Digunakan

-   **Node.js**: Lingkungan eksekusi untuk JavaScript di sisi server.
-   **Express.js**: Kerangka kerja web untuk Node.js yang mempermudah pembuatan API.
-   **MySQL2**: Driver MySQL untuk Node.js.
-   **dotenv**: Modul untuk memuat variabel lingkungan dari file `.env`.

## Cara Menjalankan Proyek

Ikuti langkah-langkah di bawah ini untuk menjalankan proyek di lingkungan lokal Anda.

### 1. Clone Repositori

Pertama, clone repositori ini dari GitHub ke mesin lokal Anda menggunakan perintah berikut:

```bash
git clone https://github.com/mohamadsolkhannawawi/backend-movie-api.git
cd backend-movie-api
```

### 2. Instalasi Dependensi

Setelah masuk ke direktori proyek, instal semua dependensi yang dibutuhkan dengan menjalankan:

```bash
npm install
```

### 3. Konfigurasi Environment (.env)

Buat file `.env` dengan menyalin dari file `.env.example`. File ini akan berisi konfigurasi untuk koneksi database Anda.

**Untuk pengguna Linux/macOS:**

```bash
cp .env.example .env
```

**Untuk pengguna Windows:**

```bash
copy .env.example .env
```

Selanjutnya, buka file `.env` dan sesuaikan isinya dengan konfigurasi database MySQL Anda.

```
# MySQL database configuration
MYSQL_HOST=127.0.0.1
MYSQL_USER=root
MYSQL_PASSWORD="SesuaikanPasswordAnda"
MYSQL_DATABASE=movie_app_db
```

### 4. Setup Database (MySQL dengan XAMPP)

Proyek ini memerlukan server MySQL. Anda bisa menggunakan XAMPP untuk menjalankannya dengan mudah.

1.  **Buat Database**: Buka phpMyAdmin dari panel kontrol XAMPP, lalu buat database baru dengan nama `movie_app_db` (atau nama yang Anda tentukan di file `.env`).

2.  **Buat Tabel dan Isi Data**: Jalankan query SQL berikut untuk membuat tabel `movies` dan mengisinya dengan beberapa data awal.

    ```sql
    -- 1. Buat ulang tabelnya
    CREATE TABLE movies (
      id INT PRIMARY KEY AUTO_INCREMENT,
      title VARCHAR(255) NOT NULL,
      director VARCHAR(255),
      release_year INT
    );

    -- 2. Masukkan datanya
    INSERT INTO movies (title, director, release_year)
    VALUES
    ('The Shawshank Redemption', 'Frank Darabont', 1994),
    ('The Godfather', 'Francis Ford Coppola', 1972),
    ('The Dark Knight', 'Christopher Nolan', 2008);
    ```

### 5. Jalankan Server

Setelah semua konfigurasi selesai, jalankan server API dengan perintah:

```bash
npm start
```

Server akan berjalan di `http://localhost:8080`.

## Koleksi Postman

Untuk memudahkan pengujian endpoint API, Anda dapat menggunakan koleksi Postman yang sudah disiapkan. Impor koleksi melalui tautan berikut:

[Koleksi Postman Movie API](https://.postman.co/workspace/Personal-Project~8de014ec-8d43-44ac-be07-c0c5e10c2d87/collection/36177362-df978dc6-0956-4024-af2c-b46de31ab037?action=share&creator=36177362&active-environment=36177362-6895d87a-18a8-4c3f-98af-73a631bcff87)

Semoga berhasil!
