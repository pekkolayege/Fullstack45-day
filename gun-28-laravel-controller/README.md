# Gün 28 · Route ve controller

[← Gün 27](../gun-27-laravel-kurulum/README.md) · [Ana yol haritası](../README.md) · [Gün 29 →](../gun-29-laravel-migration/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Route ve controller konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Route isteği davranışa yönlendirir; controller HTTP giriş/çıkışını düzenler. Controller'ı php artisan make:controller ProjectController ile oluştur. Aşağıdaki metot sınıf içine eklenir; veriler bu alıştırmada örnektir.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```php
public function index(): \Illuminate\Http\JsonResponse
{
    // Tutarlı data zarfı istemci tarafında yanıt okumayı kolaylaştırır.
    return response()->json(['data' => [
        ['id' => 1, 'name' => 'Öğrenme projesi'],
    ]]);
}
```

**Beklenen davranış:** /projects yanıtında data listesi bulunur; route:list controller metodunu gösterir.

## Uygulama

Route::get('/projects', [ProjectController::class, 'index']) yönlendirmesini doğru import ile ekle.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Controller içine bütün iş kurallarını ve ham SQL'i biriktirme.

## Kaynak

[Resmî dokümantasyon](https://laravel.com/docs/13.x/controllers)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
