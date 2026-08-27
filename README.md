# Docker Basic Commands - Nginx

## Instalasi Docker (WSL/EC2)

```bash
sudo apt update
sudo apt install docker.io
sudo usermod -aG docker $USER
sudo apt install docker-compose
# Reboot setelah perintah di atas
```

## Perintah Dasar Docker

### 1. Image - Melihat Docker Images
```bash
docker images
```
Menampilkan semua Docker images yang sudah ter-download di sistem.

### 2. Pull - Mengunduh Docker Image
```bash
docker pull nginx:latest
```
Mengunduh image Nginx versi terbaru dari Docker Hub.

### 3. Run - Menjalankan Container
```bash
docker run -d -p 80:80 --name nginx-container nginx:latest
```
Menjalankan container Nginx dengan konfigurasi:
- `-d`: Detached mode (berjalan di background)
- `-p 80:80`: Mapping port 80 host ke port 80 container
- `--name nginx-container`: Memberi nama container
- `nginx:latest`: Image yang digunakan

### 4. Stop - Menghentikan Container
```bash
docker stop nginx-container
```
Menghentikan container yang sedang berjalan.

### 5. Remove - Menghapus Container
```bash
docker rm nginx-container
```
Menghapus container yang sudah berhenti.

## Perintah Tambahan (Ekperimen dulu sebelum Stop & Remove)

### Melihat Container yang Berjalan
```bash
docker ps
```

### Melihat Semua Container (termasuk yang berhenti)
```bash
docker ps -a
```

### Masuk ke Container (Interactive Mode)
```bash
docker exec -it nginx-container /bin/bash
```

### Melihat Log Container
```bash
docker logs nginx-container
```

### Menghapus Docker Image
```bash
docker rmi nginx:latest
```

## Stop & Remove Container (Setelah Eksperimen)

### Stop Container
```bash
docker stop nginx-container
```

### Remove Container
```bash
docker rm nginx-container
```

### Remove Image (Opsional)
```bash
docker rmi nginx:latest
```

## Menggunakan Docker Compose

### Menjalankan dengan Docker Compose
```bash
docker-compose up -d
```

### Menghentikan dengan Docker Compose
```bash
docker-compose down
```

### Melihat Status Container
```bash
docker-compose ps
```

## Struktur Project

```
docker/
├── docker-compose.yml
├── nginx/
│   └── default.conf
└── html/
    └── index.html
```

## Akses Aplikasi

Setelah container berjalan, akses aplikasi di:
- Localhost: http://localhost
- IP Server: http://[your-server-ip]
