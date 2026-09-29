# Praktikum 2 – HTML Lanjutan

Proyek ini berisi hasil praktikum **HTML Lanjutan** pada mata kuliah Pemrograman Web. Materi yang dipraktikkan: tabel, form, radio button & checkbox, select & textarea, validasi form, semantic HTML, dan multimedia (audio & video).

---

## 1. Struktur Proyek

```
yahuuuu/
├── index.html          # File utama (berisi seluruh latihan)
└── media/
    ├── musik.mpeg      # File audio
    └── video.mp4       # File video
```

| File / Folder | Keterangan |
|---|---|
| `index.html` | Halaman web utama tempat semua kode latihan ditulis |
| `media/` | Folder penyimpanan file multimedia |
| `media/musik.mpeg` | Audio yang diputar lewat tag `<audio>` |
| `media/video.mp4` | Video yang diputar lewat tag `<video>` |

> **Catatan:** Path pada atribut `src` harus sama persis dengan nama file di folder `media/` (`media/musik.mpeg` dan `media/video.mp4`), termasuk huruf besar/kecilnya.

---

## 2. Langkah Praktikum

### Langkah 1 – Membuat Tabel Data Mahasiswa
Membuat tabel sederhana berisi NIM, Nama, dan Program Studi menggunakan `<table>`, `<tr>`, `<th>`, dan `<td>`. Atribut `border="1"` dipakai agar garis tabel terlihat.

```html
<table border="1">
  <tr><th>NIM</th><th>Nama</th><th>Program Studi</th></tr>
  <tr><td>31241001</td><td>Andi</td><td>Teknik Informatika</td></tr>
  <tr><td>31241002</td><td>Budi</td><td>Teknik Informatika</td></tr>
</table>
```

### Langkah 2 – Mengembangkan Tabel dengan `thead`, `tbody`, `tfoot`
Tabel dibagi menjadi bagian kepala (`<thead>`), isi (`<tbody>`), dan kaki (`<tfoot>`), ditambah judul tabel dengan `<caption>`. Atribut `colspan="2"` dipakai pada baris "Rata-rata" untuk menggabungkan dua kolom.

```html
<table border="1">
  <caption>Nilai Praktikum</caption>
  <thead><tr><th>No</th><th>Nama</th><th>Nilai</th></tr></thead>
  <tbody>
    <tr><td>1</td><td>Andi</td><td>85</td></tr>
    <tr><td>2</td><td>Budi</td><td>90</td></tr>
  </tbody>
  <tfoot><tr><td colspan="2">Rata-rata</td><td>87.5</td></tr></tfoot>
</table>
```

### Langkah 3 – Membuat Form Registrasi Mahasiswa
Membuat form dengan berbagai tipe input: `text`, `email`, `password`, dan `date`. Setiap input dihubungkan dengan `<label>` melalui atribut `for` dan `id`. Ada tombol **Daftar** (`submit`) dan **Reset** (`reset`).

```html
<form>
  <label for="nama">Nama Lengkap</label><br>
  <input type="text" id="nama" name="nama"><br><br>
  <label for="email">Email</label><br>
  <input type="email" id="email" name="email"><br><br>
  <label for="password">Password</label><br>
  <input type="password" id="password" name="password"><br><br>
  <label for="tanggal">Tanggal Lahir</label><br>
  <input type="date" id="tanggal" name="tanggal"><br><br>
  <button type="submit">Daftar</button>
  <button type="reset">Reset</button>
</form>
```

### Langkah 4 – Radio Button dan Checkbox
- **Radio button** untuk Jenis Kelamin (hanya satu pilihan, semua radio memakai `name="jk"` yang sama).
- **Checkbox** untuk Keahlian (boleh memilih lebih dari satu: HTML, CSS, JavaScript).

```html
<h2>Jenis Kelamin</h2>
<input type="radio" id="laki" name="jk" value="L">
<label for="laki">Laki-laki</label>
<input type="radio" id="perempuan" name="jk" value="P">
<label for="perempuan">Perempuan</label>

<h2>Keahlian</h2>
<input type="checkbox" id="html" name="skill" value="HTML">
<label for="html">HTML</label>
<input type="checkbox" id="css" name="skill" value="CSS">
<label for="css">CSS</label>
<input type="checkbox" id="js" name="skill" value="JavaScript">
<label for="js">JavaScript</label>
```

