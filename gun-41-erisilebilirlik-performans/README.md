# Gün 41 · Erişilebilirlik ve performans

[← Gün 40](../gun-40-frontend-test/README.md) · [Ana yol haritası](../README.md) · [Gün 42 →](../gun-42-guvenlik/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Erişilebilirlik ve performans konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Erişilebilirlik semantik yapı, klavye, odak ve anlaşılır geri bildirim gerektirir. Performans ölçümü önce darboğazı belirler; varsayımla optimizasyon yapma. Örnek işlem sonucunu ekran okuyucuya duyuran HTML parçasıdır.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```html
<!-- Düşük öncelikli bildirim mevcut okumayı kesmeden duyurulur. -->
<p role="status" aria-live="polite">Görev kaydedildi.</p>
<!-- Alanın hatası aria-describedby ile ilgili alana bağlanır. -->
<label for="title">Başlık</label>
<input id="title" aria-describedby="title-error" aria-invalid="true">
<p id="title-error">Başlık boş bırakılamaz.</p>
```

**Beklenen davranış:** Bulunan sorun için ölçüm, değişiklik ve tekrar ölçüm kaydı vardır.

## Uygulama

Klavye ile tüm akışı dene. Ağ panelinde yinelenen istekleri ve veritabanında sorgu sayısını ölç.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Lighthouse puanı tek başına bütün erişilebilirlik koşullarını doğrulamaz.

## Kaynak

[Resmî dokümantasyon](https://www.w3.org/WAI/tutorials/)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
