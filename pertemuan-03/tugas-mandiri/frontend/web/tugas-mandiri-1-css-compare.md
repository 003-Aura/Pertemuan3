# Perbandingan CSS Component-Based dan Utility-First

## Data Kartu

Kedua versi menggunakan konten yang sama:

- Nama: Aura Illa Sari
- NIM: 2024520003
- Foto profil
- Tombol: Lihat Profil

## Versi Component-Based

Versi component-based menggunakan class `.card` dan `.btn` dengan CSS yang ditulis sendiri di dalam tag `<style>`.

Jumlah baris CSS yang dibuat sendiri: **45 baris CSS**.


## Versi Utility-First

Versi utility-first menggunakan Tailwind CSS melalui CDN. Tampilan kartu diatur menggunakan class utility tanpa menambahkan CSS atau atribut `style`.

Jumlah class utility yang digunakan pada kartu dan elemennya adalah **31 class utility**.

## Perbandingan

Pada percobaan saya, versi component-based lebih mudah digunakan ketika beberapa kartu memiliki tampilan yang sama karena cukup menggunakan class komponen yang sama. Versi utility-first lebih cepat untuk membuat tampilan sederhana karena perubahan dapat dilakukan langsung melalui class pada elemen.

Dari segi waktu, utility-first terasa lebih cepat karena tidak perlu membuat aturan CSS satu per satu. Namun, component-based lebih mudah dibaca ketika sebuah proyek memiliki banyak komponen dengan tampilan yang konsisten.

Untuk proyek akhir, saya memilih **component-based** karena proyek memiliki banyak komponen yang membutuhkan tampilan yang konsisten dan lebih mudah dikelola melalui class yang sudah dibuat.

## Kesimpulan

Pada versi component-based, perubahan warna kartu dilakukan melalui aturan CSS pada `.card` atau `.btn`. Pada versi utility-first, perubahan warna dilakukan dengan mengganti class utility seperti `bg-blue-600` atau `bg-blue-700` secara langsung pada elemen.