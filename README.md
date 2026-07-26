# 📡 Roadmap Pembelajaran TLJ Kelas XII

Website statis (HTML murni, tanpa build tools) berisi **roadmap pembelajaran** mata pelajaran **Teknik Layanan Jaringan (TLJ) Kelas XII** — SMK Bintang Raudloh, Tahun Ajaran 2026/2027.

Guru pengampu: **Khalid Nabawi, S.Kom.**

🔗 Live demo (setelah di-deploy ke GitHub Pages): `https://<username-github-anda>.github.io/<nama-repo>/`

---

## 🗂️ Struktur File

```
.
├── index.html      # Halaman utama (Roadmap) — pintu masuk website
├── bab1.html        # Materi BAB 1 — Review Dasar Jaringan (sudah lengkap: teori, kalkulator subnet, kuis, evaluasi 25 soal)
├── bab2.html        # BAB 2 — Perencanaan Topologi (placeholder, materi belum tersedia)
├── bab3.html        # BAB 3 — Switching (placeholder)
├── bab4.html        # BAB 4 — Inter VLAN Routing (placeholder)
├── bab5.html        # BAB 5 — Static Routing (placeholder)
├── bab6.html        # BAB 6 — Dynamic Routing (placeholder)
├── bab7.html        # BAB 7 — NAT dan Internet Gateway (placeholder)
├── bab8.html        # BAB 8 — Troubleshooting Routing (placeholder)
├── bab9.html        # BAB 9 — Wireless Network (placeholder)
├── bab10.html       # BAB 10 — Firewall (placeholder)
├── bab11.html       # BAB 11 — Proxy Server (placeholder)
├── bab12.html       # BAB 12 — Manajemen Bandwidth (placeholder)
├── bab13.html       # BAB 13 — Load Balancing (placeholder)
├── bab14.html       # BAB 14 — Network Monitoring (placeholder)
├── bab15.html       # BAB 15 — Fiber Optic (placeholder)
├── bab16.html       # BAB 16 — Maintenance (placeholder)
├── bab17.html       # BAB 17 & 18 — Project Based Learning & Uji Kompetensi (placeholder)
└── README.md        # Dokumentasi ini
```

> **Penting:** semua file HTML saling terhubung lewat hyperlink berdasarkan **nama file**nya (`bab1.html`, `bab2.html`, dst). Jangan mengubah nama file kecuali kamu juga memperbarui semua tautan yang mengarah ke file tersebut di `index.html`.

Halaman placeholder (`bab2.html` s.d. `bab17.html`) hanya menampilkan judul bab dan pesan bahwa materi belum tersedia beserta kontak guru pengampu. File-file ini bisa diisi materi lengkap kapan saja mengikuti pola `bab1.html`.

---

## 🛠️ Teknologi yang Digunakan

Tidak ada proses build/compile — semua halaman adalah **HTML statis murni** yang bisa langsung dibuka di browser.

