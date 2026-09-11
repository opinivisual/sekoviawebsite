# Sekovia — Website

Halaman landas (marketing site) untuk aplikasi manajemen sekolah **Sekovia**.
Statis, satu berkas, tanpa proses build — dirancang untuk **GitHub Pages**.

- `index.html` — seluruh halaman (HTML + CSS + JS inline, tanpa dependensi build)
- `.nojekyll` — memberi tahu GitHub Pages untuk tidak memproses situs ini lewat Jekyll

## Konten

Satu halaman (`index.html`) berisi: hero, empat peran (Admin/Guru/Siswa/Orang
Tua), fitur unggulan (Absensi Kartu QR, Perpustakaan Digital, Kalender &
Catatan, Asisten AI), cara memulai, keamanan & privasi, dan kontak.

Teks fitur diambil dari deskripsi resmi di `native/PLAY_STORE.md` (proyek
aplikasi) — jujur terhadap fitur yang benar-benar ada, tanpa klaim yang
dibuat-buat (tanpa angka pengguna fiktif, tanpa testimoni palsu).

Palet & font sengaja berbeda dari dashboard aplikasi (yang bergaya SaaS modern
biru-putih) — situs ini bergaya "buku rapor/ledger sekolah" (kertas gading,
garis buku tulis, font Fraunces untuk judul) supaya terasa seperti halaman
promosi, bukan cuplikan dashboard.

## Menjalankan lokal

Buka `index.html` langsung di peramban, atau jalankan server statis apa pun:

```bash
python -m http.server 8080
```

## Deploy ke GitHub Pages

1. Push repo ini ke GitHub (repo **publik**, atau privat + GitHub Pro untuk Pages privat).
2. **Settings → Pages** → Source: **Deploy from a branch** → Branch: `main` / `(root)`.
3. Situs akan tersedia di `https://<username>.github.io/<nama-repo>/`.
4. (Opsional) Domain kustom: tambah berkas `CNAME` berisi domain (mis. `sekovia.id`),
   lalu atur DNS domain menunjuk ke GitHub Pages (`ALIAS`/`ANAME` ke
   `<username>.github.io`, atau 4 `A` record ke IP GitHub Pages).

## Update

Edit `index.html`, commit, push — GitHub Pages otomatis membangun ulang dalam
beberapa menit.
