# Analisis Authentication dan Authorization
## Project E-Library



## 1. Peran Pengguna
Sistem E-Library memiliki tiga peran pengguna, yaitu:

1. **Admin**
   - Mengelola data buku.
   - Mengelola data user.
   - Melihat dashboard sistem.

2. **Petugas**
   - Mengelola proses peminjaman.
   - Mengelola proses pengembalian.
   - Mengelola data peminjaman.

3. **User**
   - Melakukan registrasi dan login menggunakan NIM.
   - Melihat dan mencari buku.
   - Melakukan peminjaman dan pengembalian.
   - Melihat riwayat peminjaman.



## 2. Fitur yang Tersedia
Fitur yang tersedia pada sistem E-Library antara lain:

1. Melihat daftar buku
2. Mencari buku
3. Melihat detail buku
4. Melakukan peminjaman buku
5. Melakukan pengembalian buku
6. Mengelola buku
7. Mengelola user
8. Mengelola peminjaman
9. Melihat riwayat peminjaman



## 3. Matriks Hak Akses
| **Fitur** | **Admin** | **Petugas** | **User** | **Endpoint** |
| :--- | :---: | :---: | :---: | :--- |
| Melihat daftar buku | ✅ | ✅ | ✅ | `GET /buku` |
| Mencari buku | ❌ | ❌ | ✅ | `GET /buku/search` |
| Melihat detail buku | ❌ | ❌ | ✅ | `GET /buku/:id` |
| Melakukan peminjaman buku | ❌ | ✅ | ✅ | `POST /peminjaman` |
| Melakukan pengembalian buku | ❌ | ✅ | ✅ | `PUT /peminjaman/:id/pengembalian` |
| Mengelola buku | ✅ | ❌ | ❌ | `POST /buku` |
| Mengelola user | ✅ | ❌ | ❌ | `PUT /user/:id` |
| Mengelola peminjaman | ❌ | ✅ | ❌ | `PUT /peminjaman/:id` |
| Melihat riwayat peminjaman | ❌ | ✅ | ✅ | `GET /peminjaman/riwayat` |

Keterangan:

- **✅** menunjukkan bahwa role memiliki izin untuk mengakses fitur tersebut.
- **❌** menunjukkan bahwa role tidak memiliki izin untuk mengakses fitur tersebut. Jika identitas pengguna sudah terverifikasi tetapi tidak memiliki izin, sistem memberikan respons `403 Forbidden`.
- Endpoint pada tabel merupakan rancangan endpoint yang digunakan untuk menggambarkan hak akses pada sistem E-Library.



## 4. Authentication dan Authorization
**Authentication (autentikasi)** adalah proses untuk memeriksa dan memastikan identitas pengguna. Pada E-Library, pengguna melakukan login menggunakan NIM dan kata sandi. Setelah berhasil login, pengguna mendapatkan token yang digunakan untuk mengakses endpoint yang dilindungi.

**Authorization (otorisasi)** adalah proses untuk memeriksa apakah pengguna yang identitasnya sudah terverifikasi memiliki hak untuk mengakses suatu fitur. Hak akses ditentukan berdasarkan peran pengguna, yaitu Admin, Petugas, dan User.

### Penggunaan Kode 401

Kode `401 Unauthorized` digunakan ketika pengguna mengakses endpoint yang dilindungi tanpa token atau menggunakan token yang tidak valid. Artinya, identitas pengguna belum berhasil diverifikasi.

Contoh:

User dengan NIM `2024520003` mencoba mengakses:

`POST /buku`

tanpa menyertakan token.

Hasil yang diharapkan:

`401 Unauthorized`

### Penggunaan Kode 403

Kode `403 Forbidden` digunakan ketika pengguna sudah memiliki token yang valid sehingga identitasnya berhasil diverifikasi, tetapi pengguna tersebut tidak memiliki hak akses terhadap fitur yang diminta.

Contoh:

User dengan NIM `2024520003` sudah login dan memiliki token yang valid. Kemudian User mencoba mengakses:

`POST /buku`

Endpoint tersebut digunakan untuk mengelola buku dan hanya dapat diakses oleh Admin. Karena identitas User valid tetapi role User tidak memiliki izin, maka hasil yang diharapkan adalah:

`403 Forbidden`

### Contoh Skenario Akses

Misalnya User memiliki NIM `2024520003`.

| **Keadaan** | **Pemeriksaan** | **Hasil yang diharapkan** |
| :--- | :--- | :--- |
| User tidak menyertakan token saat mengakses `POST /buku` | Identitas belum terverifikasi | `401` |
| User menyertakan token valid dan mengakses `GET /buku` | Identitas dan hak akses memenuhi aturan | Permintaan diizinkan |
| User menyertakan token valid dan mengakses `POST /buku` | Identitas valid, tetapi User tidak memiliki hak mengelola buku | `403` |



## 5. Risiko Jika Hanya Menggunakan requireAuth
Jika endpoint penambahan buku hanya menggunakan `requireAuth`, sistem hanya memeriksa apakah pengguna sudah login dan memiliki token yang valid. Tanpa `requireRole`, pengguna seperti User atau Petugas yang sudah login dapat mengakses endpoint `POST /buku` meskipun seharusnya fitur tersebut hanya dapat digunakan oleh Admin.



## Kesimpulan
Authentication digunakan untuk memastikan identitas pengguna, sedangkan authorization digunakan untuk menentukan hak akses pengguna terhadap fitur tertentu. Pada sistem E-Library, `401` digunakan ketika identitas pengguna belum terverifikasi, sedangkan `403` digunakan ketika identitas sudah terverifikasi tetapi pengguna tidak memiliki izin untuk mengakses fitur tersebut.