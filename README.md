Tugas Sesi 6 — Implementasi Kriptografi
### CRUD + XOR Stream Cipher + MySQL (Python)

Repository ini berisi implementasi tugas kriptografi untuk membuat aplikasi CLI sederhana yang melakukan operasi **CRUD** pada database **MySQL**, dengan data yang disimpan **terenkripsi** menggunakan metode **stream cipher XOR**.

---

Fitur Aplikasi
- Create data (nama, email, note)
- Read data (otomatis didekripsi sebelum ditampilkan)
- Update data
- Delete data
- Enkripsi XOR berbasis repeating key
- Penyimpanan ciphertext di database (kolom VARBINARY)

---

File dalam Repository
| File | Fungsi |
|------|--------|
| `xor_crud.py` | Program utama CRUD + enkripsi XOR |
| `dump.sql` | Struktur database MySQL (DB: `cryptotask`, tabel: `users`) |
| `Snapshot.pdf` | (Opsional) Bukti screenshot proses aplikasi |

---

## ⚙ Cara Menjalankan Program

### 1. Pastikan MySQL aktif
Jika memakai XAMPP:
- Jalankan **XAMPP Control Panel**
- Klik **Start** pada MySQL

### 2. Import database
Melalui phpMyAdmin:
1. Buka http://localhost/phpmyadmin
2. Klik **Import**
3. Pilih file `dump.sql`
4. Klik **Go**

Atau via terminal:
