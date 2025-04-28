# 📋 CHANGELOG - NV Bot


## ✨ Versi Update: 28 April 2025
## Version 1.0.1 - 2025-04-28
- Memperbaiki logika status WD, agar bot tidak mengirimkan "WD Gagal" jika transaksi sukses.
- Mengubah pemeriksaan status transaksi menjadi `status === "Sukses"`.
- Menambahkan log error ketika PIN atau password salah.
- Menambahkan log untuk setiap request transaksi WD yang dikirim.
- Menambahkan log untuk hasil transaksi WD.

## Version 1.0.0 - 2025-04-20
- Menambahkan fitur WD dengan menggunakan OkeConnect API.
- Memungkinkan pengguna melakukan withdrawal dengan harga yang sesuai menggunakan command `.wd <nominal>`.

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

> Dibuat dengan ❤️ oleh Nizar  - 2025
