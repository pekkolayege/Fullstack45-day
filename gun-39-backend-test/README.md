# Gün 39 · Backend davranış testleri

[← Gün 38](../gun-38-hata-deneyimi/README.md) · [Ana yol haritası](../README.md) · [Gün 40 →](../gun-40-frontend-test/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Backend davranış testleri konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Özellik testleri HTTP isteği ile veritabanı etkisini birlikte sınar. Aşağıdaki metot Laravel PHPUnit test sınıfına eklenir. User/Project modelleri, factory, DELETE yolu ve policy gerekir; test sınıfında RefreshDatabase yalnızca ayrılmış test veritabanıyla kullanılmalıdır.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```php
public function test_non_member_cannot_delete_project(): void
{
    $user = \App\Models\User::factory()->create();
    $project = \App\Models\Project::factory()->create();
    // Üyeliği olmayan kullanıcı için hem yanıtı hem veri etkisini doğrularız.
    $this->actingAs($user)
        ->deleteJson('/api/projects/' . $project->id)
        ->assertForbidden();
    $this->assertDatabaseHas('projects', ['id' => $project->id]);
}
```

**Beklenen davranış:** php artisan test geçer; yetkisiz işlemde kayıt korunur.

## Uygulama

Yetkili silme, yetkisiz silme ve doğrulama hatası için üç test yaz.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Yalnızca yanıt kodunu test etmek istenmeyen veri değişimini kaçırabilir.

## Kaynak

[Resmî dokümantasyon](https://laravel.com/docs/13.x/http-tests)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
