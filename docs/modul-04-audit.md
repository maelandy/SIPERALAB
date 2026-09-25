# Audit Modul 4 - Flexbox, Grid, dan Responsive Design

## Hasil Uji Viewport
| Viewport | Gejala Awal | Penyebab | Perbaikan | Hasil Uji Ulang |
|---|---|---|---|---|
| **360 px** | Navigasi & tombol berdesakan | Lebar container tidak mencukupi untuk 1 baris | Diterapkan `flex-wrap: wrap` pada header, nav, dan `.form-actions` | Elemen berpindah baris secara rapi, tanpa horizontal scroll |
| **768 px** | Hero dan form masih 1 kolom vertikal | Belum ada instruksi layout multi-kolom | Ditambahkan media query `@media (min-width: 48rem)` untuk `.hero` dan `.form-grid` | Hero menjadi 2 kolom horizontal, form terbagi menjadi 2 kolom |
| **1280 px** | Konten melebar terlalu jauh | Lebar elemen mengikuti 100% layar | Diberikan `width: min(1100px, calc(100% - 2rem))` pada container utama | Tampilan terpusat dengan *whitespace* yang nyaman |

## Audit Overflow
- **Elemen yang menyebabkan overflow:** Gambar ilustrasi hero dan kartu katalog saat viewport diperkecil.
- **Bukti dari DevTools:** Gambar keluar dari batas elemen pembungkus (*parent box*).
- **Aturan penyebab:** Gambar memiliki ukuran *intrinsic width* tetap (misal `320px`).
- **Perbaikan:** Menambahkan aturan global `img, svg, video { display: block; max-width: 100%; height: auto; }`.
- **Hasil uji ulang:** Gambar menyesuaikan ukuran container secara responsif.

## Pengujian Aksesibilitas Keyboard & Zoom
- [x] Navigasi keyboard (Tab / Shift+Tab) menunjukkan *outline ring* fokus dengan jelas pada seluruh link dan input form.
- [x] Zoom browser 200% tidak merusak fungsi utama dan tidak menimbulkan *clipping* teks.