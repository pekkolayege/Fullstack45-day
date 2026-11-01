# Gün 30 · Eloquent ilişkileri

[← Gün 29](../gun-29-laravel-migration/README.md) · [Ana yol haritası](../README.md) · [Gün 31 →](../gun-31-laravel-validation/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Eloquent ilişkileri konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Eloquent modelleri tablo kayıtlarını temsil eder. hasMany bir kaydın çok sayıda alt kaydını tanımlar. Eager loading ilişkileri önceden yükleyerek döngü içinde tekrarlı sorguları azaltır. Project ve Task modelleri ile project_id alanı gerekir.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```php
// Project modelinin içinde; dönüş tipi ilişkiyi açıklar.
public function tasks(): \Illuminate\Database\Eloquent\Relations\HasMany
{
    return $this->hasMany(Task::class);
}
// Controller içinde ilişkileri önceden yükleyerek listeleyebiliriz.
// $projects = Project::with('tasks')->get();
```

**Beklenen davranış:** Her görev doğru projeye bağlıdır; sorgu sayısı proje adediyle doğrusal artmaz.

## Uygulama

Task modelinde belongsTo ilişkisini kur. Ön yüklemeli ve ön yüklemesiz sorgu sayısını karşılaştır.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

with('tasks') bütün görevleri yükler; büyük listelerde sayfalama veya withCount düşün.

## Kaynak

[Resmî dokümantasyon](https://laravel.com/docs/13.x/eloquent-relationships)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
