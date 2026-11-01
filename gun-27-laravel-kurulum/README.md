# Gün 27 · Laravel kurulum ve istek döngüsü

[← Gün 26](../gun-26-sql-transaction/README.md) · [Ana yol haritası](../README.md) · [Gün 28 →](../gun-28-laravel-controller/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Laravel kurulum ve istek döngüsü konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Laravel yönlendirme, doğrulama ve veri erişimini yapılandırır. Resmî kurulum rehberine göre ayrı Laravel projesi oluştur. PHP/Composer gereksinimlerini kullandığın ana sürümle eşleştir. Örnek routes/web.php içine eklenebilir.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```php
<?php
use Illuminate\Support\Facades\Route;
// Basit sağlık kontrolü veritabanına bağlı olmadan HTTP akışını doğrular.
Route::get('/health', function () {
    return response()->json(['status' => 'ok']);
});
```

**Beklenen davranış:** /health 200 ve status:ok döndürür.

## Uygulama

php artisan serve ile projeyi çalıştır. /health yanıtını ve php artisan route:list çıktısını incele.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Bu kontrol veritabanının sağlıklı olduğunu kanıtlamaz; yalnızca uygulama yanıtını sınar.

## Kaynak

[Resmî dokümantasyon](https://laravel.com/docs/13.x/installation)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
