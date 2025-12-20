# Instalasi libvirt di Ubuntu 24.04

Untuk menginstal `libvirt` di Ubuntu 24.04, ikuti langkah-langkah berikut:

**Syarat utama**: Pastikan CPU Anda mendukung virtualisasi. Anda dapat memeriksa dukungan virtualisasi dengan menjalankan perintah berikut:
```bash
lscpu | grep Virtualization
```
Jika output menunjukkan `VT-x` atau `AMD-V`, maka CPU Anda mendukung virtualisasi.

1. **Perbarui sistem**:
   ```bash
   sudo apt update && sudo apt upgrade -y
   ```

2. **Instal libvirt**:
   ```bash
   sudo apt install libvirt-daemon-system libvirt-clients -y
   ```

3. **Tambahkan pengguna ke grup libvirt**:
   ```bash
   sudo usermod -aG libvirt $(whoami)
   ```
   Setelah menjalankan perintah ini, logout dan login kembali agar perubahan berlaku.

4. **Mulai dan aktifkan layanan libvirt**:
   ```bash
   sudo systemctl start libvirtd
   sudo systemctl enable libvirtd
   ```

5. **Verifikasi instalasi**:
   ```bash
   virsh --version
   ```

6. **Bukti Instalasi**:
   Berikut adalah gambar sebagai bukti bahwa instalasi telah berhasil:
   ![Bukti Instalasi](images/kvm.png)

Dengan langkah-langkah di atas, `libvirt` telah berhasil diinstal dan siap digunakan.
