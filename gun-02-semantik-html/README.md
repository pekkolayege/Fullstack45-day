# Gün 02 · Semantik HTML

[← Gün 1](../gun-01-web-ve-git/README.md) · [Ana yol haritası](../README.md) · [Gün 3 →](../gun-03-formlar/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Semantik HTML konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Semantik HTML içeriğin görevini açıklar. main ana içeriği, article bağımsız içeriği ve nav gezinmeyi temsil eder. Başlık düzeyleri görsel boyut seçmek için değil içerik hiyerarşisi için kullanılır. Tarayıcıda açılabilen örneği index.html olarak kaydet.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```html
<!doctype html>
<html lang="tr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>Öğrenme günlüğü</title>
</head>
<body>
  <!-- Tek ana içerik alanı gezinmeyi kolaylaştırır. -->
  <main><h1>Öğrenme günlüğüm</h1>
    <article><h2>İlk gün</h2><p>Git ile ilk kaydımı oluşturdum.</p></article>
  </main>
</body>
</html>
```

**Beklenen davranış:** Bir h1 ve iki h2 bulunur; içerik CSS olmadan da anlamlı okunur.

## Uygulama

İki günlük notu article içinde göster; sayfaya anlamlı title ve Türkçe dil tanımı ekle.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Başlık düzeylerini yalnızca yazı boyutunu değiştirmek için atlama.

## Kaynak

[Resmî dokümantasyon](https://developer.mozilla.org/en-US/docs/Glossary/Semantics)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
