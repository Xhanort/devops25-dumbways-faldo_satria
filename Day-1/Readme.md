# Tugas Day 1 - Introduction to DevOps

## 1. Apa itu DevOps?
DevOps adalah budaya kerja yang menyatukan tim Developer dan Operations agar proses rilis aplikasi menjadi lebih cepat namun tetap stabil. Terutama dengan mengandalkan otomatisasi untuk meminimalkan pekerjaan manual.

---

## 2. Langkah Instalasi Ubuntu Server
Berikut adalah langkah-langkah instalasi yang saya lakukann :

1. **Download dan install Ubuntu Server dan VirtualBox**
   
   <img width="1920" height="1020" alt="Screenshot 2025-11-18 142045" src="https://github.com/user-attachments/assets/de4e5243-0b58-4ef4-b02d-817aa2a891c1" />
   Kunjungi web untuk downloadnya 
   
   https://ubuntu.com/download/server ( Ubuntu Server)
   
   https://www.virtualbox.org/ ( VirtualBox)

   Jika sudah,berikut adalah tampilan dari virtualbox nya
   
   <img width="1049" height="989" alt="Screenshot 2025-11-18 142722" src="https://github.com/user-attachments/assets/30f5ee3f-df92-400b-abb0-8ef19b595da1" />

2. **Setup Ubuntu Server**

   Setelah menginstall virtualboxnya , langkah selanjutnya adalah setup untuk ubuntu servernya

   a) Klik *New* untuk membuat servernya
    
   <img width="1020" height="507" alt="Screenshot 2025-11-18 143222" src="https://github.com/user-attachments/assets/042c641c-ada2-4aea-a3d6-1f8b89af118a" />

    - Vm name   : Nama project
    - Vm Folder : Path dari virtualbox
    - ISO Image : File ubuntu server yang di dowload yang berformat ISO
      
   b) Jika Sudah klik *Next* maka akan masuk ke step berikutnya 
  
   <img width="1020" height="507" alt="Screenshot 2025-11-18 143620" src="https://github.com/user-attachments/assets/443a7090-17ec-4259-9398-f8df32a5c601" />

   - Base Memory     : Ram yang dipakai untuk servernya
   - Number Of Cpu   : Core cpu yang akan dipakai untuk servernya
   - Disk Size       : Storage yang dipakai untuk servernya

   c) Klik *Next* untuk lanjut ke step berikutnya

   <img width="1020" height="507" alt="Screenshot 2025-11-18 143641" src="https://github.com/user-attachments/assets/c44154a8-868f-4c44-abc5-5f0399320861" />

   Tampilan diatas adalah rangkuman spesifikasi servernya, jika sudah klik *Finish*, Maka tampilannya akan seperti itu 

   <img width="1049" height="989" alt="Screenshot 2025-11-18 143707" src="https://github.com/user-attachments/assets/c3740d46-4c9c-488e-ad55-8b671c1b28eb" />

   d) Klik *Start* untuk memulai servernya, lalu klik *install* ubuntu server

   <img width="1280" height="800" alt="VirtualBox_project_dumbways_18_11_2025_15_49_01" src="https://github.com/user-attachments/assets/2d0d4f13-93bd-4c0c-b0ce-bb2f4f48194f" />

   Tampilan diatas adalah memilih bahasa yang akan digunakan

   e) Klik *Done* untuk lanjut ke step berikutnya

   <img width="1280" height="800" alt="VirtualBox_project_dumbways_18_11_2025_15_49_46" src="https://github.com/user-attachments/assets/f023b696-dd12-4576-a809-0b044940ce5f" />

   Ini adalah tampilan dari tipe instalasinnya, disini kita pilih yang ubuntu server 
   
   - Ubuntu server              : Versi full package
   - Ubuntu server (minimized)  : Versi kecil

   f) Selanjutnya adalah konfigurasi *network*, klik *edit* dan ubah dari DHCP ke manual 
   
   <img width="1280" height="800" alt="VirtualBox_project_dumbways_19_11_2025_08_31_06" src="https://github.com/user-attachments/assets/6debda32-8f96-421f-b7a3-a4d550684ac8" />

   Berikut Tammpilannya dari configurasi networknya
   
   - Subnet          : Cakupan jaringan (kelompok IP) tempat server berada.
   - Adress          : Alamat IP unik (Nomor Rumah) untuk server ini.
   - Gateway         : Pintu gerbang (Router) untuk koneksi ke internet luar
   - Name Server     : DNS untuk menerjemahkan nama web (saya pakai Google: 8.8.8.8).
   - Search Domains  : (Opsional) Untuk domain pencarian lokal.

   Jika ingin tau configurasi internet yang digunakan , bisa ke cmd terus ketik (ipconfig), berikut tampilannya
   
   <img width="1483" height="762" alt="Screenshot 2025-11-19 083237" src="https://github.com/user-attachments/assets/4ab88ed5-34c2-4134-9ad2-a118de4db412" />

  g) Step senjutnya klik *done* saja sampai ke step *storage configuration*
  
  <img width="1280" height="800" alt="VirtualBox_project_dumbways_18_11_2025_16_14_45" src="https://github.com/user-attachments/assets/3b6257de-9395-4475-a49e-f49b597168e2" />

  h) Berikut tampilan dari storage configuration

  <img width="1280" height="800" alt="VirtualBox_project_dumbways_18_11_2025_15_53_37" src="https://github.com/user-attachments/assets/645a59f4-58f3-43bc-ad7f-dbf53a9927b6" />

   Pada tahap ini, saya memilih opsi Use an entire disk agar pengaturan lebih praktis. Seperti yang terlihat di gambar, sistem secara otomatis membagi hardisk virtual saya menjadi partisi        utama (/ atau root) untuk menyimpan data sistem, dan partisi swap sebagai memori cadangan. Saya menyetujui pengaturan default ini dengan menekan Done.

   I) Step selanjutnya adalah *profile configuration*

   <img width="1280" height="800" alt="VirtualBox_project_dumbways_18_11_2025_15_54_30" src="https://github.com/user-attachments/assets/3815dc60-9dc0-4581-8ce8-45ed2bb793b0" />

   saya diminta untuk membuat identitas pengguna utama. Di sini saya mengisi nama server dengan dumbways, serta membuat username (fldo) dan password yang nantinya akan digunakan untuk login     ke dalam sistem, selanjutnya klik *done* lalu *finish* 

   <img width="1280" height="800" alt="VirtualBox_project_dumbways_19_11_2025_18_04_36" src="https://github.com/user-attachments/assets/f06fd56e-6ef2-4474-98cb-8e21d6291482" />
    Berikut tampilan jika sudah selesai instalasinya 

    
## 3. Cek Koneksi Internet (Ping)
Setelah server menyala, saya melakukan tes koneksi dengan perintah `ping google.com`. Berikut hasilnya:

<img width="1280" height="800" alt="VirtualBox_project_dumbways_19_11_2025_23_02_41" src="https://github.com/user-attachments/assets/ac08ac0b-4ec8-42d0-9e52-dd5865cd3e3e" />
