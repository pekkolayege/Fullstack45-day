# Gün 25 · İlişkiler ve JOIN

[← Gün 24](../gun-24-sql-crud/README.md) · [Ana yol haritası](../README.md) · [Gün 26 →](../gun-26-sql-transaction/README.md)

**Hazırlayan:** Ege Pekkolay  
**Çalışma süresi:** Yaklaşık 3–4 saat; araştırma ve alıştırmalar dahil.  
**Ön koşul:** Önceki günlerin kavramları; örnekte belirtilen çalışma ortamı.

## Öğrenme hedefi

İlişkiler ve JOIN konusunu açıklamak, örneğin veri akışını takip etmek ve aşağıdaki alıştırmayı kendi çalışma alanında tamamlamak.

## Konu anlatımı

INNER JOIN eşleşen kayıtları, LEFT JOIN soldaki eşleşmeyen kayıtları da getirir. Çoklu ilişkiler sayımı çoğaltabilir. Görevsiz projeleri de göstermek için LEFT JOIN gerekir. Gün 23 tablolarını kullan.

## Açıklamalı örnek

Bu örnek dersin kavramını gösterir. Proje içi parçalar bağımsız program değildir; gerekli sınıflar, değişkenler ve kurulum koşulları anlatımda belirtilmiştir.

```sql
-- COUNT(t.id), görevsiz projedeki NULL satırını saymaz.
SELECT p.id, p.name, COUNT(t.id) AS task_count
FROM projects AS p
LEFT JOIN tasks AS t ON t.project_id = p.id
GROUP BY p.id, p.name
ORDER BY p.id;
```

**Beklenen davranış:** Her iki proje görünür; görev sayıları sırasıyla 0 ve 2 olur.

## Uygulama

Bir görevsiz, bir iki görevli proje oluştur ve sorguyu çalıştır.

[Ayrıntılı çalışma ve kontrol listesi](ALISTIRMALAR.md)

## Sık yapılan hata

COUNT(*) görevsiz projedeki birleştirilmiş satırı da sayar.

## Kaynak

[Resmî dokümantasyon](https://www.postgresql.org/docs/current/tutorial-join.html)

---

**Hatalı Kod ve Destek:** [info@egepekkolay.com.tr](mailto:info@egepekkolay.com.tr)
