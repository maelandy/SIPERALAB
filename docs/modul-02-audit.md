# Audit Modul 2 Semantic HTML dan Formulir

## Sebelum perbaikan
| Temuan | Halaman/elemen | Bukti | Rencana perbaikan |
|---|---|---|---|
| Katalog masih berupa ul/li | peralatan.html | DOM | Ubah menjadi section + article |
| Form belum tersedia | peminjaman.html | file baru | Buat form lengkap dengan fieldset & validasi |

## Setelah perbaikan
- [x] Landmark halaman masuk akal (header, nav, main, footer).
- [x] Hierarki heading logis (h1, h2, h3).
- [x] Minimal tiga item katalog lengkap (Multimeter, Router, Kamera).
- [x] Label dapat diklik dan fokus otomatis berpindah ke kontrol input terkait.
- [x] Field penting memiliki atribut name untuk pengiriman form.
- [x] Submit saat kosong memicu validasi bawaan browser.
- [x] Urutan Tab navigasi keyboard berjalan logis.
- [x] Validator HTML tidak menampilkan error utama.

## Refleksi
1. **Perbedaan section, article, dan div:**
   - `<section>`: Mengelompokkan konten tematik yang berhubungan (contoh: seluruh katalog alat).
   - `<article>`: Bagian konten independen yang bisa berdiri sendiri (contoh: satu kotak spesifikasi alat).
   - `<div>`: Elemen generik tanpa makna semantik, hanya dipakai sebagai pembungkus untuk kebutuhan styling/layout.
2. **Mengapa placeholder tidak cukup menggantikan label?**
   - Placeholder akan hilang begitu pengguna mengetik sehingga menghilangkan konteks input. Placeholder juga tidak dapat diakses secara optimal oleh Screen Reader dan tidak memindahkan fokus ketika diklik.
3. **Fungsi atribut `name`:**
   - Atribut `name` berfungsi sebagai kunci (*key*) dari data yang dikirimkan ke server/backend melalui payload form (misal: format key-value). Tanpa atribut `name`, isi input tidak akan ikut terkirim ke backend.
4. **Masalah yang terdeteksi saat audit keyboard:**
   - Memastikan urutan Tab berjalan alami dari atas ke bawah tanpa meloncat, serta memverifikasi bahwa checkbox dan tombol dapat diaktifkan menggunakan spasi dan Enter.
5. **Mengapa starter Modul 2 tidak boleh langsung menimpa Modul 1?**
   - Karena praktikum ini bersifat *longitudinal* (berkelanjutan). Menimpa repo bisa menghilangkan riwayat commit Git, merusak konfigurasi dependensi yang sudah stabil, dan menghapus penyesuaian yang sudah dibuat sebelumnya.