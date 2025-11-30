# VNC

## 0. GENEL SİSTEM MİMARİSİ

* Laravel → Web paneli, kullanıcı yönetimi, API, komut logları
* Node.js → WebSocket sunucusu, düşük gecikmeli VNC aktarımı
* Kotlin (Android Agent) → Ekran görüntüsü, komut çalıştırma, API & WS bağlantısı

---

## 1. SUNUCU KURULUMU

### Seçenek A – Ubuntu + Nginx + Laravel + Node.js

* Ubuntu güncellemesi yapılacak
* Gerekli paketler kurulacak
* Composer kurulacak
* Laravel proje klasörü oluşturulacak
* Node.js + PM2 kurulacak
* CyberPanel kurulumu
* PHP + Laravel gereksinimleri eklenecek
* Domain + SSL ayarlanacak
* Laravel proje dizini ayarlanacak
* Node.js servisleri için reverse proxy yapılacak
---

## 2. LARAVEL (WEB PANELİ – BACKEND)

### 2.1. Proje Hazırlığı

* Laravel kurulumu
* Çevresel değişkenlerin ayarlanması (.env)
* Migration ve seeder yapısının hazırlanması

### 2.2. Authentication & Authorization

* Admin Auth sistemi
* Role / Permission yapısı oluşturma
* Yetki bazlı erişim kontrolü
* Admin panel erişim kuralları

### 2.3. REST API Tasarımı

#### API Rotaları

* /api/device/register
* /api/devices/list
* /api/device/{id}
* /api/device/{id}/commands
* /api/device/{id}/logs
* /api/vnc/start
* /api/vnc/stop

#### API Yapılması Gerekenler:

* Request validation
* JWT token kontrolü
* Response şeması oluşturma (success/error formatı)

### 2.4. Komut Kuyruğu Sistemi

* device_commands tablosunun tasarımı
* Pending → Executed akışının yazılması
* Android Agent’ın polling veya push sistemi ile komut çekmesi

### 2.5. VNC Yönetimi

* Node.js WS sunucu URL’lerinin Laravel tarafından sağlanması
* Cihaz bazlı VNC oturumu oluşturma
* Session loglama

### 2.6. Panel Arayüzü

* Cihaz listesi sayfası
* Cihaz detay sayfası
* Canlı ekran izleme (VNC / canvas)
* Komut gönderme paneli
* SMS/Call log görüntüleme
* Komut geçmişi listeleme

### 2.7. Güvenlik

* JWT token
* API rate limit
* CSRF kontrolü
* IP güvenlik duvarı politikaları

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

## 8. PROJE SÜRESİ & MALİYET
8.1. Ortalama Yapım Süresi

Toplam geliştirme süresi: 20 – 30 iş günü
Toplam maliyet: 200.000 TL
Ödeme Planı : %50 başlangıç ödemesi - %50 proje tamamlandığında ödeme
