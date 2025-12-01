# Day 5 - Application in Server

Tugas ini bertujuan untuk men-deploy tiga aplikasi dengan bahasa pemrograman berbeda (NodeJS, Python, dan Golang) di server Linux

## 1. Daftar Aplikasi & Port

| Aplikasi | Bahasa | Port | Status |
| :--- | :--- | :--- | :--- |
| Wayshub Frontend | NodeJS v12 | 3000 | Online |
| Simple App | Python (Flask) | 5000 | Online |
| Simple App | Golang | 8080 | Online |

---

## 2. Screenshot Bukti (Proof of Work)

### A. Tampilan Browser
**1. NodeJS (Wayshub - Port 3000)**

  <img width="1920" height="1020" alt="Screenshot 2025-11-27 094150" src="https://github.com/user-attachments/assets/4308eb05-b1d8-40ce-8487-f7658ceb9563" />


**2. Python (Nama - Port 5000)**

  <img width="1920" height="1020" alt="Screenshot 2025-11-27 104529" src="https://github.com/user-attachments/assets/4c69b571-9bc0-437d-829a-fa61e1c217d2" />


**3. Golang (Golang Geming - Port 8080)**
  <img width="1920" height="1020" alt="Screenshot 2025-11-27 105748" src="https://github.com/user-attachments/assets/125ecb95-3358-476f-99bc-f3f5a3fa6655" />


---

# 🏆 Challenge: App On Background

Tantangan ini mengharuskan aplikasi berjalan di *background* (mode *detached*) agar terminal tetap bisa digunakan untuk perintah lain, dan aplikasi tetap hidup meskipun sesi terminal ditutup.

Solusi yang saya gunakan adalah **PM2 (Process Manager 2)**.

## 🛠 Langkah-Langkah Pengerjaan

Berikut adalah tahapan instalasi dan konfigurasi PM2 yang saya lakukan:

### 1. Instalasi PM2
Saya menginstall PM2 secara global menggunakan NPM agar bisa diakses dari folder mana saja.

```bash
# Pastikan menggunakan Node versi 12 (Sesuai requirements app)
nvm use 12

# Install PM2 Global
npm install -g pm2
```
Berikut tampilannya 

  <img width="1920" height="1020" alt="Screenshot 2025-11-27 140154" src="https://github.com/user-attachments/assets/1fe629a0-3e92-44a9-9445-e585efe29c00" />

  
### 2. Menjalankan aplikasi 

**A) Nodejs**
```
cd ~/wayshub-frontend
pm2 start npm --name "wayshub-frontend" -- start
```

  <img width="1920" height="1020" alt="Screenshot 2025-11-27 141100" src="https://github.com/user-attachments/assets/c6d06f98-4be4-4837-82cb-6685860ba878" />
  


  <img width="1920" height="1020" alt="Screenshot 2025-11-27 141024" src="https://github.com/user-attachments/assets/3ee3378b-3f06-47e5-8319-03ea48ffe886" />


**B) Python**
```
cd ~/python
pm2 start index.py --name "tugas-python" --interpreter python3
```

<img width="1920" height="1020" alt="Screenshot 2025-11-27 142803" src="https://github.com/user-attachments/assets/b1f314d0-8c6b-4dd8-9f9e-eda67bb68539" />

<img width="1920" height="1020" alt="Screenshot 2025-11-27 142819" src="https://github.com/user-attachments/assets/9ac95ffa-2989-46ac-bea1-92fcf9023467" />

**C) Golang**
```
cd ~/golang
# Build Source Code
/usr/local/go/bin/go build -o app-ku index.go
# Run Binary
pm2 start ./app-ku --name "tugas-golang" --interpreter none
```

<img width="1793" height="505" alt="Screenshot 2025-12-01 114730" src="https://github.com/user-attachments/assets/661e0edd-58b4-44f7-be26-650a9624ea6c" />

<img width="1920" height="1020" alt="Screenshot 2025-12-01 114712" src="https://github.com/user-attachments/assets/2950e19f-469e-4c50-a1ca-399a2a815f6d" />

