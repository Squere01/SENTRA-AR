# SENTRA Reader · halaman AR

Halaman web statis untuk melihat SENTRA Reader v2 dalam augmented reality, dalam ukuran asli (skala 1 : 1).
Tidak butuh build, server, atau API: cukup upload folder ini ke hosting statis HTTPS.

| File | Isi |
|---|---|
| `index.html` | Halaman AR (tema SENTRA, Bahasa Indonesia) |
| `model-viewer.min.js` | Google model-viewer 4.0.0 (sudah termasuk three.js) |
| `models/sentra_reader.glb` / `.usdz` | Model utuh: Android / iPhone |
| `models/sentra_reader_urai.glb` / `.usdz` | Model 568 part dengan animasi urai lalu menyatu |
| `fonts/` | IBM Plex |
| `vercel.json`, `_headers` | Content-Type yang benar untuk `.glb` dan `.usdz` (Vercel / Netlify) |

## Cara deploy (pilih satu)

**Vercel (disarankan, URL sudah dipakai di QR guidebook)**

```bash
npm i -g vercel
cd sentra-tb-ar
vercel --prod
```

Saat ditanya nama project, isi `sentra-tb-ar`, sehingga URL-nya menjadi `https://sentra-tb-ar.vercel.app`,
sama dengan URL di QR guidebook. Kalau nama itu sudah dipakai orang lain, Vercel memberi URL lain:
QR di guidebook harus dibuat ulang dengan URL tersebut.

**Netlify Drop:** buka app.netlify.com/drop, seret folder `sentra-tb-ar`. Ganti nama site di
Site settings agar URL-nya rapi, lalu buat ulang QR dengan URL itu.

**GitHub Pages:** push folder ini ke repo, aktifkan Pages (branch `main`, folder root).

## Cara mengetes

- **Android:** buka URL di Chrome pada HP yang mendukung ARCore, lalu tekan *Lihat di ruangan Anda*.
- **iPhone/iPad:** buka di Safari, lalu tekan tombol yang sama. AR Quick Look akan terbuka.
- **Laptop:** model bisa diputar dan diperbesar; tombol AR tidak muncul karena laptop tidak punya AR.

Model `Urai` berukuran ± 0,9 m saat terurai penuh, jadi butuh meja atau lantai yang cukup lapang.

## Membuat ulang QR dengan URL lain

Dari kode sumber guidebook:

```bash
cd /home/claude/sentra/pdf
SENTRA_AR_URL="https://url-baru-anda" python3 ../guide/build_guide.py
```

Konsep riset SENTRA-TB, belum tervalidasi secara klinis.
