# Tugas Pendahuluan Pertemuan 03

## Soal 1 — Bandingkan Bootstrap dan Tailwind

Bootstrap menggunakan class komponen seperti `card`, `card-body`, `card-title`, dan `btn btn-primary` untuk membuat kartu dan tombol. Tailwind menggunakan class utility seperti `bg-white`, `rounded-lg`, `shadow`, `p-4`, serta `bg-blue-500`, `text-white`, dan `px-4` untuk tombol. Menurut saya, Bootstrap lebih mudah untuk pemula karena komponen seperti card dan button sudah tersedia dan siap digunakan.

## Soal 2 — Rancang Kartu Biodata

Sketsa kartu biodata:

```text
┌─────────────────────────┐
│         [ FOTO ]        │
│                         │
│     Aura Illa Sari      │
│     NIM: 2024520003     │
│                         │
│       [ Detail ]        │
└─────────────────────────┘
```

**Versi komponen (Bootstrap):**

```html
<div class="card">
  <img src="foto.jpg" class="card-img-top" alt="Foto">
  <div class="card-body">
    <h5 class="card-title">Aura Illa Sari</h5>
    <p class="card-text">NIM: 2024520003</p>
    <button class="btn btn-primary">Detail</button>
  </div>
</div>
```

Jumlah aturan CSS yang perlu ditulis sendiri pada versi komponen adalah **0**, karena Bootstrap sudah menyediakan aturan CSS untuk komponen tersebut.

**Versi utility (Tailwind):**

```html
<div class="w-72 bg-white rounded-lg shadow p-4">
  <img src="foto.jpg" class="w-full h-48 object-cover rounded" alt="Foto">
  <h2 class="text-xl font-bold mt-4">Aura Illa Sari</h2>
  <p class="text-gray-600">NIM: 2024520003</p>
  <button class="bg-blue-500 text-white px-4 py-2 rounded mt-3">Detail</button>
</div>
```

Versi utility tersebut menggunakan **19 class utility**. Versi **Tailwind lebih mudah diubah warnanya** karena warna dapat langsung diganti melalui class utility seperti `bg-blue-500` menjadi `bg-red-500`.

## Soal 3 — Amati Isi Token

JWT tersebut memiliki **3 bagian**, yaitu header, payload, dan signature. Pada payload terlihat data `sub`, `name`, dan `iat`.

Password tidak boleh disimpan di dalam payload JWT karena isi payload dapat di-decode sehingga bukan tempat yang aman untuk menyimpan data rahasia. Password sebaiknya disimpan sebagai hash di database.

## Soal 4 — Analogi Gerbang Kampus

Pemeriksaan identitas di gerbang UNIRA merupakan contoh **authentication**, karena bertujuan memastikan siapa orang yang masuk. Pemeriksaan di depan ruang server merupakan **authorization**, yaitu memastikan apakah orang tersebut memiliki izin masuk; contohnya mahasiswa berhasil teridentifikasi tetapi tidak memiliki izin masuk ke ruang server.

## Soal 5 — Peran di Aplikasi Nyata

Saya memilih **GitHub**, dengan peran **Owner, Collaborator, dan Public User**; salah satu fitur yang hanya dapat digunakan oleh Owner adalah menghapus repository. Pengguna yang belum login mendapat **401 Unauthorized**, sedangkan pengguna yang sudah login tetapi tidak memiliki izin mendapat **403 Forbidden**, karena identitasnya sudah diketahui tetapi aksesnya tidak diizinkan.
