# Gün 40 · Frontend ve uçtan uca test

[← Gün 39](../gun-39-backend-test/README.md) · [Ana yol haritası](../README.md) · [Gün 41 →](../gun-41-erisilebilirlik-performans/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Frontend ve uçtan uca test konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Kullanıcı davranışını sınayan test, iç değişkenlere bağımlı testten daha dayanıklıdır. Aşağıdaki Playwright örneği kurulu test projesi, baseURL ve kayıtlı kullanıcıyla giriş yapılmış storageState gerektirir. Test verisi her çalışmada hazırlanmalıdır.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```typescript
import { test, expect } from '@playwright/test';
test('boş görev başlığı reddedilir', async ({ page }) => {
  await page.goto('/projects/1');
  // Erişilebilir adlarla seçim yapmak test ile kullanıcı deneyimini hizalar.
  await page.getByRole('textbox', { name: 'Başlık', exact: true }).fill('   ');
  await page.getByRole('button', { name: 'Görev ekle', exact: true }).click();
  await expect(page.getByRole('alert')).toContainText('Başlık');
});
```

**Beklenen davranış:** Testler ayrı test ortamında tekrar çalıştırılabilir.

## Uygulama

Başarılı görev ekleme ve yenileme sonrası kaydı görme testini ekle.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Sabit bekleme süreleri yerine gözlenebilir sonucu bekle.

## Kaynak

[Resmî dokümantasyon](https://playwright.dev/docs/intro)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
