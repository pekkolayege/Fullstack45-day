# Gün 44 · CI ve operasyon

[← Gün 43](../gun-43-yayinlama/README.md) · [Ana yol haritası](../README.md) · [Gün 45 →](../gun-45-portfoy/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

CI ve operasyon konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Sürekli entegrasyon, değişikliklerde tanımlı kontrolleri otomatik çalıştırır. Başarılı test her üretim riskini ortadan kaldırmaz. Aşağıdaki GitHub Actions örneği kökte package.json/package-lock.json ve npm test betiği bulunan öğrencinin ayrı frontend projesi içindir.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```yaml
name: Frontend checks
on: [push, pull_request]
permissions:
  contents: read
jobs:
  check:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: '22'
      # Kilit dosyasına göre tekrar üretilebilir kurulum yapar.
      - run: npm ci
      - run: npm test
      - run: npm run build
```

**Beklenen davranış:** Hatalı test CI'ı başarısız yapar; geri yükleme alıştırma ortamında denenir.

## Uygulama

Kendi uygulamanın test betiklerine göre workflow'u uyarla. Veritabanı yedekleme ve geri yükleme adımlarını ayrı belgeye yaz.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Yedek dosyası almak, geri yüklenebildiğini kanıtlamaz.

## Kaynak

[Resmî dokümantasyon](https://docs.github.com/en/actions)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
