# Gün 31 · Laravel Form Request

[← Gün 30](../gun-30-eloquent/README.md) · [Ana yol haritası](../README.md) · [Gün 32 →](../gun-32-laravel-crud/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Laravel Form Request konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Form Request, istek doğrulamasını ayrı sınıfta tutar. make:request StoreTaskRequest komutuyla oluşturulur. Örnek rules metodudur. authorize metodu da ayrı karar verir; doğrulama erişim izni anlamına gelmez.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```php
public function rules(): array
{
    return [
        // İzin verilen alan ve sınırlar açıkça tanımlanır.
        'title' => ['required', 'string', 'max:120'],
        'completed' => ['sometimes', 'boolean'],
    ];
}
```

**Beklenen davranış:** Geçersiz girişte 422 ve title alanına bağlı hata döner.

## Uygulama

StoreTaskRequest oluştur; authorize kararını belirle. JSON isteyen istekle boş başlık gönder.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

$request->all() yerine validated() kullan; rol gibi hassas alanları toplu atamaya açma.

## Kaynak

[Resmî dokümantasyon](https://laravel.com/docs/13.x/validation)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