### Langkah 5 – Select dan Textarea
`<select>` dipakai untuk dropdown pilihan Program Studi, sedangkan `<textarea>` untuk input teks panjang seperti alamat.

```html
<label for="prodi">Program Studi</label>
<select id="prodi" name="prodi">
  <option value="">-- Pilih Prodi --</option>
  <option value="ti">Teknik Informatika</option>
  <option value="si">Sistem Informasi</option>
</select>
<br><br>
<label for="alamat">Alamat</label><br>
<textarea id="alamat" name="alamat" rows="5" cols="40"></textarea>
```

### Langkah 6 – Validasi Form Dasar
Menambahkan validasi langsung di HTML tanpa JavaScript memakai atribut `required`, `minlength`, `min`, dan `max`.

```html
<form>
  <label for="nama">Nama</label>
  <input type="text" id="nama" name="nama" required minlength="3">
  <label for="email">Email</label>
  <input type="email" id="email" name="email" required>
  <label for="umur">Umur</label>
  <input type="number" id="umur" name="umur" min="17" max="60" required>
  <button type="submit">Kirim</button>
</form>
```

### Langkah 7 – Membuat Halaman Semantic HTML
Menyusun halaman Portal Mahasiswa dengan elemen semantik: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, dan `<footer>`.

```html
<body>
  <header><h1>Portal Mahasiswa</h1></header>
  <nav>
    <a href="#">Beranda</a>
    <a href="#">Profil</a>
    <a href="#">Kontak</a>
  </nav>
  <main>
    <section>
      <h2>Informasi Akademik</h2>
      <article>
        <h3>Praktikum HTML Lanjutan</h3>
        <p>Mahasiswa mempelajari tabel, form, semantic HTML, multimedia, dan validasi.</p>
      </article>
    </section>
    <aside>Informasi tambahan mahasiswa.</aside>
  </main>
  <footer><p>&copy; 2026 Teknik Informatika</p></footer>
</body>
```

### Langkah 8 – Menambahkan Multimedia
1. Buat folder `media/` di dalam folder proyek.
2. Masukkan file `musik.mpeg` dan `video.mp4` ke folder tersebut.
3. Tambahkan tag `<audio>` dan `<video>` pada `index.html`.

```html
<h2>Audio</h2>
<audio controls>
  <source src="media/musik.mpeg" type="audio/mpeg">
  Browser tidak mendukung audio.
</audio>

<h2>Video</h2>
<video controls width="480">
  <source src="media/video.mp4" type="video/mp4">
  Browser tidak mendukung video.
</video>
```

### Langkah 9 – Tugas Akhir: Halaman Biodata Mahasiswa
Menggabungkan semua materi menjadi satu halaman: semantic HTML (`header`, `nav`, `main`, `section`, `footer`), tabel biodata, dan form biodata dengan validasi `required`, `select`, `textarea`, serta tombol **Simpan** dan **Reset**. Menu navigasi memakai anchor internal (`#biodata`, `#form`).

### Cara Menjalankan
1. Ekstrak folder proyek.
2. Pastikan folder `media/` berisi `musik.mpeg` dan `video.mp4`.
3. Buka `index.html` dengan browser (Chrome, Firefox, Edge).
4. Uji tabel, form (coba kosongkan field `required`), serta putar audio dan video.

---

## 3. Jawaban Pertanyaan

### 1. Apa fungsi `<table>`, `<tr>`, `<th>`, dan `<td>`?
- `<table>` : membungkus seluruh tabel.
- `<tr>` (*table row*) : membuat satu baris di dalam tabel.
- `<th>` (*table header*) : sel judul kolom/baris; teksnya otomatis tebal dan rata tengah.
- `<td>` (*table data*) : sel yang berisi data biasa.

### 2. Apa perbedaan `<th>` dan `<td>`?
`<th>` adalah sel **judul/header** (default tebal dan rata tengah, bermakna semantik sebagai header sehingga membantu screen reader), sedangkan `<td>` adalah sel **data** biasa (default rata kiri dan tidak tebal).

