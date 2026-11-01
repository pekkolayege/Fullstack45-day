# Gün 17 · PHP ortamı ve temel tipler

[← Gün 16](../gun-16-frontend-kontrol/README.md) · [Ana yol haritası](../README.md) · [Gün 18 →](../gun-18-php-diziler/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

PHP ortamı ve temel tipler konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

PHP sunucuda veya komut satırında çalışır. php -v ile kurulumu kontrol et. Örneği example.php olarak kaydedip php example.php ile çalıştır. strict_types, tip bildirimleri olan çağrılarda istenmeyen örtük dönüşümleri azaltır; dış girdiyi doğrulamaz.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```php
<?php
declare(strict_types=1);
// Parametre ve dönüş tipi, fonksiyonun sözleşmesini açıklar.
function greeting(string $name): string {
    return 'Merhaba, ' . trim($name);
}
echo greeting(' Ege ') . PHP_EOL;
```

**Beklenen davranış:** Örnek Merhaba, Ege yazdırır; boş başlık görevin tarafından reddedilir.

## Uygulama

Görev başlığı kabul eden, trim uygulayan ve boş başlığı reddeden fonksiyon yaz.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

PHP kodunu tarayıcıda dosya olarak açmak PHP yorumlayıcısını çalıştırmaz.

## Kaynak

[Resmî dokümantasyon](https://www.php.net/manual/tr/langref.php)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
