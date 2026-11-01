# Gün 33 · API sözleşmesi ve kontrol noktası

[← Gün 32](../gun-32-laravel-crud/README.md) · [Ana yol haritası](../README.md) · [Gün 34 →](../gun-34-kimlik-dogrulama/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

API sözleşmesi ve kontrol noktası konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

API sözleşmesi yöntem, yol, veri ve hata davranışını açıklar. Başarılı JSON ile hata gövdeleri tutarlı olmalıdır. Örnek, oluşturulmuş görev için 201 yanıt gövdesidir; gerçek HTTP durum kodu ayrıca ayarlanır.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```json
{
  "data": {
    "id": 42,
    "project_id": 1,
    "title": "API sözleşmesini yaz",
    "completed": false
  }
}
```

**Beklenen davranış:** Bir başka geliştirici yalnızca sözleşmeyi okuyarak örnek istek hazırlayabilir.

## Uygulama

GET/POST/PATCH/DELETE uç noktalarını tablo halinde yaz. 401, 403, 404 ve 422 senaryolarını ayır.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Hata durumunu yalnızca JSON içine yazıp HTTP 200 döndürme.

## Kaynak

[Resmî dokümantasyon](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Status)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