- [Tailwind CSS](https://tailwindcss.com/) via CDN (`cdn.tailwindcss.com`) — utility class untuk layout & warna.
- [Font Awesome 6](https://fontawesome.com/) via CDN — ikon.
- [Google Fonts — Inter](https://fonts.google.com/specimen/Inter) — font utama seluruh halaman.
- JavaScript vanilla (tanpa framework) — untuk navbar, kalkulator subnet, kuis interaktif, dan skoring evaluasi di `bab1.html`.

Karena semua library dimuat lewat CDN, **koneksi internet dibutuhkan saat website dibuka** (baik lokal maupun online).

---

## 💻 Cara Menjalankan di Komputer Lokal

Karena ini website statis, tidak perlu Node.js, PHP, atau server khusus.

1. Clone atau download repo ini.
2. Buka file `index.html` langsung dengan double-click, **atau**
3. Jalankan local server sederhana (opsional, disarankan agar semua fitur berjalan normal di beberapa browser):

   ```bash
   # Python 3
   python -m http.server 8000

   # lalu buka http://localhost:8000 di browser
   ```

---

## 🚀 Cara Deploy ke GitHub Pages (Gratis)

1. Buat repository baru di GitHub, lalu upload seluruh isi folder ini (jaga strukturnya tetap datar/flat, jangan dimasukkan ke sub-folder).
2. Masuk ke **Settings → Pages** pada repo tersebut.
3. Pada bagian **Build and deployment**, pilih:
   - Source: `Deploy from a branch`
   - Branch: `main` (atau `master`) — folder `/ (root)`
4. Simpan. Tunggu 1–2 menit, GitHub akan memberi tautan seperti:
   `https://<username-github-anda>.github.io/<nama-repo>/`
5. Halaman `index.html` akan otomatis menjadi halaman utama.

---

## ✍️ Cara Menambahkan Materi Bab Baru (untuk Guru Lain)

Jika ingin mengisi materi ke salah satu bab yang masih placeholder (misalnya `bab2.html`):

1. Buka `bab1.html` sebagai **contoh/template** — halaman ini sudah lengkap dengan semua komponen (hero, navigasi sidebar, panel materi, kalkulator, kuis, evaluasi).
2. Salin struktur navbar atas, hero, dan footer dari `bab1.html` agar tampilan tetap konsisten dengan `index.html`.
3. Ganti bagian `<main>` dengan materi bab yang bersangkutan (section per topik, gunakan class `.section`, `.panel`, `.eyebrow`, dsb yang sudah tersedia di `<style>`).
4. Perbarui daftar `<ul class="navlist">` di sidebar agar sesuai dengan sub-topik bab tersebut.
5. Simpan file dengan nama yang **sama seperti tautan di `index.html`** (misalnya materi BAB 2 harus tetap bernama `bab2.html`).
6. Commit & push perubahan ke GitHub — jika sudah terhubung ke GitHub Pages, perubahan akan otomatis online dalam beberapa menit.

### Palet Warna & Font (agar tetap konsisten)

| Elemen              | Nilai                                   |
|----------------------|------------------------------------------|
| Primary (biru tua)   | `#1e40af`                                 |
| Secondary (biru)     | `#3b82f6`                                 |
| Accent (kuning)      | `#f59e0b`                                 |
| Dark (teks gelap)    | `#1e293b`                                 |
| Light (background)   | `#f8fafc`                                 |
| Font utama           | `Inter` (Google Fonts)                    |
| Font kode/angka      | `IBM Plex Mono` (opsional, untuk angka teknis) |

Konfigurasi warna ini sudah didefinisikan di `tailwind.config` pada setiap file — cukup gunakan class Tailwind seperti `bg-primary`, `text-secondary`, `bg-dark`, dll.

---

## 🧪 Fitur Interaktif di BAB 1

- **Kalkulator Subnet/CIDR** — menghitung network address, subnet mask, rentang host, broadcast, dan jumlah host valid secara otomatis.
- **Kartu OSI Layer interaktif** — klik untuk membuka penjelasan tiap layer.
- **Kuis Ringan (10 soal)** — jawaban langsung diperiksa benar/salah saat diklik, cocok untuk latihan mandiri siswa.
- **Studi Kasus Akhir (Tantangan Mini)** — soal VLSM dengan tombol untuk menampilkan jawaban yang diharapkan.
- **Evaluasi Akhir (25 Soal)** — kuis penilaian resmi:
  - Siswa mengisi Nama & Kelas.
  - Semua 25 soal harus dijawab sebelum bisa mengumpulkan.
  - Setelah klik **"Kumpulkan Jawaban"**, jawaban benar/salah ditandai dan skor akhir (X/25 serta nilai) langsung ditampilkan di layar.
  - Skor ini **dinilai secara manual oleh guru** — siswa diminta menunjukkan/screenshot layar hasil skor kepada guru pengampu.

---

## 📄 Lisensi & Penggunaan

Materi ini dibuat untuk keperluan edukasi internal SMK Bintang Raudloh. Guru lain yang ingin menggunakan atau memodifikasi struktur website ini dipersilakan, dengan tetap mencantumkan kredit mata pelajaran dan menyesuaikan identitas sekolah/guru pengampu sesuai kebutuhan masing-masing.

---

## 🙋 Kontak

Untuk pertanyaan seputar materi TLJ Kelas XII, silakan hubungi: Khalid Nabawi (khalidnabawidigital@gmail.com)

**Khalid Nabawi, S.Kom.**
Guru Pengampu — Teknik Layanan Jaringan, SMK Bintang Raudloh
