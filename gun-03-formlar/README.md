# Gün 03 · Formlar ve erişilebilirlik

[← Gün 2](../gun-02-semantik-html/README.md) · [Ana yol haritası](../README.md) · [Gün 4 →](../gun-04-css-responsive/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Formlar ve erişilebilirlik konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Form alanlarının görünür etiketleri olmalıdır. label içindeki for, input kimliğiyle eşleşir. required tarayıcı doğrulaması sağlar ancak sunucu doğrulamasının yerini tutmaz. Bu HTML parçasını önceki günün main alanına yerleştir. Örnek veri gönderme sunucusu içermez.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```html
<!-- Etikete tıklamak ilgili alana odaklanır. -->
<form>
  <label for="email">E-posta</label>
  <input id="email" name="email" type="email" required>
  <!-- Form içindeki işlem türü açıkça belirtilir. -->
  <button type="submit">Kontrol et</button>
</form>
```

**Beklenen davranış:** Boş ve geçersiz e-posta tarayıcı tarafından reddedilir; her alanın etiketi vardır.

## Uygulama

Ad ve e-posta alanı ekle. Yalnızca Tab, Shift+Tab ve Enter kullanarak formu dene.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Placeholder etiket değildir; kullanıcı yazınca kaybolur.

## Kaynak

[Resmî dokümantasyon](https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Forms)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
