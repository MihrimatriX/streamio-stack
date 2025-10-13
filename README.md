# 🎬 Stremio Self-Hosted Stack

[![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
[![Stremio](https://img.shields.io/badge/Stremio-FF6B35?style=for-the-badge&logo=stremio&logoColor=white)](https://www.stremio.com/)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=for-the-badge)](LICENSE)

> **Self-hosted Stremio media streaming server with Docker Compose setup**

---

## 🇹🇷 Türkçe

### 📋 Açıklama

Bu Docker Compose yapılandırması, kendi sunucunuzda Stremio'yu host etmenizi sağlar. Torrentio, OpenSubtitles ve diğer popüler eklentilerle birlikte gelir.

### 🚀 Hızlı Başlangıç

```bash
# Repository'yi klonlayın
git clone https://github.com/yourusername/stremio-stack.git
cd stremio-stack

# Servisleri başlatın
docker-compose up -d

# Logları kontrol edin
docker-compose logs -f stremio
```

### 📱 Erişim Noktaları

| Servis | URL | Açıklama |
|--------|-----|----------|
| **Stremio Web** | http://localhost:3579 | Ana web arayüzü |
| **Stremio Server** | http://localhost:11470 | API sunucusu |

### 🔌 Önceden Yapılandırılmış Eklentiler

- ✅ **Torrentio** - Torrent akışı
- ✅ **OpenSubtitles** - Altyazı desteği
- ✅ **TMDB** - Film/dizi bilgileri
- ✅ **TR Altyazi** - Türkçe altyazılar
- ✅ **Dizipal** - Türkçe içerik
- ✅ **Anime Altyazi** - Anime içerikleri

### ⚙️ Yapılandırma

```yaml
# docker-compose.yml
services:
  stremio:
    image: tsaridas/stremio-docker:latest
    ports:
      - "3579:8080"    # Web arayüzü
      - "11470:11470"  # API sunucusu
    environment:
      - TZ=Europe/Istanbul
    volumes:
      - ./stremio-data:/root/.stremio-server
```

### 💾 Cache Yönetimi

```bash
# Cache boyutunu kontrol et
du -sh ./stremio-data/cache/

# Cache temizle
docker-compose exec stremio rm -rf /root/.stremio-server/cache/*
```

### 🆘 Sorun Giderme

```bash
# Servis durumunu kontrol et
docker-compose ps

# Logları incele
docker-compose logs stremio

# Yeniden başlat
docker-compose restart stremio
```

---

## 🇺🇸 English

### 📋 Description

This Docker Compose configuration allows you to host Stremio on your own server. Comes pre-configured with Torrentio, OpenSubtitles, and other popular addons.

### 🚀 Quick Start

```bash
# Clone the repository
git clone https://github.com/yourusername/stremio-stack.git
cd stremio-stack

# Start services
docker-compose up -d

# Check logs
docker-compose logs -f stremio
```

### 📱 Access Points

| Service | URL | Description |
|---------|-----|-------------|
| **Stremio Web** | http://localhost:3579 | Main web interface |
| **Stremio Server** | http://localhost:11470 | API server |

### 🔌 Pre-configured Addons

- ✅ **Torrentio** - Torrent streaming
- ✅ **OpenSubtitles** - Subtitle support
- ✅ **TMDB** - Movie/TV show information
- ✅ **TR Altyazi** - Turkish subtitles
- ✅ **Dizipal** - Turkish content
- ✅ **Anime Altyazi** - Anime content

### ⚙️ Configuration

```yaml
# docker-compose.yml
services:
  stremio:
    image: tsaridas/stremio-docker:latest
    ports:
      - "3579:8080"    # Web interface
      - "11470:11470"  # API server
    environment:
      - TZ=Europe/Istanbul
    volumes:
      - ./stremio-data:/root/.stremio-server
```

### 💾 Cache Management

```bash
# Check cache size
du -sh ./stremio-data/cache/

# Clear cache
docker-compose exec stremio rm -rf /root/.stremio-server/cache/*
```

### 🆘 Troubleshooting

```bash
# Check service status
docker-compose ps

# Examine logs
docker-compose logs stremio

# Restart service
docker-compose restart stremio
```

---

## 🔒 Legal Notice

**⚠️ Important**: This software is for educational purposes only. Users are responsible for complying with local laws and regulations. Only stream content you have the right to access.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## ⭐ Support

If you found this project helpful, please give it a star! ⭐
