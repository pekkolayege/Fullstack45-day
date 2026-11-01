# Gün 04 · CSS ve responsive düzen

[← Gün 3](../gun-03-formlar/README.md) · [Ana yol haritası](../README.md) · [Gün 5 →](../gun-05-javascript-temelleri/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

CSS ve responsive düzen konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Kutu modeli içerik, padding, border ve margin'den oluşur. border-box genişlik hesabını öngörülebilir yapar. Grid iki boyutlu yerleşim sağlar. Aşağıdaki stil için HTML içinde cards sınıfına sahip bir kapsayıcı ve birkaç article oluştur.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```css
/* Kenarlık ve iç boşluk verilen genişliğe dahil edilir. */
* { box-sizing: border-box; }
.cards { display: grid; gap: 1rem; grid-template-columns: 1fr; }
.cards article { padding: 1rem; border: 1px solid #667085; }
/* İçerik için yer olduğunda iki sütuna geçilir. */
@media (min-width: 48rem) {
  .cards { grid-template-columns: repeat(2, 1fr); }
}
:focus-visible { outline: 3px solid #7540c8; outline-offset: 3px; }
```

**Beklenen davranış:** Yatay taşma yoktur ve klavye odağı görünürdür.

## Uygulama

360, 768 ve 1280 piksel genişlikte kart düzenini kontrol et. Uzun başlıkla tekrar dene.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Taşmayı overflow:hidden ile gizlemek yerine sebebini düzelt.

## Kaynak

[Resmî dokümantasyon](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Responsive_Design)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
