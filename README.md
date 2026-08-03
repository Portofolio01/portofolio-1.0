# Portofolio — Restu Nurrokhman (v3.1)

Situs statis HTML/CSS/JS, tanpa build step. Buka `index.html` langsung di
browser, atau deploy sebagai static site (GitHub Pages, Netlify, dll).

## Yang berubah di v3.1 (penyesuaian.md)

- **Intro**: tombol/teks "Lewati" dihapus total. Intro 4 detik + audio
  MP3 tetap main bareng, otomatis lanjut ke hero begitu selesai.
- **LED navbar**: sebelumnya 2 titik cahaya jalan berlawanan arah
  (masing-masing cuma separuh jalur). Sekarang **1 titik cahaya**
  yang mengitari seluruh tepi navbar **ke arah kiri (counterclockwise),
  infinite loop**, tanpa putus.
- **Efek pendaran LED di latar belakang web**: ditambahkan — 3 titik
  cahaya blur lembut yang "bernapas" pelan di balik semua section,
  pakai `mix-blend-mode: screen` supaya tetap terlihat di atas warna
  solid tiap section.
- **Fitur Search dihapus total** (tombol kaca pembesar, input, CSS,
  dan JS-nya) beserta logonya.
- **Footer**: dari `position: sticky` (nempel di layar) jadi
  `position: static` — sekarang statis mengikuti alur halaman, teks
  tetap rata tengah.
- **Bug diperbaiki**: atribut `aria-hidden` pada menu bahasa dan
  `aria-expanded` pada tombol hamburger/bahasa sebelumnya ditulis
  statis di HTML dan tidak pernah diperbarui saat menu dibuka/tutup —
  sekarang disinkronkan lewat JS.
- **Font CJK**: menambah fallback Noto Sans/Serif SC & JP supaya teks
  Jepang & Mandarin render lebih rapi di berbagai perangkat.

## Yang sudah ada sejak v3.0 (dicek ulang, tidak diubah)

- Kartu bio bergaya lanyard (dengan animasi gantung) ada di posisi
  paling atas section "Latar", di atas slideshow foto kenangan.
- Navbar mengambang dengan sudut melengkung, logo `</>` Restu.dev, dan
  ikon hamburger yang berfungsi ganda buka/tutup menu.
- Teks bahasa Indonesia, Inggris, Jepang, dan Mandarin lengkap
  (dicek: tidak ada key terjemahan yang hilang).
- "Hubungi Saya" sudah jadi 3 ikon langsung: WhatsApp, Instagram, Email.
- Animasi masuk elemen dari kiri/kanan/bawah (`reveal-left/right/up`).

## Struktur

```
index.html
assets/css/style.css     — bagian bernomor
assets/js/main.js         — bagian bernomor
assets/frames/               — 96 frame logo (intro)
assets/audio/intro.mp3         — audio intro
assets/img/profile.jpg           — foto hero & kartu bio
assets/img/memories/               — 7 foto kenangan
```

## Placeholder yang masih perlu diisi

- `CERTS`, `FIELDS` di `assets/js/main.js` bagian 0 — masih array
  kosong, tampil sebagai "Belum ada sertifikat." / "Belum ditentukan."
  sampai diisi manual.

## Deploy ke GitHub Pages

1. Buat repo baru di GitHub (jangan centang "Add README" biar tidak
   bentrok), lalu di folder project ini jalankan:

   ```bash
   git remote add origin https://github.com/USERNAME/NAMA-REPO.git
   git push -u origin main
   ```

2. Di GitHub: masuk repo → **Settings → Pages** → Source pilih
   **Deploy from a branch** → Branch pilih `main` / folder `/ (root)`
   → Save.
3. Tunggu 1–2 menit, situs akan aktif di
   `https://USERNAME.github.io/NAMA-REPO/`.

Karena ukuran project ~15MB (dominan dari audio + 96 frame intro),
pastikan koneksi stabil saat `git push` pertama kali.
