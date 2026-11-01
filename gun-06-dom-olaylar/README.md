# Gün 06 · DOM ve olaylar

[← Gün 5](../gun-05-javascript-temelleri/README.md) · [Ana yol haritası](../README.md) · [Gün 7 →](../gun-07-async-http/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

DOM ve olaylar konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

DOM belgenin tarayıcıdaki nesne ağacıdır. Olay dinleyicileri kullanıcı eylemlerini işler. textContent metni HTML olarak yorumlamaz. Örneği HTML dosyası olarak kaydet; betik düğmeden sonra olduğu için eleman hazırdır.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```html
<button id="counter" type="button">0 kez tıklandı</button>
<script>
  const button = document.querySelector('#counter');
  let count = 0;
  button.addEventListener('click', () => {
    count += 1;
    // Düğmenin kendisini değiştirmeden yalnızca metni güncelleriz.
    button.textContent = `${count} kez tıklandı`;
  });
</script>
```

**Beklenen davranış:** Üç tıklamadan sonra 3 görünür; sıfırlama sonrası 0 görünür.

## Uygulama

Sayacı sıfırlayan ikinci bir düğme ekle ve klavyeyle dene.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Kullanıcı girdisini innerHTML ile doğrudan yerleştirme.

## Kaynak

[Resmî dokümantasyon](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
