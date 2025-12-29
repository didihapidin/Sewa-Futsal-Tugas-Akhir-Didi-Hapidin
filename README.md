# Didi Hapidin - 221011400763
# Sewa Futsal – Website Penyewaan Lapangan

Website ini digunakan untuk mengelola penyewaan lapangan futsal: dari melihat jadwal, melakukan pemesanan, hingga pengelolaan data oleh pengelola. Proyek ini ditujukan untuk berjalan di lingkungan PHP + MySQL (mis. XAMPP/Laragon/WAMP).

## Fitur Singkat
- Melihat ketersediaan jadwal lapangan
- Pemesanan/penyewaan lapangan
- Manajemen data oleh admin/operator
- Melihat Laporan 

## Persyaratan
- PHP 7.4+ (direkomendasikan 7.4–8.x)
- MySQL/MariaDB
- Web server lokal (XAMPP/Laragon/WAMP)
- Composer (opsional, jika ingin pengelolaan dependency tambahan)

## Struktur Proyek (ringkas)
- `db/futsalkita.sql` – Dump database
- `koneksi.php` – Konfigurasi koneksi database
- `admin/`, `operator/`, `member/` – Modul per peran pengguna (termasuk sendEmail)

## Instalasi Lokal (XAMPP)
1. Pindahkan folder proyek ke direktori web server Anda.
   - Contoh (XAMPP Windows): `C:/xampp/htdocs/sewa-futsal`
2. Jalankan Apache dan MySQL dari XAMPP Control Panel.
3. Buat dan impor database:
   - Buka phpMyAdmin: http://localhost/phpmyadmin
   - Buat database baru dengan nama: `futsalkita`
   - Import berkas: `db/futsalkita.sql`
4. Sesuaikan konfigurasi database bila perlu:
   - Buka `koneksi.php` dan set nilai berikut sesuai environment Anda:
     ```php
     $koneksi = mysqli_connect("localhost", "root", "");
     $select = mysqli_select_db($koneksi, "futsalkita");
     ```
   - Ganti host, user, password, dan nama database jika Anda tidak menggunakan default XAMPP.
5. Akses aplikasi melalui browser:
   - http://localhost/sewa-futsal

## Konfigurasi Email (opsional)
- Di dalam folder `admin/`, `operator/`, dan `member/` terdapat modul `sendEmail-v156`.
- Jika ingin menggunakan fitur email, sesuaikan pengaturan SMTP/library email pada modul tersebut sesuai kredensial email Anda.

## Troubleshooting
- Jika halaman tidak bisa terhubung ke database:
  - Pastikan MySQL aktif, database `futsalkita` sudah dibuat, dan impor SQL berhasil.
  - Pastikan `koneksi.php` memakai host/user/password yang benar.
- Jika port MySQL berbeda (bukan 3306), sesuaikan konfigurasi MySQL atau parameter koneksi.

## Lisensi
Proyek untuk tujuan pembelajaran/pengembangan. Sesuaikan lisensi sesuai kebutuhan Anda sebelum dipublikasikan.
