# Gün 16 · Frontend değerlendirmesi

[← Gün 15](../gun-15-react-effect/README.md) · [Ana yol haritası](../README.md) · [Gün 17 →](../gun-17-php-temelleri/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Frontend değerlendirmesi konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Arayüzün çalışması yalnızca ideal veriyle görünmesi değildir. Boş, yükleniyor ve hata durumları ayrı değerlendirilir. Klavye odağı, form etiketleri ve dar ekran davranışı teslim kriterinin parçasıdır.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```typescript
type ViewState = 'loading' | 'empty' | 'error' | 'ready';
function chooseView(loading: boolean, error: string, count: number): ViewState {
  // Hata ve yüklenme durumlarını boş veriyle karıştırmayız.
  if (loading) return 'loading';
  if (error) return 'error';
  return count === 0 ? 'empty' : 'ready';
}
```

**Beklenen davranış:** Dört durum için ayrı ekran veya açıklama vardır; odağın yeri takip edilir.

## Uygulama

İlk 15 günün çalışmalarını dört görünüm durumu, klavye ve mobil düzen bakımından incele.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Boş listeyi otomatik olarak hata kabul etme.

## Kaynak

[Resmî dokümantasyon](https://react.dev/learn/conditional-rendering)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
