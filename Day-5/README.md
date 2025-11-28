# Day 5 - Application in Server

Tugas ini bertujuan untuk men-deploy tiga aplikasi dengan bahasa pemrograman berbeda (NodeJS, Python, dan Golang) di server Linux, serta mengkonfigurasi Firewall (UFW) dan Process Manager (PM2).

## 1. Daftar Aplikasi & Port

| Aplikasi | Bahasa | Port | Status |
| :--- | :--- | :--- | :--- |
| Wayshub Frontend | NodeJS v12 | 3000 | Online (PM2) |
| Simple App | Python (Flask) | 5000 | Online (PM2) |
| Simple App | Golang | 8080 | Online (PM2) |

---

## 2. Screenshot Bukti (Proof of Work)

### A. Tampilan Browser
**1. NodeJS (Wayshub - Port 3000)**
![SS NodeJS](link_gambar_nodejs_kamu_disini)

**2. Python (Nama - Port 5000)**
![SS Python](link_gambar_python_kamu_disini)

**3. Golang (Golang Geming - Port 8080)**
![SS Golang](link_gambar_golang_kamu_disini)

---

### B. Konfigurasi Server
**1. Status PM2 (Semua Online)**
![SS PM2](link_gambar_pm2_kamu_disini)

**2. Versi Node (v12)**
![SS Node Version](link_gambar_node_v_kamu_disini)

**3. Status Firewall (UFW Allow)**
![SS UFW](link_gambar_ufw_kamu_disini)

---

## 3. Cara Menjalankan (Dokumentasi)

Berikut adalah perintah yang digunakan untuk menjalankan aplikasi di server:

**NodeJS:**
```bash
nvm use 12
cd wayshub-frontend
pm2 start npm --name "wayshub-frontend" -- start
