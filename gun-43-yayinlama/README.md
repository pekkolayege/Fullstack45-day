# Gün 43 · Yayınlama kavramları

[← Gün 42](../gun-42-guvenlik/README.md) · [Ana yol haritası](../README.md) · [Gün 44 →](../gun-44-ci-operasyon/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Yayınlama kavramları konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Bu ders eğitim reposunu bir siteye dönüştürmez; öğrencinin ayrı uygulamasının üretime hazırlanmasını anlatır. Üretim ve geliştirme ortamları ayrılmalı, HTTPS kullanılmalı ve Laravel document root public klasörünü göstermelidir. Aşağıdaki değerler .env örneği parçalarıdır.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```dotenv
# Ayrıntılı hata ekranları üretimde kapalı olmalıdır.
APP_ENV=production
APP_DEBUG=false
# Gerçek alan adını kendi uygulamana göre ayarla.
APP_URL=https://example.com
SESSION_SECURE_COOKIE=true
```

**Beklenen davranış:** Yeni bir ortamda talimatlar izlenebilir; sırlar repoda yer almaz.

## Uygulama

Uygulamanın ortam değişkenlerini sır içermeyen bir .env.example dosyasında belgele. Kurulum ve migration sırasını yaz.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Mevcut APP_KEY değerini gelişigüzel değiştirmek şifreli verileri ve oturumları etkiler.

## Kaynak

[Resmî dokümantasyon](https://laravel.com/docs/13.x/deployment)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