### 3. Apa fungsi `colspan` pada tabel?
`colspan` menggabungkan beberapa kolom menjadi satu sel. Contoh: `<td colspan="2">Rata-rata</td>` membuat sel tersebut melebar menutupi dua kolom.

### 4. Apa fungsi `<form>` dalam HTML?
`<form>` adalah wadah untuk elemen input agar data dapat dikumpulkan dan dikirim ke server (atau diproses) saat tombol *submit* ditekan. Atribut penting: `action` (tujuan pengiriman data) dan `method` (GET/POST).

### 5. Apa perbedaan radio button dan checkbox?
| Radio button | Checkbox |
|---|---|
| Hanya boleh memilih **satu** opsi dalam satu grup | Boleh memilih **satu atau lebih** opsi |
| Grup dibuat dengan `name` yang sama | Biasanya tiap opsi bisa berdiri sendiri (`name` boleh sama untuk satu kelompok) |
| Cocok untuk jenis kelamin, metode pembayaran | Cocok untuk keahlian, hobi, persetujuan |

### 6. Mengapa `<label>` sebaiknya terhubung dengan `id` input melalui atribut `for`?
- Mengklik teks label otomatis memfokuskan/memilih input terkait (area klik lebih luas, terutama radio dan checkbox).
- Meningkatkan **aksesibilitas**: screen reader membacakan label saat input difokuskan.
- Hubungan antara label dan input menjadi jelas secara semantik.

### 7. Apa perbedaan `<textarea>` dengan `input type="text"`?
- `<input type="text">` : input **satu baris**, tag *self-closing*, nilai lewat atribut `value`.
- `<textarea>` : input **banyak baris**, punya tag penutup, ukuran diatur dengan `rows` dan `cols`, isi awalnya ditulis di antara tag pembuka dan penutup. Cocok untuk alamat, komentar, atau pesan panjang.

### 8. Apa fungsi semantic HTML seperti `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, dan `<footer>`?
- `<header>` : bagian kepala halaman/section (judul, logo).
- `<nav>` : kumpulan tautan navigasi/menu.
- `<main>` : konten utama halaman (hanya satu per halaman).
- `<section>` : pengelompokan konten berdasarkan topik/tema.
- `<article>` : konten mandiri yang bisa berdiri sendiri (berita, postingan blog).
- `<aside>` : konten tambahan/sampingan (sidebar, info terkait).
- `<footer>` : bagian kaki halaman/section (hak cipta, kontak).

Manfaatnya: struktur halaman lebih jelas, kode lebih mudah dibaca, lebih ramah SEO, dan lebih mudah diakses oleh pembaca layar.

### 9. Apa fungsi `required`, `min`, `max`, dan `minlength`?
- `required` : field wajib diisi sebelum form dapat dikirim.
- `min` : nilai **minimum** yang diizinkan (untuk `number`, `date`, dll.).
- `max` : nilai **maksimum** yang diizinkan.
- `minlength` : jumlah **karakter minimum** yang harus diisi pada input teks.

Contoh: `<input type="number" min="17" max="60" required>` hanya menerima umur 17 sampai 60 dan tidak boleh kosong.

### 10. Apa perbedaan elemen `<audio>` dan `<video>`?
- `<audio>` : memutar **suara saja** (musik, podcast); tampilannya hanya kontrol pemutar.
- `<video>` : memutar **gambar bergerak beserta suara**; mempunyai area tampilan sehingga bisa diatur `width`/`height` dan poster.

Keduanya memakai atribut `controls` untuk menampilkan tombol putar/jeda/volume, serta `<source>` untuk menentukan file dan format (`audio/mpeg`, `video/mp4`) dengan teks cadangan jika browser tidak mendukung.

---

## 4. Kesimpulan
Melalui praktikum ini dipelajari cara menyusun tabel yang terstruktur, membuat form lengkap dengan berbagai tipe input dan validasi bawaan HTML, menerapkan semantic HTML agar halaman lebih bermakna, serta menyisipkan audio dan video ke halaman web.
