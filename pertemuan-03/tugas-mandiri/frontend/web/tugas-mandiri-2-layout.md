# Penjelasan Layout dengan Class Utility

## 1. Navbar
Class utama yang digunakan:

- `bg-white` : memberikan warna putih pada navbar.
- `shadow-md` : memberikan bayangan pada navbar.
- `max-w-6xl` : membatasi lebar maksimum konten.
- `mx-auto` : membuat konten berada di tengah.
- `px-5 py-4` : memberikan jarak bagian dalam secara horizontal dan vertikal.
- `flex` : menggunakan Flexbox untuk mengatur elemen.
- `gap-3` : memberikan jarak antar elemen.
- `md:flex-row` : pada layar medium, elemen navbar disusun secara horizontal.
- `md:items-center` : menyelaraskan elemen di tengah pada layar medium.
- `md:justify-between` : memberikan jarak antara logo dan menu.
- `hover:text-pink-600` : mengubah warna teks ketika mouse diarahkan ke menu.



## 2. Hero
Class utama yang digunakan:

- `bg-pink-100` : memberikan warna latar belakang pada hero.
- `max-w-6xl` : membatasi lebar konten.
- `mx-auto` : membuat konten berada di tengah.
- `px-5 py-12` : memberikan jarak di dalam section.
- `flex` : menggunakan Flexbox untuk mengatur teks dan foto.
- `flex-col` : menyusun elemen secara vertikal pada layar kecil.
- `gap-8` : memberikan jarak antar elemen.
- `md:flex-row` : mengubah susunan menjadi horizontal pada layar medium.
- `md:items-center` : membuat elemen berada di tengah secara vertikal.
- `md:flex-1` : memberikan ruang yang fleksibel pada bagian hero.
- `rounded-full` : membuat foto menjadi berbentuk lingkaran.
- `object-cover` : membuat gambar menyesuaikan area tanpa merusak proporsi.
- `shadow-md` : memberikan bayangan pada foto.
- `hover:bg-pink-600` : mengubah warna tombol ketika mouse diarahkan ke tombol.
- `hover:shadow-lg` : menambahkan bayangan pada tombol saat hover.



## 3. Tiga Content Cards
Class utama yang digunakan:

- `grid` : menggunakan CSS Grid untuk mengatur kartu.
- `grid-cols-1` : membuat kartu menjadi satu kolom pada layar kecil.
- `gap-5` : memberikan jarak antar kartu.
- `md:grid-cols-3` : membuat tiga kolom pada layar medium dan lebih besar.
- `bg-white` : memberikan warna putih pada kartu.
- `p-6` : memberikan jarak bagian dalam kartu.
- `rounded-xl` : membuat sudut kartu menjadi melengkung.
- `shadow-md` : memberikan bayangan pada kartu.
- `transition` : membuat perubahan tampilan menjadi lebih halus.
- `hover:-translate-y-1` : membuat kartu sedikit bergerak ke atas saat diarahkan mouse.
- `hover:shadow-lg` : membuat bayangan kartu lebih besar saat hover.

Tiga kartu yang dibuat adalah:

1. Biodata
2. Jadwal Kuliah
3. Kegiatan



## 4. Footer
Class utama yang digunakan:

- `bg-gray-800` : memberikan warna latar belakang gelap.
- `px-5 py-6` : memberikan jarak bagian dalam.
- `text-center` : membuat teks berada di tengah.
- `text-white` : membuat teks berwarna putih.



## 5. Responsive Layout
Pada layar kecil, hero menggunakan `flex-col` sehingga teks dan foto disusun ke bawah. Tiga kartu menggunakan `grid-cols-1` sehingga kartu ditampilkan satu per satu.

Pada layar yang lebih besar, digunakan `md:flex-row` pada hero dan `md:grid-cols-3` pada kelompok kartu. Dengan demikian, tiga kartu dapat ditampilkan dalam tiga kolom.


## 6. Kelebihan dan Kekurangan Utility Class
Penggunaan utility class lebih mudah untuk membuat layout sederhana karena setiap perubahan dapat dilakukan langsung melalui class pada elemen HTML. Pengaturan seperti jarak, ukuran, warna, posisi, dan responsive juga dapat dilakukan tanpa membuat file CSS tambahan. Namun, jika sebuah elemen memiliki banyak kebutuhan tampilan, rangkaian class dapat menjadi panjang dan lebih sulit dibaca. Pada tugas ini, bagian yang paling mudah dibuat dengan utility class adalah pengaturan grid tiga kartu, jarak antar elemen, dan responsive layout. Bagian yang cukup sulit dibaca adalah elemen yang memiliki banyak class sekaligus, terutama pada bagian hero dan kartu karena beberapa class digunakan untuk mengatur ukuran, posisi, responsive, dan efek hover secara bersamaan.