# Gün 29 · Migration ve seed

[← Gün 28](../gun-28-laravel-controller/README.md) · [Ana yol haritası](../README.md) · [Gün 30 →](../gun-30-eloquent/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Migration ve seed konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Migration veritabanı şemasının sürümlenmiş tarifidir. Seeder geliştirme verisini üretir. Örnek oluşturduğun migration sınıfının up metodunda yer alır; Schema ve Blueprint import edilmelidir.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```php
Schema::create('projects', function (Blueprint $table) {
    // Otomatik kimlik ve zaman damgaları ortak şema kurallarıdır.
    $table->id();
    $table->string('name', 120);
    $table->timestamps();
});
```

**Beklenen davranış:** Boş veritabanında şema ve beş kayıt yeniden üretilebilir.

## Uygulama

Projects migration'ı ve beş örnek kayıt üreten seeder yaz. Sadece alıştırma veritabanında migrate ve db:seed çalıştır.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

migrate:fresh tabloları siler; paylaşılan veya üretim veritabanında kullanma.

## Kaynak

[Resmî dokümantasyon](https://laravel.com/docs/13.x/migrations)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
