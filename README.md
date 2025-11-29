Tugas Sesi 6 – Implementasi Kriptografi
CRUD + XOR Stream Cipher + MySQL (Python)

Repository ini berisi implementasi tugas kriptografi untuk membuat aplikasi CLI sederhana yang melakukan operasi CRUD pada database MySQL. Semua data yang disimpan dalam database akan dienkripsi menggunakan metode stream cipher XOR.

===============================================================================

Fitur Aplikasi

Menambah data (nama, email, catatan)

Melihat data (plaintext didekripsi otomatis)

Mengubah data

Menghapus data

Enkripsi menggunakan repeating-key XOR

Data tersimpan dalam bentuk ciphertext di kolom VARBINARY MySQL

===============================================================================

File dalam Repository

xor_crud.py : Program utama CRUD + enkripsi XOR

dump.sql : Struktur database MySQL (database: cryptotask, tabel: users)

Snapshot.pdf : (Opsional) berisi screenshot bukti program berjalan

===============================================================================

Cara Menjalankan Program

a. Menjalankan MySQL

Jika menggunakan XAMPP, buka XAMPP Control Panel

Klik tombol Start pada MySQL

b. Mengimport database
Melalui phpMyAdmin:

Buka http://localhost/phpmyadmin

Pilih tab Import

Pilih file dump.sql

Klik Go

Atau melalui terminal MySQL:
mysql -u root -p < dump.sql

c. Menginstall library Python
Pastikan Python sudah terpasang, lalu jalankan perintah:
pip install mysql-connector-python

d. Menjalankan program
Masuk ke folder tempat file berada lalu jalankan:
python xor_crud.py

Menu program akan tampil berisi:

Tambah Data

Lihat Semua Data

Update Data

Hapus Data

Keluar

===============================================================================

Penjelasan Enkripsi XOR

Program menggunakan enkripsi repeating-key XOR.

Plaintext diubah menjadi byte

Setiap byte di-XOR dengan key (key diulang terus)

Hasil XOR diencode base64 dan disimpan ke database

Saat menampilkan data, ciphertext di-decode lalu di-XOR ulang untuk mendapatkan plaintext

Contoh logika XOR pada program:
out = bytes([p[i] ^ KEY[i % len(KEY)] for i in range(len(p))])

Metode ini tidak aman untuk penggunaan produksi dan digunakan hanya untuk kepentingan tugas/latihan kriptografi.

===============================================================================

Struktur Database

Database : cryptotask
Tabel : users

Kolom:

id : INT AUTO_INCREMENT PRIMARY KEY

name : VARBINARY(512)

email : VARBINARY(512)

note : VARBINARY(2048)

Semua kolom selain id berisi ciphertext hasil enkripsi XOR.

===============================================================================

Contoh Output

Contoh data terenkripsi di MySQL:
name : JxYbCw==
email : JxYbCyMVCxxxx
note : BL4WCMxxxxx

Contoh data saat ditampilkan di aplikasi Python:
ID : 1
Nama : John
Email : John@gmail.com

Catatan : Agen rahasia 1998

===============================================================================

Identitas Pembuat

Nama : [Isi Nama Anda]
NIM : [Isi NIM Anda]
Mata Kuliah : Kriptografi
Tugas : Sesi 6 – Implementasi Kriptografi (CRUD + XOR Encryption)
