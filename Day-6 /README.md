# Day 6 - Web Server & Reverse Proxy

Tugas ini mendemonstrasikan implementasi **Nginx** sebagai Reverse Proxy. Dengan konfigurasi ini, aplikasi Wayshub yang berjalan di port 3000 dapat diakses menggunakan nama domain standar (Port 80).

---

## 1. Arsitektur Web Server (Task 1)

### Diagram Alur
Berikut adalah gambaran bagaimana User mengakses aplikasi melalui Nginx:

![Untitled Diagram](https://github.com/user-attachments/assets/0f570a44-6c07-4fa9-8379-b2d3f662dd94)


### Penjelasan Cara Kerja
1.  **User** mengakses alamat `http://faldo.xyz` melalui browser.
2.  Request tersebut masuk ke Server dan diterima oleh **Nginx** di **Port 3000**.
3.  **Nginx** bertindak sebagai *Reverse Proxy* (Perantara). Ia meneruskan request tersebut ke **Port 3000** (tempat aplikasi NodeJS/Wayshub berjalan).
4.  Aplikasi memproses data dan memberikannya kembali ke Nginx.
5.  Nginx mengirimkan tampilan web kembali ke Browser User.

---

## 2. Konfigurasi Nginx (Task 2)

Saya menggunakan domain lokal: **`faldo.xyz`**.

**File Konfigurasi:** `/etc/nginx/sites-available/fldo.conf`

```nginx
server {
    listen 80;
    server_name faldo.xyz;

    location / {
        # Meneruskan traffic ke aplikasi NodeJS
        proxy_pass [http://192.168.1.100:3000]
    }
}
