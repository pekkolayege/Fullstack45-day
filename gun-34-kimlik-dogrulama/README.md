# Gün 34 · Kimlik doğrulama ve parola

[← Gün 33](../gun-33-api-sozlesmesi/README.md) · [Ana yol haritası](../README.md) · [Gün 35 →](../gun-35-sanctum-csrf/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Kimlik doğrulama ve parola konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Kimlik doğrulama kimin istek yaptığını belirler. Parola geri çözülebilir biçimde saklanmaz; uygun parola özeti kullanılır. Aşağıdaki Laravel parçası özet üretme ve kontrol etmeyi gösterir; tek başına kayıt/giriş sistemi değildir.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```php
use Illuminate\Support\Facades\Hash;
// Gerçek uygulamada parola doğrulanmış istekten alınır; günlük dosyasına yazılmaz.
$plainPassword = 'yalnizca-yerel-ornek';
$hash = Hash::make($plainPassword);
$matches = Hash::check($plainPassword, $hash);
```

**Beklenen davranış:** Veritabanında düz parola yoktur; yanlış parola doğrulanmaz.

## Uygulama

Kayıt doğrulamasını, benzersiz e-postayı ve genel giriş hata mesajını tasarla.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Hash::make çıktısını tekrar üretip metin olarak karşılaştırma; Hash::check kullan.

## Kaynak

[Resmî dokümantasyon](https://laravel.com/docs/13.x/hashing)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
