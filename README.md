# VNC — Yapılacaklar Listesi

## 0. GENEL SİSTEM MİMARİSİ

* Laravel → Web paneli, kullanıcı yönetimi, API, komut logları
* Node.js → WebSocket sunucusu, düşük gecikmeli VNC aktarımı
* Kotlin (Android Agent) → Ekran görüntüsü, komut çalıştırma, API & WS bağlantısı

---

## 1. SUNUCU KURULUMU

– Ubuntu + Nginx + Laravel + Node.js

* Ubuntu güncellemesi yapılacak
* Gerekli paketler kurulacak
* Composer kurulacak
* Node.js + PM2 kurulacak

* CyberPanel kurulumu
* Domain + SSL ayarlanacak
* Laravel proje dizini ayarlanacak
* Node.js servisleri için reverse proxy yapılacak


---

## 2. LARAVEL (WEB PANELİ – BACKEND)

* Proje kurulumu
* Admin Auth sistemi
* Role-permission sistemi
* REST API endpointlerinin tasarlanması
* Komut kuyruğu sistemi
* VNC entegrasyon uç noktalarının eklenmesi
* Panel arayüz bileşenlerinin hazırlanması
* Güvenlik yapılandırmaları (JWT, rate limit, CSRF)

---

## 3. NODE.JS (GERÇEK ZAMANLI VNC & WEBSOCKET)

* WebSocket sunucusunun hazırlanması
* Her cihaz için WS kanal yönetimi
* Android’den gelen frame’in işlenmesi
* Panel’e frame aktarımı
* Komut tüneli yönetimi
* Bağlantı kopma/yeniden bağlanma yönetimi
* Yük dağıtım mimarisi

---

## 4. ANDROID AGENT (KOTLIN)

* Servis & izinlerin hazırlanması
* Laravel API entegrasyonu
* Keepalive sistemi
* Komut işleyici modülleri
* VNC ekran paylaşımı
* WebSocket aktarımı
* Güvenlik (SSL, token doğrulama)
* Self-update yapısı

---

## 5. VERİTABANI TASARIMI

* devices tablosu
* device_commands tablosu
* sms_logs / call_logs tabloları
* vnc_sessions tablosu

---

## 6. ALTYAPI & DAĞITIM

* Laravel API sunucusu
* Node.js WS sunucusu
* Veritabanı sunucusu
* Redis sunucusu
* Load balancer
* CDN (opsiyonel)
* Docker ortamı hazırlığı

---

## 7. TEST & MONITORING

* VNC gecikme testleri
* FPS testleri
* Komut gecikme testleri
* Android izinlerinin doğruluğu
* Bağlantı kopma senaryoları
* Monitoring paneli kurulumu (CPU/RAM, cihaz online/offline, FPS izlemesi)

---
