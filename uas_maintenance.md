UNIVERSITAS PERSATUAN ISLAM
             UNIPI - PSDKU CISURUPAN

1.	ANALISIS PEMBUATAN ULANG DOKUMENTASI PEMELIHARAAN (MAINTENANCE DOCUMENTATION) DARI SEBUAH APLIKASI PERANGKAT LUNAK OPEN-SOURCE YANG KOMPLEKS 
Nama Aplikasi				    : Sistem Informasi Perpustakaan Berbasis Web
Versi					        : 2.4
Repository / URL			    : https://github.com/nurullatifahscoups/uas_maintenance.git
Nama Penyusun			        : Nurul Latifah
Tanggal Pembuatan Dokumentasi	: 20 Juni 2025

2.	Deskripsi Umum Aplikasi
Tujuan utama website Sistem Informasi Perpustakaan dirancang adalah untuk mengotomatisasi dan mempermudah pengelolaan, serta akses koleksi peminjaman & pengembalian buku dan layanan perpustakaan, meningkatkan efisiensi operasional dan kualitas layanan bagi anggota dan staf.
Fitur-fitur utama pada website Sistem Informasi Perpustakaan meliputi:
•	Manajemen Anggota: Yaitu fitur bagi admin perpustakaan untuk mendata informasi anggota perpustakaan seperti menambahkan anggota perpustakaan, mengedit anggota perpustakaan, menghapus anggota perpustakaan serta admin bisa mencetakan kartu anggota perpustakaan.
•	Manajemen Koleksi Buku: Fitur ini memungkinkan admin perpustakaan untuk menambah, mengedit, menghapus, dan mengelola detail setiap koleksi buku seperti ISBN, sampul buku, judul buku, kategori, pengarang, penerbit, tahun terbit, jumlah buku, jumlah peminjam, keteragan lainnya (tipe buku dan bahasa yang digunakan) Lokasi penyimpanan buku, lampiran serta tanggal masuk buku tersebut ke perpustakaan.
•	Manajemen Kategori: Fitur ini berfungsi untuk menambahkan kategori baru untuk buku, terutama saat ada buku baru yang masuk ke perpustakaan dan belum memiliki kategori yang sesuai.. Selain menambahkan, admin juga dapat menghapus dan mengedit kategori tersebut.
•	Manajemen Rak : Yaitu sama hal-nya dengan fitur manajemen kategori. Admin bisa menambahn mengedit, dan menghapus data rak.
•	Pencarian dan Penelusuran Koleksi: Pengguna (anggota dan staf) dapat mencari koleksi berdasarkan berbagai kriteria 
•	Sirkulasi (Peminjaman & Pengembalian): Fitur inti untuk mencatat proses peminjaman dan pengembalian koleksi buku, termasuk tanggal peminjaman, tanggal jatuh tempo, dan denda keterlambatan jika ada.
•	Riwayat Peminjaman dan Pengembalian: Pengguna dapat melihat riwayat peminjaman dan pengembalian mereka sendiri, dan staf dapat melihat riwayat peminjaman dan pengembalian semua anggota.
•	Manajemen Denda: Sistem untuk menghitung dan melacak denda keterlambatan pengembalian koleksi.
•	Dashboard Admin/Staff: Antarmuka khusus untuk staf perpustakaan yang menyediakan ringkasan aktivitas, dan akses cepat ke fitur-fitur manajemen.
•	Data Anggota: Anggota bisa mengedit datanya sendiri.
•	Cetak kartu anggota: fitur ini berfungsi untuk pengguna atau anggota yang igin mencetak kartu anggotanya. Pengguna/anggota hanya dapat mencetak kartu anggotanya sendiri.

Website Sistem Informasi Perpustakaan menggunakan teknologi:
•	bahasa pemrograman PHP,
•	Codeigniter 3,
•	Bootstrap 4,
•	dan databasenya menggunakan XAMPP-MySQL.

Lingkungan operasional aplikasi website Sistem Informasi Perpustakaan berada di server berbasis Linux. Pengaksesan aplikasi oleh pengguna dilakukan melalui browser web di berbagai sistem operasi dan perangkat.

