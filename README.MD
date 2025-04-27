
---

# 🤖 NV Bot - WhatsApp Bot Multifungsi

**NV Bot** adalah bot WhatsApp serbaguna yang dirancang untuk menyederhanakan berbagai aktivitas otomatisasi di WhatsApp, seperti manajemen grup sewa, sistem pembayaran otomatis, deteksi penipuan, dan fitur premium berbasis langganan. Bot ini cocok untuk dijadikan layanan sewa bot WhatsApp.

## 🚀 Fitur Utama

- ✅ **Sistem Sewa Otomatis**
  - Bergabung otomatis ke grup berdasarkan link undangan
  - Slot pengelolaan grup di `slotmember.json`
  - Durasi sewa fleksibel, bisa premium atau reguler

- 💸 **Pembayaran Otomatis**
  - Terintegrasi dengan API SimpleBot (OrderKuota)
  - Mendukung QRIS
  - Sistem pengecekan status pembayaran
  - Invoice custom dengan QR Code dan informasi grup

- 🚫 **Anti-Fraud**
  - Bot auto keluar dari grup ilegal
  - Banned otomatis ke nomor penipu selama 9999 hari

- 🛒 **Pembelian Premium**
  - Command `.buypremium [durasi] [nomor]`
  - Aktivasi otomatis dan manajemen masa aktif

- 📑 **Menu Interaktif**
  - Menu command dengan kategori (tools, info, premium, owner)
  - Respon cepat dan efisien

## ⚙️ Struktur Utama

- `slotmember.json` — Menyimpan daftar grup aktif dan slot sewa
- `paymentHandler.js` — Handler untuk webhook dan status pembayaran
- `invoiceCanvas.js` — Modul Canvas untuk membuat invoice bergambar
- `commands/` — Folder command seperti `.sewabot`, `.addsewa`, `.buypremium`, dll

## 🛠️ Cara Install

```bash
git clone https://github.com/nizarrahman/nvbot-addon
cd nvbot-addon
npm install
npm start
```

Lalu buat file `.env` atau isi `config.js`:

```js
global.ApikeyRestApi = "API_KEY_REST";
global.QrisOrderKuota = "API_KEY_QRIS";
global.IdMerchant = "MERCHANT_ID";
global.ApikeyOrderKuota = "API_KEY_ORDERKUOTA";
```

## 📦 Contoh Command

- `.sewabot` – Membeli sewa bot grup
- `.addsewa https://chat.whatsapp.com/xxxx` – Menambahkan grup ke slot aktif
- `.buypremium 1bulan 628xxxx` – Memberikan akses premium

## 📸 Contoh Invoice

Invoice akan dikirim otomatis setelah pembayaran berhasil dalam bentuk gambar berisi:
- QR Code
- Nama grup
- Durasi sewa
- Waktu kedaluwarsa

## 👤 Developer

- Author: **NizarDev**
- iNSTAHRAM: [nizarrrahman.f_](https://instagram.com/nizarrrahman.f_)

## 📄 License

Script ini di jual silahkan hubungi admin
whatsapp: [6287856848569](https://wa.me/6287856848569)

---


# 📋 CHANGELOG - Sewa Bot

## ✨ Versi Update: 27 April 2025

---

## 🔥 Fitur Baru

### Notifikasi Admin 2
- Setelah transaksi pembayaran QRIS berhasil,
- Bot otomatis mengirimkan notifikasi ke nomor admin kedua.
- Isi notifikasi mencakup paket, harga, fee, total bayar, ID order, dan penyewa.

### Notifikasi ke Grup
- Setelah bot bergabung ke grup penyewa,
- Bot otomatis mengirimkan pesan konfirmasi ke grup:
  - Penyewa (tag langsung @user)
  - Nama paket
  - Durasi sewa

### Sistem Slot Member
- Setelah join ke grup:
  - Bot otomatis set *slot member* grup menjadi **400**.
  - Data disimpan di file `slotmember.json`.
  - Jika file tidak ada, otomatis dibuat.

---

## 🛠️ Perbaikan dan Optimasi

### Pembayaran
- Cek mutasi QRIS lebih stabil dengan retry otomatis jika parsing gagal.

### Pengiriman Pesan
- Format notifikasi ke user lebih rapih.
- Tag penyewa langsung dalam pesan dengan `mentions`.

### Format Waktu
- Expired pembayaran ditampilkan sebagai `HH:MM WIB`.

---

## 🧹 Struktur Kode

- Variabel admin utama dan admin tambahan disusun di bagian atas file.
- Tambahan pengecekan keberadaan file `slotmember.json` sebelum membaca.
- Penyusunan flow pembayaran lebih sistematis.

---

## 📊 Catatan

- Pastikan `setting.js` dan `utils.js` sudah tersedia.
- Pastikan Orkut API aktif dan ID/API key benar.
- Jangan lupa backup file `slotmember.json` secara berkala.

---

> Dibuat dengan ❤️ oleh Nizar Rahman Fadillah - 2025
