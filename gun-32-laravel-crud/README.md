# Gün 32 · CRUD ve sayfalama

[← Gün 31](../gun-31-laravel-validation/README.md) · [Ana yol haritası](../README.md) · [Gün 33 →](../gun-33-api-sozlesmesi/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

CRUD ve sayfalama konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Liste yanıtları sınırsız büyümemelidir. paginate veriyle sayfalama bilgisini birlikte sunar. Örnek controller metodunda kullanılacak parçadır; Project modeli, tasks ilişkisi ve ProjectPolicy:view daha önce tanımlanmalıdır.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```php
public function index(\App\Models\Project $project)
{
    // Sorgudan önce proje erişimini doğrularız.
    \Illuminate\Support\Facades\Gate::authorize('view', $project);
    return $project->tasks()->orderByDesc('id')->paginate(20);
}
```

**Beklenen davranış:** İlk sayfa en fazla 20 kayıt döndürür; başka projenin görevleri görünmez.

## Uygulama

Proje kapsamındaki görevleri listele. Ekleme ve güncellemede Form Request, silmede policy kullan.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Global Task sorgusuyla proje kapsamını yanlışlıkla aşma.

## Kaynak

[Resmî dokümantasyon](https://laravel.com/docs/13.x/pagination)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
