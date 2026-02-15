# 🌙 Mutabaah Yaumiyah Ramadhan 1447H

![Project Status](https://img.shields.io/badge/Status-Active-success)
![Platform](https://img.shields.io/badge/Platform-Web-blue)
![Backend](https://img.shields.io/badge/Backend-Google%20Sheets-green)

Aplikasi berbasis web sederhana namun futuristik untuk memantau ibadah harian siswa selama bulan Ramadhan. Sistem ini menggunakan **Github Pages** sebagai frontend dan **Google Sheets** sebagai database backend (Serverless).

---

## ✨ Fitur Utama

1.  **Desain Modern & Responsif:** Tampilan *Glassmorphism* dengan nuansa Ramadhan yang ceria, cocok untuk HP maupun Desktop.
2.  **Real-time Database:** Terhubung langsung dengan Google Sheets.
3.  **Smart Form:**
    * **Auto-Save Email:** Orang tua tidak perlu mengetik ulang email setiap hari.
    * **Validasi Harian:** Mencegah input ganda (1 siswa hanya bisa input 1x sehari).
    * **Dropdown Dinamis:** Nama siswa muncul otomatis berdasarkan Kelas yang dipilih.
    * **Conditional Input:** Kolom "Alasan" hanya muncul jika status "Tidak Puasa".
4.  **Penanggalan Otomatis:** Menampilkan tanggal Masehi dan Hijriah (Estimasi Ramadhan 1447H).

---

## 🚀 Cara Instalasi & Penggunaan

Ikuti langkah-langkah berikut untuk menggunakan source code ini:

### 1. Persiapan Database (Google Sheets)
1.  Buat Google Spreadsheet baru.
2.  Buat **Sheet 1** dengan nama `Database`.
    * Kolom A: **Kelas**
    * Kolom B: **Nama Siswa**
    * *(Isi data siswa di sini)*
3.  Buat **Sheet 2** dengan nama `Respon`.
    * Buat Header di baris pertama (A1 - M1):
        `Timestamp`, `Email`, `Kelas`, `Nama Siswa`, `Status Puasa`, `Alasan Tidak Puasa`, `Sholat Wajib/Sunnah`, `Lokasi Sholat`, `Tilawah Awal`, `Tilawah Akhir`, `Murojaah`, `Validasi`, `Tanggal Masehi`

### 2. Konfigurasi Backend (Google Apps Script)
1.  Di Google Sheets, klik **Ekstensi** > **Apps Script**.
2.  Copy kode backend (ada di file terpisah atau tutorial sebelumnya).
3.  Klik **Deploy (Terapkan)** > **New Deployment**.
4.  **PENTING:** Pada bagian "Who has access" (Siapa yang memiliki akses), pilih **"Anyone" (Siapa Saja)**.
5.  Salin **Web App URL** yang dihasilkan (dimulai dengan `https://script.google.com/...`).

### 3. Konfigurasi Frontend (Github)
1.  Download atau Clone repository ini.
2.  Buka file `index.html`.
3.  Cari baris kode berikut (biasanya di bagian bawah):
    ```javascript
    const SCRIPT_URL = 'GANTI_DENGAN_URL_DEPLOYMENT_GAS_ANDA_DISINI';
    ```
4.  Tempel URL Web App dari langkah ke-2 di situ.
5.  Pastikan ada file gambar logo dengan nama `logosmpit.png` di folder yang sama.

### 4. Publikasi
1.  Push perubahan ke Github.
2.  Masuk ke menu **Settings** > **Pages** di repository Github.
3.  Pilih branch `main` (atau master) dan folder `/root`.
4.  Website Anda sudah online! 🎉

---

## ⚙️ Penyesuaian (Customization)

* **Mengubah Tanggal Mulai Ramadhan:**
    Buka `index.html`, cari variabel `startRamadhan` di dalam script:
    ```javascript
    const startRamadhan = new Date('2026-02-18'); // Sesuaikan tanggal 1 Ramadhan 1447H
    ```
* **Mengganti Logo:**
    Ganti file `logosmpit.png` dengan logo sekolah Anda (pastikan nama file tetap sama atau ubah referensinya di `index.html`).

---

## 📂 Struktur File

```text
mutabaah-ramadhan/
├── index.html        # Halaman Utama (Frontend)
├── logosmpit.png     # Logo Sekolah/Yayasan
└── README.md         # Dokumentasi ini
