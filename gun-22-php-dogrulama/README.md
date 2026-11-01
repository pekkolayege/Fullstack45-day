# Gün 22 · PHP doğrulama ve hata yönetimi

[← Gün 21](../gun-21-composer/README.md) · [Ana yol haritası](../README.md) · [Gün 23 →](../gun-23-postgresql-model/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

PHP doğrulama ve hata yönetimi konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Dış veri eksik, farklı tipte veya bozuk olabilir. JSON ayrıştırma hatasıyla iş kuralı hatasını ayır. Örnek HTTP handler parçasıdır; JSON yanıt başlığı önceden ayarlanmış olmalıdır.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```php
<?php
try {
    $data = json_decode(file_get_contents('php://input'), true, 512, JSON_THROW_ON_ERROR);
    $title = is_array($data) ? ($data['title'] ?? null) : null;
    // trim öncesi tip kontrolü yanlış girdide TypeError oluşmasını engeller.
    if (!is_string($title) || trim($title) === '') {
        http_response_code(422);
        echo json_encode(['error' => 'Başlık zorunludur.']);
        return;
    }
    echo json_encode(['title' => trim($title)]);
} catch (JsonException $error) {
    http_response_code(400);
    echo json_encode(['error' => 'Geçersiz JSON.']);
}
```

**Beklenen davranış:** Bozuk JSON 400, geçersiz başlık 422, geçerli başlık 200 üretir.

## Uygulama

Bozuk JSON, null, sayı başlık ve geçerli başlık için dört istek dene.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

İstisnanın dosya yolu ve yığın izini üretim yanıtına yazma.

## Kaynak

[Resmî dokümantasyon](https://www.php.net/manual/en/function.json-decode.php)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