3.	Struktur Direktori dan File
application/
config/ #koneksi database
	      config.php #pegaturan dasar (base_url, dan laim-lain) 
		      database.php #menyimpan semua parameter koneksi ke database
		      routes.php #routing halaman
	controllers/ #pusat kendali logika aplikasi web
	models/ #akses dan manipulasi data
	views/ #tampilan User Interface
            assets_style/ #css, js, file gambar
            index.php #entry point aplikasi
            .htaccess #pengaturan url rewrite

4.	Instruksi Instalasi dan Konfigurasi
Berikut Instruksi instalansi untuk menjalankan aplikasi website Sistem Informasi Perpustakaan:
1)	Download code dari GitHub
2)	Pastikan sudah meng-install XAMPP, VSCode 
3)	Salin WinRar ZIP yang telah didownload dari GitHub ke xampp/htdocs/
4)	Extract ZIP tersebut.
5)	Buka XAMPP
6)	Aktifkan Apache dan MySQL
7)	Buat database dengan nama “projek_perpus” di phpMyAdmin
8)	Import file projek_perpus.sql ke database
9)	Buka folder aplikasi di VSCode
10)	Edit application/config/database.php:
php
'hostname' => 'localhost',
'username' => 'root',
'password' => '',
'database' => 'projek_perpus'
**karena isi database.php sudah benar, maka tidak perlu diedit
11)	Edit application/config/config.php → ubah base_url (jika perlu)
12)	Jalankan aplikasi di browser dengan mengetikkan: http://localhost/perpus/ 

5.	Dependency yang Digunakan
•	CodeIgniter 3 - Framework PHP MVC    
•	Bootstrap 4 - Desain antarmuka (UI) 
•	FontAwesome - Menampilkan ikon grafis
•	XAMPP 8.2.12 - Interaksi database MySQL  
•	VSCode – untuk menuliskan kode

6.	Instruksi Build dan Deployment
Tidak ada proses build karena PHP interpreted.
Deployment ke Hosting:
•	Upload semua file ke public_html via cPanel atau FTP.
•	Buat database dan import .sql ke hosting (melalui phpMyAdmin).
•	Ubah konfigurasi database:
'hostname' => 'localhost',
'username' => 'nama_user_hosting',
'password' => 'password_hosting',
'database' => 'nama_db_hosting',
•	Ubah base_url di application/config/config.php menjadi URL hosting:
$config['base_url'] = 'https://domainanda.com/';

7.	Panduan Debugging dan Logging
Debugging:
•	Aktifkan error reporting: index.php (set ENVIRONMENT ke development).
•	Gunakan log_message('error', 'Pesan error'); untuk mencatat kesalahan.
Logging:
•	Buat file log.txt untuk mencatat aktivitas penting
•	Format log: [timestamp] LEVEL – pesan
•	Contoh: 2025-06-18 10:00:01 INFO - User admin login berhasil
Tools Pendukung:
•	Chrome DevTools : Cek konsol error HTML/JS.
•	phpMyAdmin : Validasi data dan relasi.
•	Postman : Jika nanti mengembangkan API backend.
•	CI Profiler: untuk memeriksa query dan performa halaman

8.	Change Log
Versi	Tanggal	Perubahan
1.0.0	16-6-2025	Rilis awal
1.1.0		
1.2.0		




9.	Bug Dikenal
a.	Foto tidak terupdate
Ketika ingin mengupdate foto lalu mengklik edit data, foto baru yang sudah kita pilih tidak terupdate.
b.	Notifikasi "Berhasil Update..."
Setelah kita melakukan edit pada sebuah data, otifikasi “Berhasil Update….” masih muncul saat mengklik fitur lain.

10.	Saran Pengembangan Selanjutnya
1)	Fitur QR code untuk scan buku
2)	Reservasi/Pemesanan: Anggota dapat memesan koleksi yang sedang dipinjam oleh orang lain.
3)	Notifikasi: Sistem pengingat untuk anggota mengenai tanggal jatuh tempo peminjaman atau status reservasi.
4)	Laporan: Menyediakan laporan-laporan penting seperti daftar koleksi terlaris, daftar anggota aktif, laporan peminjaman per periode, dan statistik lainnya untuk analisis manajemen perpustakaan.
5)	Fitur registrasi untuk pengguna yang belum memliki akun.
6)	Fitur Kembali pada Data Buku Detail.




