# Tugas Day 2 - Basic Shell & Networking

---

## 1. Diagram Jaringan (CIDR /28)
Di tugas ini, saya merancang topologi jaringan sederhana menggunakan **CIDR 192.168.11.0/28**.

Karena aturannya pakai subnet mask **/28**, berarti jatah IP-nya cukup terbatas. Total cuma ada **16 IP**, dan yang efektif bisa dipakai buat device cuma **14 IP** (mulai dari `.1` sampai `.14`).

### Detail Setup Device:
Berikut adalah pembagian IP yang saya buat untuk 4 device tersebut:

<img src="https://github.com/user-attachments/assets/df03d677-3aa2-4e6a-832c-2a03d87a42f5" width="600" alt="Diagram Jaringan" />

---

| Device Name | IP Address | Subnet Mask | Keterangan |
| :--- | :--- | :--- | :--- |
| **Router / Gateway** | `192.168.11.1` | `255.255.255.240` | Pintu gerbang utama jaringan |
| **Server Utama** | `192.168.11.2` | `255.255.255.240` | Menggunakan OS Ubuntu Server |
| **Client Laptop A** | `192.168.11.3` | `255.255.255.240` | Dipakai oleh Admin |
| **Client Laptop B** | `192.168.11.4` | `255.255.255.240` | Dipakai oleh Staff |

---

## 2. Apa Bedanya SH dan BASH?
Dari yang saya pelajari, ini perbedaan mendasar antara keduanya:

### SH (Shell)
Bisa dibilang ini versi "jadul" atau versi klasik dari command line di Unix/Linux.
* **Kondisi:** Fiturnya bener-bener dasar banget.
* **Kekurangan:** Agak kaku dipakainya. Kita gak bisa tekan tombol `Tab` buat *auto-complete* command, dan gak bisa tekan panah atas buat cari history command.
* **Penggunaan:** Biasanya cuma dipakai buat script sistem yang simpel banget supaya bisa jalan di mesin-mesin tua.

### BASH (Bourne-Again Shell)
Nah, kalau ini versi modern-nya, ibarat cucunya SH. Ini yang sekarang kita pakai sehari-hari di Ubuntu.
* **Kelebihan:** Fiturnya udah lengkap dan memanjakan pengguna.
* **Kenapa enak:** Kita bisa tekan `Tab` kalau malas ngetik panjang (auto-complete), tampilannya ada warnanya, dan history command tersimpan rapi.

> **Singkatnya** BASH itu versi *upgrade* dari SH yang jauh lebih pinter dan nyaman buat kerja sehari-hari.

---

## 3. Catatan Command Linux (Cheat Sheet)
Ini adalah rangkuman command Linux yang sudah saya coba dan menurut saya penting untuk diingat:

### 📂 Utak-atik File & Folder
| Command | Fungsi |
| :--- | :--- |
| `pwd` | Cek kita lagi ada di folder mana sekarang (*Print Working Directory*). |
| `ls -lah` | Lihat isi folder secara detail (file tersembunyi juga kelihatan). |
| `mkdir -p folder/baru` | Bikin folder baru (bisa langsung bikin folder di dalamnya). |
| `rm -rf <nama>` | Hapus folder beserta isinya secara paksa (Harus hati-hati pakainya!). |
| `cp -r <asal> <tujuan>` | Copy folder dan seluruh isinya ke tempat lain. |
| `cat <file>` | Intip isi file teks langsung lewat terminal. |

### 🔧 Izin Akses & System
| Command | Fungsi |
| :--- | :--- |
| `chmod 777 <file>` | Kasih izin full akses (baca, tulis, eksekusi) ke file tersebut. |
| `chown user:group <file>` | Ganti pemilik file. |
| `sudo su` | Masuk ke mode "Dewa" (Root User). |
| `history` | Lihat jejak command apa aja yang pernah kita ketik sebelumnya. |

### 🌐 Networking (Cek Jaringan)
| Command | Fungsi |
| :--- | :--- |
| `ping google.com` | Tes koneksi internet jalan atau nggak. |
| `ip a` | Cek IP Address di komputer sendiri. |
| `curl ifconfig.me` | Cek IP Public internet kita lewat terminal. |
| `netstat -tuln` | Cek "pintu" (port) mana aja yang lagi kebuka di server. |

### 📊 Monitoring (Nilai Plus ++)
| Command | Fungsi |
| :--- | :--- |
| `htop` | Task manager yang tampilannya keren buat pantau CPU & RAM real-time. |
| `df -h` | Cek sisa kapasitas Hardisk. |
| `free -m` | Cek sisa RAM yang tersedia. |
| `grep "kata" <file>` | Cari kata spesifik di dalam file (berguna banget buat cari error di log). |
