# Sekovia — Website

Halaman pemasaran (marketing site) untuk aplikasi manajemen sekolah **Sekovia**.
Statis, banyak halaman, tanpa proses build — dirancang untuk **GitHub Pages**.

## Struktur

```
index.html      Beranda — hero, 4 peran, teaser fitur, cara mulai, CTA
tentang.html    Tentang Sekovia + Keamanan & Privasi
fitur.html      Fitur unggulan + daftar lengkap 14 modul + pratinjau tampilan
manfaat.html    Kenapa sekolah pindah ke Sekovia
harga.html      Model harga (disesuaikan skala sekolah, bukan paket fiktif)
faq.html        Pertanyaan umum
kontak.html     Email, web admin, alamat + CTA
assets/styles.css   Semua gaya (token warna, tipografi, komponen) — dipakai semua halaman
assets/script.js    Menu mobile (hamburger) + animasi kartu fitur muncul saat discroll
.nojekyll       Memberi tahu GitHub Pages untuk tidak memproses lewat Jekyll
```

Tiap halaman berbagi header (nav + logo) dan footer yang sama; nav menyorot
halaman yang sedang dibuka (`class="active"`).

## Konten

Struktur & kelengkapan halaman dibandingkan dengan situs referensi
(scholarik.com) atas permintaan pengguna — tapi **palet warna tetap milik
Sekovia sendiri** (biru, bukan warna acuan). Teks fitur diambil dari deskripsi
resmi di `native/PLAY_STORE.md` (proyek aplikasi) — jujur terhadap fitur yang
benar-benar ada:

- Tanpa angka pengguna atau testimoni fiktif
- Tanpa paket harga yang dikarang — halaman Harga mengarahkan ke kontak
- Tanpa video demo yang tidak dimiliki — diganti kartu mockup abstrak
  (bukan tangkapan layar data sekolah asli)

## Menjalankan lokal

```bash
python -m http.server 8080
```
Buka `http://localhost:8080`.

## Deploy ke GitHub Pages

1. Push repo ini ke GitHub (repo **publik**, atau privat + GitHub Pro untuk Pages privat).
2. **Settings → Pages** → Source: **Deploy from a branch** → Branch: `main` / `(root)`.
3. Situs akan tersedia di `https://<username>.github.io/<nama-repo>/`.
4. (Opsional) Domain kustom: tambah berkas `CNAME` berisi domain (mis. `sekovia.id`),
   lalu atur DNS domain menunjuk ke GitHub Pages (`ALIAS`/`ANAME` ke
   `<username>.github.io`, atau 4 `A` record ke IP GitHub Pages).

## Menambah halaman baru

1. Salin salah satu halaman yang ada (mis. `manfaat.html`) sebagai kerangka.
2. Ganti `<title>`, `<meta name="description">`, isi `<main>`.
3. Tambahkan tautan ke halaman baru di nav (desktop `ul` + `#mobileMenu ul`)
   **di semua halaman**, termasuk halaman baru itu sendiri (tandai `class="active"`).
4. Tambahkan juga di kolom "Halaman" pada footer tiap halaman kalau perlu.

## Update

Edit berkas yang relevan, commit, push — GitHub Pages otomatis membangun ulang
dalam beberapa menit.
