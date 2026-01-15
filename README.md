# Data Excel Upload

Antarmuka web sederhana untuk mengunggah file Excel ke GitHub melalui Cloudflare Worker. Proyek ini menyediakan halaman upload yang sudah siap dipakai dan daftar file Excel yang tersimpan di repo.

## ✨ Fitur Utama

- **Upload Excel (.xlsx/.xls)** langsung dari browser.
- **Progress upload real-time** dan status aktivitas.
- **Daftar file Excel** dengan aksi unduh dan hapus.
- **PIN/Key** disimpan di `sessionStorage` untuk sesi browser saat ini.
- **Tampilan “hacker theme”** dengan nuansa terminal.

## 📂 Struktur Folder

```
.
├── index.html
└── uploads
    ├── upload.html
    └── (file Excel yang diunggah)
```

## 🚀 Cara Pakai

1. Buka halaman upload:
   ```
   /uploads/upload.html
   ```
2. Masukkan PIN/KEY lalu klik **Simpan**.
3. Pilih file Excel, klik **Upload**.
4. Klik **Refresh List** untuk memuat daftar file.

## ⚙️ Konfigurasi Worker

Di file `uploads/upload.html`, sesuaikan URL Worker pada konstanta berikut:

```js
const WORKER_BASE = "https://your-worker-url.workers.dev";
```

Endpoint yang digunakan:

- `POST /upload`
- `GET /list`
- `GET /download?filename=...`
- `POST /delete`

## 🛡️ Keamanan Singkat

- PIN/KEY divalidasi di Worker, bukan di browser.
- Kunci hanya tersimpan di `sessionStorage` (hilang saat browser ditutup).

## ✅ Catatan

Proyek ini merupakan halaman statis (HTML/CSS/JS). Anda bisa menjalankannya langsung lewat GitHub Pages atau server statis lainnya.
