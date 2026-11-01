# Gün 09 · Union tipler ve daraltma

[← Gün 8](../gun-08-typescript/README.md) · [Ana yol haritası](../README.md) · [Gün 10 →](../gun-10-react-baslangic/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Union tipler ve daraltma konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Union bir değerin izin verilen alternatiflerini tanımlar. Ayrıştırıcı alan ile farklı durumları güvenli biçimde ele alabiliriz. Yükleniyor, başarı ve hata durumlarını ayrı modellemek olanaksız kombinasyonları azaltır.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```typescript
type Result =
  | { status: 'loading' }
  | { status: 'success'; count: number }
  | { status: 'error'; message: string };
function describe(result: Result): string {
  // status kontrolü ilgili alanları güvenli biçimde erişilebilir kılar.
  if (result.status === 'success') return `${result.count} görev`;
  if (result.status === 'error') return result.message;
  return 'Yükleniyor';
}
```

**Beklenen davranış:** loading durumunda count alanını okumaya çalışmak tip hatası verir.

## Uygulama

Boş listeyi success durumunda count:0 ile temsil et. Üç durumu da çağır.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Her alanı opsiyonel yapmak yerine durumları anlamlı biçimde ayır.

## Kaynak

[Resmî dokümantasyon](https://www.typescriptlang.org/docs/handbook/2/narrowing.html)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
