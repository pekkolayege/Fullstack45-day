# Gün 36 · Policy ve proje rolleri

[← Gün 35](../gun-35-sanctum-csrf/README.md) · [Ana yol haritası](../README.md) · [Gün 37 →](../gun-37-api-entegrasyonu/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Policy ve proje rolleri konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Yetkilendirme kullanıcının hangi işlemi yapabileceğini belirler. Rolü global kullanıcı alanı yerine proje üyeliğinde tutmak farklı projelerde farklı yetki sağlar. Örnek ProjectPolicy metodudur; memberships ilişkisi ve user_id/role alanları gerekir.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```php
public function delete(\App\Models\User $user, \App\Models\Project $project): bool
{
    // Yetki yalnızca işlem yapılan projenin üyeliği üzerinden hesaplanır.
    return $project->memberships()
        ->where('user_id', $user->id)
        ->where('role', 'admin')
        ->exists();
}
```

**Beklenen davranış:** Hedef projede admin olmayan kullanıcı 403 alır ve veri değişmez.

## Uygulama

Controller'da Gate::authorize('delete', $project) uygula. Başka proje yöneticisiyle aynı işlemi dene.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Arayüzde düğmeyi gizlemek sunucu yetkilendirmesinin yerine geçmez.

## Kaynak

[Resmî dokümantasyon](https://laravel.com/docs/13.x/authorization)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
