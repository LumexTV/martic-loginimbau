# Martic Solutions - Login Im Bau

Eine einfache statische Website, die anzeigt, dass der Login-Bereich sich im Bau befindet.

## 🚀 Deployment mit Docker

### Option 1: Docker Build & Run
```bash
# Docker Image erstellen
docker build -t martic-loginpage .

# Container starten
docker run -d -p 8080:80 --name martic-loginpage martic-loginpage
```

### Option 2: Docker Compose
```bash
# Mit Docker Compose starten
docker-compose up -d

# Container stoppen
docker-compose down
```

### Option 3: Für Nginx Proxy Manager

1. **Network erstellen** (falls nicht vorhanden):
   ```bash
   docker network create nginx-proxy
   ```

2. **Container starten**:
   ```bash
   docker-compose up -d
   ```

3. **In Nginx Proxy Manager einrichten**:
   - Forward Hostname/IP: `martic-loginpage`
   - Forward Port: `80`
   - Domain: `app.marticsolutions.de`

## 📁 Struktur

```
login_im_bau/
├── index.html          # Hauptseite
├── Dockerfile          # Docker Konfiguration
├── docker-compose.yml  # Docker Compose Setup
├── .dockerignore       # Docker ignore Regeln
└── README.md           # Diese Datei
```

## 🔧 Anpassungen

Um die Website zu ändern, bearbeite einfach die `index.html` Datei und erstelle das Docker Image neu:

```bash
docker-compose down
docker-compose up -d --build
```

## 🌐 Zugriff

Nach dem Start ist die Website erreichbar unter:
- Lokal: `http://localhost:8080`
- Mit Proxy Manager: `https://app.marticsolutions.de`
