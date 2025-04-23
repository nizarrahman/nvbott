
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

Proyek ini menggunakan lisensi MIT. Silakan gunakan dan kembangkan dengan bebas.

---
