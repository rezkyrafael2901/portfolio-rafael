# Portofolio — Rafael Rezki Sembiring

Website portofolio statis (HTML + CSS + JavaScript, tanpa framework dan tanpa build step).
Desain dark-professional dengan aksen gradien cyan→violet, responsif sampai layar 320px.

## Struktur

```
portfolio-rafael/
├── index.html                          # seluruh halaman (7 section)
├── assets/
│   ├── styles.css                      # design system + layout responsif
│   ├── script.js                       # nav, scroll reveal, counter, mobile menu
│   └── CV-Rafael-Rezki-Sembiring.pdf   # file CV untuk tombol Download
├── vercel.json                         # clean URLs + security headers + cache
└── .gitignore
```

## Section

| # | Section | Isi |
|---|---------|-----|
| 1 | Hero | Nama, role, ringkasan, CTA, statistik (36 audit / 13 jaringan / 4 produk) |
| 2 | About | Profil, pendidikan, bahasa |
| 3 | Experience | Timeline 6 pengalaman (Auditor, Vana dev, AI annotator, Node validator, Web3 tester, Technical support) |
| 4 | Projects | **Featured: Nodea (Vana Ecosystem)** + VRouter, HoodSniper, Audit Portfolio, Node Validator Ops |
| 5 | Skills | 4 blok: security/blockchain, development, infra/tools, data |
| 6 | Certifications | 6 sertifikat dengan nomor lisensi |
| 7 | Contact | Email, LinkedIn, telepon, lokasi |

## Menjalankan lokal

```bash
cd portfolio-rafael
python3 -m http.server 8899
# buka http://127.0.0.1:8899
```

## Deploy ke Vercel

```bash
cd portfolio-rafael
npx vercel --prod          # butuh login Vercel sekali
```

Atau lewat dashboard Vercel: import folder ini sebagai project statis
(framework preset: **Other**, build command kosong, output directory kosong/`.`).

## Cara update konten

- **Proyek:** cari `<section class="section" id="projects">` di `index.html`.
  - Kartu utama Nodea ada di `<article class="proj-featured">`.
  - Kartu lain ada di `<div class="proj-grid">` → tambah `<article class="proj-card reveal">` baru.
- **Pengalaman:** `<div class="timeline">` → tambah `<article class="tl-item reveal">`.
- **Skill:** `<div class="skills-grid">` → tambah `<span>` di dalam `.chips`.
- **Warna/aksen:** ubah `--accent`, `--accent-2`, `--grad` di `assets/styles.css` bagian `:root`.
- **CV:** ganti file `assets/CV-Rafael-Rezki-Sembiring.pdf` (nama file sama agar tombol tetap jalan).

## Catatan teknis

- Animasi memakai *progressive enhancement*: class `.js` ditambahkan oleh `script.js`,
  jadi tanpa JavaScript seluruh konten tetap terlihat (tidak ada halaman kosong).
- Semua animasi dimatikan otomatis bila pengguna mengaktifkan `prefers-reduced-motion`.
- Tidak ada dependency eksternal selain Google Fonts (Plus Jakarta Sans + JetBrains Mono).
