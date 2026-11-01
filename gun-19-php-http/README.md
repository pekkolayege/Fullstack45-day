# Gün 19 · PHP ile HTTP ve JSON

[← Gün 18](../gun-18-php-diziler/README.md) · [Ana yol haritası](../README.md) · [Gün 20 →](../gun-20-php-oop/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

PHP ile HTTP ve JSON konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

HTTP yanıtı durum kodu, başlıklar ve gövdeden oluşur. JSON yanıtında Content-Type doğru olmalıdır. Aşağıdaki dosyayı index.php olarak kaydedip bulunduğu klasörde php -S 127.0.0.1:8000 çalıştır. Bu sunucu yalnızca yerel alıştırma içindir.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```php
<?php
declare(strict_types=1);
header('Content-Type: application/json; charset=utf-8');
// Yanıt kodu istemcinin sonucu anlamasını sağlar.
http_response_code(200);
echo json_encode(['data' => ['message' => 'API hazır']], JSON_THROW_ON_ERROR);
```

**Beklenen davranış:** Başarılı yanıtta 200 ve geçerli JSON; bulunamadı örneğinde 404 vardır.

## Uygulama

Tarayıcı ağ panelinde durum kodunu ve Content-Type değerini incele. Bir bulunamadı yanıtı üret.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

header çağrısından önce echo veya dosya başında boşluk gönderme.

## Kaynak

[Resmî dokümantasyon](https://www.php.net/manual/en/function.header.php)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
