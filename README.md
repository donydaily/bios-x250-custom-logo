# 🔧 Mengganti Logo BIOS ThinkPad X250

## ✅ Persyaratan

- **OS saat ini**: Linux Mint
- **File logo**:
  - Format: GIF
  - Mode: Indexed 24 (Edit menggunakan GIMP)
  - Resolusi: 640x480 (disarankan)
  - Ukuran: < 30 KB

  NOTE: Jangan gunakan background transparan
---

## 🧰 Langkah-langkah

### 1. Burn Image BIOS Ke Flashdisk

```bash
sudo dd if=x250.img of=/dev/sdx bs=64K
```
NOTE:
- Ganti /dev/sdx sesuai dengan jalur flashdisk
- Untuk mengeceknya
```bash
lsblk
```

### 2. Masukan logo

Salin file logo ke dalam flashdisk, tepatnya didalam folder FLASH
Ubah namanya menjadi :
- `logo1.gif`
- `logo2.gif`


### 3. Boot dari USB

- Restart laptop
- Saat boot, tekan `F12` lalu pilih USB
- Setelah muncul pilihan, pilih saja nomor 2
- Lalu tinggal Y dan Enter saja sampai selesai
