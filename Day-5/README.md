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

nd
pm2 start npm --name "wayshub-frontend" -- start
