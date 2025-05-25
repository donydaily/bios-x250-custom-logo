# 🔧 Membuat Bootable Untuk Update BIOS/Mengganti BIOS Logo

## ✅ Persyaratan

- **OS saat ini** : Linux Mint
- **USB Flashdisk** : Minimal 1 GB
- **Secure RollBack Prevention** : Harus DISABLE
- **File BIOS** : [Bisa dowmload di situs resminya](https://pcsupport.lenovo.com/id/en/) Download bootable berformat ISO
- **File logo** :
  - Format : GIF
  - Mode : Indexed 24 (Edit menggunakan GIMP)
  - Resolusi : 640x480 (disarankan)
  - Ukuran : < 30 KB

  NOTE :
  - Jangan gunakan background transparan
  - Untuk ThinkPad tipe lain, tinggal sesuaikan saja semua bahannya
  - Cara ini bisa juga digunakan untuk update BIOS (Skip bagian logo)
  - Untuk logo, bisa di sesuaikan resolusi dll nya (Steiap tipe beda beda)
  - Panduan untuk resolusi ukuran logo lebih jelas ada di `README` di dalam folder `FLASH`

---

## 🧰 Langkah-langkah

### 1. Disable BIOS Secure RollBack Prevention
- Restart laptop
- Saat boot, tekan `F1` sampai masuk menu BIOS
- Masuk ke tab `Security`
- Pilih `BIOS Update Option`
- Lalu pada bagian `Secure Rollback Prevention` ubah jadi `Disabled`
- Setelah itu simpan dengan tekan `F10` lalu `Enter`


### 2. Burn Image BIOS Ke Flashdisk
- Ekstrak Bios-image-x250.7z
- Lalu jalankan perintah berikut
```bash
sudo dd if=x250.img of=/dev/sdx bs=64K
```
NOTE :
- Ganti `/dev/sdx` sesuai dengan jalur flashdisk
- Ganti `x250.img` sesuai dengan nama file IMG
- Untuk mengeceknya
```bash
lsblk
```
- Jika file BIOS masih berfomat ISO, Ubah dulu ke IMG
- Jalankan perintah berikut :
```bash
sudo apt-get install genisoimage
geteltorito -o x250.img n10ur29w.iso
```
NOTE :
- Ganti `n10ur29w.iso` sesuai dengan nama file ISO
- Untuk `x250.img` bebas diganti nama sesuai keinginan


### 3. Masukan logo

Salin file logo ke dalam flashdisk, tepatnya didalam folder FLASH
Ubah namanya menjadi :
- `logo1.gif`
- `logo2.gif`


### 4. Boot dari USB

- Restart laptop
- Saat boot, tekan `F12` sampai muncul pilihan
- Lalu pilih USB flashdisk tadi
- Setelah muncul menu, pilih saja nomor 2
- Lalu tinggal Y dan Enter saja sampai selesai

