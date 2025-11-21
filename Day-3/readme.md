# Tugas Day 3 - Manage Server w/ Terminal

---

## 1. Konfigurasi SSH (Public Key Only)
Pada tugas ini, saya melakukan pengamanan server dengan cara menonaktifkan login menggunakan password biasa dan mewajibkan penggunaan **SSH Public Key**.

**Langkah-langkah yang saya lakukan:**

1.  Membuat pasangan kunci (Key Pair) di laptop lokal menggunakan perintah `ssh-keygen`.
   
   <img width="1483" height="762" alt="Screenshot 2025-11-21 133723" src="https://github.com/user-attachments/assets/b13b2663-d9c4-4368-98cd-23981ad4fb37" />

2.  Menyalin **Public Key** ke dalam file `~/.ssh/authorized_keys` di dalam server.
    
   <img width="1904" height="1012" alt="image" src="https://github.com/user-attachments/assets/918bd22c-7de4-4f7e-bc4c-8147ca062181" />
   
  a) Buka file menggunakan notepad yang bernama kunci.pub

   <img width="1426" height="778" alt="image" src="https://github.com/user-attachments/assets/bf3891de-130a-4475-bdb2-3dc70ac455c0" />
   
  b) Copy keysnya 

  <img width="1483" height="762" alt="Screenshot 2025-11-21 135006" src="https://github.com/user-attachments/assets/f2f3f3d0-24c5-4a40-9bb9-76f59a07eb86" />

  c) Ketik comamnd seperti diatas 
  
  <img width="1483" height="762" alt="Screenshot 2025-11-21 135006" src="https://github.com/user-attachments/assets/f6cd3a29-7551-4966-9de1-20bd99faf220" />

  d) Paste keys nya ke server, jika sudah tekan ctrl+o untuk save 

  <img width="1483" height="762" alt="Screenshot 2025-11-21 134839" src="https://github.com/user-attachments/assets/395d439b-4e33-4787-9153-9b2334fd4e3e" />



**Bukti Berhasil Login Tanpa Password:**
Berikut adalah screenshot saat saya login ke server dan langsung masuk tanpa diminta password:

<img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/2bd320e3-7d6f-4ac3-b9bf-03bf346c0515" />

---

## 2. Text Manipulation (Linux Command)

1.  **`echo`**: Saya gunakan untuk membuat file baru berisi beberapa baris teks.

     <img width="1483" height="762" alt="image" src="https://github.com/user-attachments/assets/ea4de6aa-9a99-41f4-a9da-bbbee80f7e43" />

2.  **`cat`**: Saya gunakan untuk melihat/membaca isi file tersebut.

     <img width="1483" height="762" alt="Screenshot 2025-11-21 172717" src="https://github.com/user-attachments/assets/042139e5-cb9a-4799-992a-f0f3f836cc5c" />
   
3.  **`grep`**: Saya gunakan untuk mencari kata kunci spesifik di dalam file.

     <img width="1483" height="762" alt="Screenshot 2025-11-21 173619" src="https://github.com/user-attachments/assets/23313e90-737c-470f-9867-f76dff2ed6c3" />

4.  **`sed`**: Saya gunakan untuk mengganti kata tertentu (Find & Replace) dalam tampilan output.
   
    <img width="1483" height="762" alt="Screenshot 2025-11-21 173252" src="https://github.com/user-attachments/assets/7b5f8064-26d8-4608-bf55-c7956576c2f8" />
   
---

## 3. Konfigurasi Firewall (UFW)
Terakhir, saya mengaktifkan **UFW (Uncomplicated Firewall)** untuk mengamankan port server. Saya hanya membuka port-port tertentu sesuai instruksi tugas.

| Port | Protocol | Kegunaan |
| :--- | :--- | :--- |
| **22 / OpenSSH** | TCP | Akses remote SSH (Wajib dibuka biar kita nggak terkunci dari luar) |
| **80** | TCP | HTTP (Akses Web Server standar) |
| **443** | TCP | HTTPS (Akses Web Server aman) |
| **3000, 5000** | TCP | Port untuk aplikasi backend (misal: Node.js / Python) |
| **6969** | TCP | Port khusus (Custom App) sesuai permintaan soal |

**Bukti Status UFW:**

Berikut adalah hasil dari perintah `sudo ufw status` yang menunjukkan port di atas sudah berstatus **ALLOW**:

  <img width="1483" height="762" alt="Screenshot 2025-11-21 183933" src="https://github.com/user-attachments/assets/58fb18d9-5fc7-4b38-a2d0-35bf812a289d" />

- Status: active (artinya firewall nyala).
- Semua port (22, 80, 443, 3000, 5000, 6969) sudah terdaftar ALLOW.
- Ada OpenSSH di paling atas (aman biar gak terkunci).
