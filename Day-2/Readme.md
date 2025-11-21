# Tugas Day 2 - Basic Shell & Networking

---

## 1. Diagram Jaringan (CIDR /28)
Berikut adalah desain topologi jaringan dengan aturan **CIDR 192.168.11.0/28**.

Karena menggunakan subnet mask **/28**, maka total IP yang tersedia hanya **16 IP** (Host yang bisa dipakai hanya 14, dari `.1` sampai `.14`).

### Detail Konfigurasi Device:
| Device Name | IP Address | Subnet Mask | Keterangan |
| :--- | :--- | :--- | :--- |
| **Router / Gateway** | `192.168.11.1` | `255.255.255.240` | Gerbang utama jaringan |
| **Server Utama** | `192.168.11.2` | `255.255.255.240` | Linux Ubuntu Server |
| **Client Laptop A** | `192.168.11.3` | `255.255.255.240` | User Admin |
| **Client Laptop B** | `192.168.11.4` | `255.255.255.240` | User Staff |

---

## 2. Perbedaan SH dan BASH
Berikut adalah perbedaan antara SH (Shell) dan BASH (Bourne-Again Shell) berdasarkan pemahaman saya:

### SH (Shell)
Ini adalah versi "nenek moyang" atau versi klasik dari command line di Unix.
* **Fitur:** Sangat dasar dan minim fitur.
* **Kelemahan:** Tidak ada fitur canggih seperti *auto-complete* (tab) atau history command (panah atas).
* **Kegunaan:** Biasanya hanya dipakai untuk script sistem yang sangat basic agar bisa jalan di semua mesin unix lama.

### BASH (Bourne-Again Shell)
Ini adalah versi modern dan penyempurnaan dari SH. Ini yang biasa kita pakai di Ubuntu saat ini.
* **Fitur:** Kaya fitur. Bisa *auto-complete* perintah (tekan Tab), ada warna teks, dan menyimpan riwayat perintah (History).
* **Kelebihan:** Lebih ramah pengguna (user-friendly) dan lebih enak dipakai untuk *scripting* yang kompleks.

> **Kesimpulannya adalah BASH adalah versi upgrade dari SH yang lebih pintar dan nyaman dipakai sehari-hari.

---

## 3. Linux Command Cheat Sheet
Berikut adalah daftar perintah Linux yang saya pelajari (termasuk beberapa command untuk monitoring & networking):

### 📂 File & Directory Management
| Command | Fungsi |
| :--- | :--- |
| `pwd` | Melihat posisi folder kita sekarang (*Print Working Directory*). |
| `ls -lah` | Melihat daftar file secara detail (termasuk file tersembunyi). |
| `mkdir -p folder/baru` | Membuat folder sekaligus sub-foldernya. |
| `rm -rf <nama>` | Menghapus folder beserta isinya secara paksa (Hati-hati!). |
| `cp -r <asal> <tujuan>` | Meng-copy folder dan isinya. |
| `cat <file>` | Membaca isi file teks langsung di terminal. |

### 🔧 System & Permissions
| Command | Fungsi |
| :--- | :--- |
| `chmod 777 <file>` | Memberikan hak akses penuh (Read, Write, Execute) ke file. |
| `chown user:group <file>` | Mengubah pemilik file. |
| `sudo su` | Masuk sebagai Super User (Root). |
| `history` | Melihat riwayat perintah yang pernah kita ketik. |

### 🌐 Networking (Jaringan)
| Command | Fungsi |
| :--- | :--- |
| `ping google.com` | Cek koneksi internet. |
| `ip a` | Melihat IP Address komputer kita (pengganti `ifconfig`). |
| `curl ifconfig.me` | Cek IP Public kita lewat terminal. |
| `netstat -tuln` | Melihat port mana saja yang sedang terbuka/jalan. |

### 📊 Monitoring (Nilai ++)
| Command | Fungsi |
| :--- | :--- |
| `htop` | Task manager interaktif (lebih bagus dari `top`) untuk lihat RAM/CPU. |
| `df -h` | Cek sisa kapasitas Hardisk (*Disk Free*). |
| `free -m` | Cek sisa RAM yang tersedia. |
| `grep "kata" <file>` | Mencari kata tertentu di dalam file (sangat berguna buat cari error di log). |
