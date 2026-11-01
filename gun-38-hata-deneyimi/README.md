# Gün 38 · Oturum ve hata deneyimi

[← Gün 37](../gun-37-api-entegrasyonu/README.md) · [Ana yol haritası](../README.md) · [Gün 39 →](../gun-39-backend-test/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Oturum ve hata deneyimi konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

401 geçerli kimlik doğrulama gerektiğini, 403 izin olmadığını, 422 doğrulama hatasını ifade eder. Kullanıcıya eyleme dönük mesaj göster. Beklenmeyen hataların teknik ayrıntısı günlükte kalmalı; arayüz yığın izi göstermemelidir.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```typescript
function messageFor(status: number): string {
  // Kullanıcı hangi adımı atabileceğini anlayabilmelidir.
  if (status === 401) return 'Devam etmek için giriş yapın.';
  if (status === 403) return 'Bu işlem için yetkiniz bulunmuyor.';
  if (status === 422) return 'İşaretlenen alanları kontrol edin.';
  return 'İşlem tamamlanamadı. Lütfen tekrar deneyin.';
}
```

**Beklenen davranış:** Sunucu yanıtı kaybolmadan doğru kullanıcı davranışına dönüşür.

## Uygulama

401 için giriş yönlendirmesi, 403 için bilgi ekranı, 422 için alan hataları ekle.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Her hatada oturumu silme; doğrulama hatası giriş sorunu değildir.

## Kaynak

[Resmî dokümantasyon](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Status)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
