# Gün 12 · State ve güncelleme

[← Gün 11](../gun-11-react-props/README.md) · [Ana yol haritası](../README.md) · [Gün 13 →](../gun-13-react-formlar/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

State ve güncelleme konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

State bileşenin hatırladığı veridir. Önceki değere bağlı güncellemelerde işlevsel güncelleme kullanılır. State dizisini push ile değiştirmek yerine yeni dizi üretmek React'in veri akışını anlaşılır kılar.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```tsx
import { useState } from 'react';
export function Counter() {
  const [count, setCount] = useState(0);
  return <button onClick={() => {
    // Güncelleme, sıradaki en güncel state üzerinden hesaplanır.
    setCount(previous => previous + 1);
  }}>{count}</button>;
}
```

**Beklenen davranış:** İki bağımsız Counter kendi durumunu tutar; önceki liste değiştirilmez.

## Uygulama

Sayacı görev listesine uyarla; görev tamamlandığında yalnızca ilgili nesneyi yenile.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

State'i doğrudan değiştirmek render güncellemesini garanti etmez.

## Kaynak

[Resmî dokümantasyon](https://react.dev/learn/updating-arrays-in-state)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
