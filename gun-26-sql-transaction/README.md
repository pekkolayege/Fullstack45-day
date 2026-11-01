# Gün 26 · Transaction ve indeksler

[← Gün 25](../gun-25-sql-join/README.md) · [Ana yol haritası](../README.md) · [Gün 27 →](../gun-27-laravel-kurulum/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

Transaction ve indeksler konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

Transaction birden çok değişikliği tek işlem olarak ele alır. Hata durumunda ROLLBACK bütün işlemi geri alır. İndeks okumayı hızlandırabilir ancak yazma ve depolama maliyeti vardır; sorgu planıyla değerlendirilmelidir.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```sql
BEGIN;
-- Örnek güncelleme yalnızca mevcut alıştırma projesine uygulanır.
UPDATE projects SET name = 'Deneme' WHERE id = 1;
-- Öğrenme amacıyla değişikliği kalıcılaştırmadan geri alıyoruz.
ROLLBACK;
-- Yabancı anahtar PostgreSQL'de bu indeksi kendiliğinden oluşturmaz.
CREATE INDEX tasks_project_id_idx ON tasks(project_id);
```

**Beklenen davranış:** Proje adı değişmez; indeksin sorgu planındaki etkisi açıklanır.

## Uygulama

ROLLBACK sonrası eski adı kontrol et. EXPLAIN ile proje görev sorgusunun planını incele.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

Küçük tabloda sıralı tarama görülmesi indeksin bozuk olduğu anlamına gelmez.

## Kaynak

[Resmî dokümantasyon](https://www.postgresql.org/docs/current/tutorial-transactions.html)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
