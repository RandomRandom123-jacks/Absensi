# AbsenSI — Panduan Deploy ke GitHub Pages

Ikuti langkah berikut untuk menghostkan AbsenSI secara gratis di GitHub Pages.

---

## 🚀 Langkah 1 — Buat Akun GitHub

Jika belum punya akun, daftar gratis di [github.com](https://github.com).

---

## 📁 Langkah 2 — Buat Repository Baru

1. Login ke GitHub
2. Klik tombol **"+"** di pojok kanan atas → **"New repository"**
3. Isi nama repository, contoh: `absensi-sekolah`
4. Pilih **Public**
5. Klik **"Create repository"**

---

## ⬆️ Langkah 3 — Upload File

### Cara Mudah (lewat browser):

1. Di halaman repository baru, klik **"uploading an existing file"**
2. Drag & drop ketiga file ini:
   - `index.html`
   - `style.css`
   - `app.js`
3. Klik **"Commit changes"**

### Cara via Git (opsional):

```bash
git init
git add index.html style.css app.js
git commit -m "Upload AbsenSI"
git branch -M main
git remote add origin https://github.com/USERNAME/absensi-sekolah.git
git push -u origin main
```

---

## 🌐 Langkah 4 — Aktifkan GitHub Pages

1. Di repository, klik tab **"Settings"**
2. Di sidebar kiri, klik **"Pages"**
3. Di bagian **"Branch"**, pilih `main` dan folder `/ (root)`
4. Klik **"Save"**

GitHub akan memberikan URL seperti:
```
https://username.github.io/absensi-sekolah/
```

⏳ Tunggu 1-2 menit, lalu buka URL tersebut di browser.

---

## ☁️ Langkah 5 — Setup GitHub Gist (Opsional, untuk Sync Data)

Agar data absensi tersimpan di cloud dan bisa diakses dari perangkat lain:

1. Buka [github.com/settings/tokens/new](https://github.com/settings/tokens/new?scopes=gist)
2. Beri nama token, contoh: `AbsenSI`
3. Centang scope **`gist`**
4. Klik **"Generate token"** — **salin tokennya sekarang** (tidak bisa dilihat lagi!)
5. Di aplikasi AbsenSI, klik **⚙️** di navbar
6. Tempel token → klik **"Hubungkan GitHub"**
7. Gist akan dibuat otomatis sebagai database absensi

---

## 🔑 Default Login

| Username | Password  |
|----------|-----------|
| `admin`  | `admin123` |

> **Ganti password** setelah pertama login melalui menu ⚙️ → Kelola Akun Guru → hapus admin lama, tambah akun baru.

---

## ✅ Fitur Lengkap

| Fitur | Keterangan |
|-------|-----------|
| Login guru | SHA-256 hashed, sessionStorage |
| Tambah/hapus akun guru | Multi-teacher support |
| 36 Kelas | X-1 s/d XII-12 |
| Input absensi | Nama (huruf), NIS (angka), Tanggal, Jam |
| Status absensi | Sakit / Izin / Alpa / Terlambat |
| Riwayat + filter | Cari nama/NIS, filter kelas/status/tanggal |
| Export CSV | Siap dibuka di Excel |
| Print rekap | Format print rapi |
| GitHub Gist sync | Backup cloud, akses multi-device |

---

## ❓ FAQ

**Q: Apakah data aman?**  
A: Data tersimpan di browser kamu (localStorage) dan opsional di GitHub Gist private milikmu. Tidak ada server pihak ketiga yang menyimpan data.

**Q: Bagaimana jika ganti perangkat?**  
A: Setup GitHub Gist, lalu di perangkat baru klik ⚙️ → masukkan PAT + Gist ID → klik "Load dari GitHub".

**Q: Apakah bisa dipakai banyak guru serentak?**  
A: Bisa, dengan catatan satu guru harus sync terlebih dahulu sebelum yang lain load, untuk menghindari konflik data.
