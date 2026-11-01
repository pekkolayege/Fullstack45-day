# Gün 21 · Composer ve bağımlılıklar

[← Gün 20](../gun-20-php-oop/README.md) · [Ana yol haritası](../README.md) · [Gün 22 →](../gun-22-php-dogrulama/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Composer ve bağımlılıklar konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Composer PHP paketlerini ve otomatik sınıf yüklemeyi yönetir. composer.json istekleri, composer.lock çözülen sürümleri kaydeder. Uygulama projelerinde kilit dosyası paylaşılır. JSON yorum desteklemediği için açıklama ayrı tutulur.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```json
{
  "name": "example/fullstack45-practice",
  "description": "PHP autoload alıştırması",
  "autoload": {
    "psr-4": { "App\\": "src/" }
  }
}
```

**Beklenen davranış:** Sınıf dosyası tek tek require edilmeden new App\Task ile bulunur.

## Uygulama

Bu içeriği composer.json olarak kaydet. src/Task.php içinde App namespace'i oluştur. composer dump-autoload sonrası vendor/autoload.php dosyasını yükleyerek sınıfı kullan.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Namespace, dosya adı ve büyük/küçük harf eşleşmesini kontrol et.

## Kaynak

[Resmî dokümantasyon](https://getcomposer.org/doc/01-basic-usage.md)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
