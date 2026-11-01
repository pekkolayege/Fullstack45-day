# Gün 01 · Web ve Git

[Ana yol haritası](../README.md) · [Gün 2 →](../gun-02-semantik-html/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Temel HTML, CSS ve JavaScript bilgisi.

## Öğrenme hedefi

Web ve Git konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Bir web isteği tarayıcıdan sunucuya gider; sunucu bir HTTP yanıtı üretir. HTML yapıyı, CSS görünümü, JavaScript etkileşimi yönetir. Git ise bu dosyaların zaman içindeki değişimini kaydeder. Commit, tek bir anlamlı değişikliğin açıklamalı kaydı olmalıdır.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```bash
# Yeni ve boş bir çalışma klasöründe çalıştır.
git init -b main
# Editörde oluşturduğun README dosyasını kayda hazırla.
git add README.md
git commit -m "docs: add learning goals"
# Son kaydı ve çalışma alanını incele.
git log --oneline
git status
```

**Beklenen davranış:** git log çıktısında açıklayıcı commit görünür; git status beklenmeyen dosya göstermez.

## Uygulama

Üç öğrenme hedefini README.md dosyasına yaz ve tek commit oluştur.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

git add . öncesinde dosyaları incele; .env gibi sırları kaydetme.

## Kaynak

[Resmî dokümantasyon](https://git-scm.com/book/en/v2)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
