# Gün 42 · Güvenlik kontrol noktası

[← Gün 41](../gun-41-erisilebilirlik-performans/README.md) · [Ana yol haritası](../README.md) · [Gün 43 →](../gun-43-yayinlama/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Güvenlik kontrol noktası konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Güvenlik sınırları sunucuda uygulanır. Kullanıcının gönderdiği proje kimliği veya rol güvenilir değildir. Giriş hız sınırlaması, veri kapsamı, parola özeti ve üretimde hata gizleme birlikte ele alınmalıdır. Örnek Laravel rate limiter tanımıdır; AppServiceProvider boot metoduna uygun importlarla eklenir.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```php
\Illuminate\Support\Facades\RateLimiter::for('login', function (\Illuminate\Http\Request $request) {
    // Basit eğitim sınırı; gerçek sınır trafik ve tehdit modeline göre ayarlanır.
    return \Illuminate\Cache\RateLimiting\Limit::perMinute(5)
        ->by($request->ip());
});
// Giriş rotasına ayrıca throttle:login middleware'i bağlanmalıdır.
```

**Beklenen davranış:** İzinsiz işlem veri değiştirmez; istek sınırı aşıldığında 429 gelir.

## Uygulama

Başka proje kimliği, izinsiz rol alanı, tekrarlı giriş ve HTML başlık senaryolarını dene.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Rate limiter tanımlamak yeterli değildir; ilgili rotada uygulanmalıdır.

## Kaynak

[Resmî dokümantasyon](https://laravel.com/docs/13.x/rate-limiting)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
