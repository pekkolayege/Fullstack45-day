# Gün 14 · Yönlendirme ve URL tasarımı

[← Gün 13](../gun-13-react-formlar/README.md) · [Ana yol haritası](../README.md) · [Gün 15 →](../gun-15-react-effect/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Yönlendirme ve URL tasarımı konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

URL ekranın paylaşılabilir adresidir. /projects proje listesini, /projects/42 belirli projeyi temsil edebilir. URL parametreleri güvenilir veri değildir; istemci ve sunucu bunları doğrulamalıdır. Aşağıdaki saf fonksiyon yönlendirme kütüphanesi kurmadan parametre doğrulamayı öğretir.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```typescript
function parseProjectId(value: string): number | null {
  // Yalnızca pozitif tam sayı biçimini kabul ederiz.
  if (!/^[1-9]\d*$/.test(value)) return null;
  const id = Number(value);
  return Number.isSafeInteger(id) ? id : null;
}
console.log(parseProjectId('42')); // 42
console.log(parseProjectId('42abc')); // null
```

**Beklenen davranış:** Boş, negatif ve kısmi sayısal değerler reddedilir.

## Uygulama

Liste, detay ve bulunamadı ekranı için URL tablosu hazırla. Geçersiz kimliği detay API'sine göndermeden ele al.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

parseInt('42abc') sonucunu tam doğrulama sanma.

## Kaynak

[Resmî dokümantasyon](https://developer.mozilla.org/en-US/docs/Web/API/URL)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
