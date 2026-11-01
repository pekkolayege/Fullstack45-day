# Gün 05 · JavaScript veri temelleri

[← Gün 4](../gun-04-css-responsive/README.md) · [Ana yol haritası](../README.md) · [Gün 6 →](../gun-06-dom-olaylar/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

JavaScript veri temelleri konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Nesneler ilişkili alanları, diziler koleksiyonları taşır. map her öğeyi dönüştürür; filter koşula uyanları seçer. const değişken bağını korur, nesnenin içeriğini otomatik olarak değişmez yapmaz. Örneği tarayıcı konsolunda veya node example.js komutuyla çalıştır.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```javascript
const tasks = [
  { id: 1, title: 'HTML tekrarı', completed: true },
  { id: 2, title: 'CSS alıştırması', completed: false },
];
// Eski diziye dokunmadan bekleyen başlıkları seçeriz.
const pending = tasks.filter(task => !task.completed);
console.log(pending.map(task => task.title));
```

**Beklenen davranış:** Çıktı yalnızca CSS alıştırmasını içerir; boş dizide sayı sıfırdır.

## Uygulama

Üç görev oluştur. Tamamlananların sayısını hesaplayan fonksiyon yaz.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Görevleri başlıkla değil sabit bir kimlikle ayırt et.

## Kaynak

[Resmî dokümantasyon](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
